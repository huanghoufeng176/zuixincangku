<template>
  <div class="home">
    <nav-bar class="home-nav"><div slot="center">购物街</div>></nav-bar>
    <scroll class="content" ref="scroll" :probe-type="3" @scroll="scrollContent">
      <home-swiper :banners="banners"></home-swiper>
      <recommend-view :recommends="recommends"></recommend-view>
      <feature-view></feature-view>
      <tab-control :titles="['流行','新款','精选']" class="tab-control" @tabClick="tabClick"></tab-control>
      <goods-list :goods="showGoods"></goods-list>
    </scroll>
    <back-top @click.native="backClick" v-show="isShow"></back-top>
  </div>
</template>

<script>

import NavBar from 'components/common/navbar/NavBar.vue'
import TabControl from 'components/content/tabControl/tabControl.vue'
import GoodsList from 'components/content/goods/GoodsList.vue'
import Scroll from 'components/common/scroll/Scroll.vue'
import BackTop from 'components/content/backTop/BackTop.vue'

import HomeSwiper from './childComps/HomeSwiper'
import RecommendView from './childComps/RecommendView'
import FeatureView from './childComps/FeatureView'

import {getHomeMultidata,getHomeGoods} from 'network/home.js'



export default {
  components:{
    NavBar,
    HomeSwiper,
    RecommendView,
    FeatureView,
    TabControl,
    GoodsList,
    Scroll,
    BackTop
  },
  data(){
    return {
      isShow:false,
      banners:[],
      recommends:[],
      goods: {
        'pop': {page: 0,list: []},
        'new': {page: 0,list: []},
        'sell': {page: 0,list: []},
      },
      currentType:'pop',
    }
  },
  created(){
    //1.请求多个数据
    this.getHomeMultidata()

    //2.请求商品数据
    this.getHomeGoods('pop')
    this.getHomeGoods('new')
    this.getHomeGoods('sell')
  },
  mounted(){},
  watch:{},
  computed:{
    showGoods(){
      return this.goods[this.currentType].list
    }
  },
  methods:{
    //事件监听相关的方法
    tabClick(index){
      switch(index){
        case 0:
          this.currentType='pop'
          break
        case 1:
          this.currentType='new'
          break
        case 2:
          this.currentType='sell'
          break
      }
    },
    backClick(){
    this.$refs.scroll.scroll.scrollTo(0,0)
    },

    scrollContent(position){
      this.isShow=(-position.y)>1000
    },
    //网络请求相关的方法
    getHomeMultidata(){
      getHomeMultidata().then(res=>{
      this.banners=res.data.banner.list;
      this.recommends=res.data.recommend.list
    })
    },
    getHomeGoods(type){
      const page=this.goods[type].page+1
      getHomeGoods(type,page).then(res=>{
      this.goods[type].list.push(...res.data.list)
      this.goods[type].page+=1
    })
    }
  },
}
</script>
<style scoped>
  .home-nav{
    background-color: pink;
    color: #fff;
    position: fixed;
    left: 0;
    top: 0;
    right: 0;
    z-index: 8;
  }
  .home{
    /* padding-top: 44px; */
    height: 100vh;
  }
  .tab-control{
    position: sticky;
    top: 44px;
    z-index: 8;
  }
  .content{
    height: calc(100% - 93px);
    overflow: hidden;
    margin-top: 44px;
  }
</style>