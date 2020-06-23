<template>
<div class="wrapp" ref='aaa'>
  <div class="content">
    <button @click="btnClick">按钮</button>
    <ul>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
      <li>商品列表</li>
    </ul>
  </div>
</div>
</template>

<script>

import BScroll from 'better-scroll'

export default {
  components:{},
  data(){
    return {
      scroll:null
    }
  },
  created(){

  },
  mounted(){
    this.scroll=new BScroll(this.$refs.aaa,{
      probeType:3,
      pullUpLoad:true,
      click:true
    })

    this.scroll.on('scroll',position=>{
      console.log(position)
    })
    this.scroll.on('pullingUp',()=>{
      console.log('上啦加载更多')
    })
  },
  watch:{},
  computed:{},
  methods:{
    btnClick(){
      console.log('btnclick')
    }
  },
}
</script>
<style scoped>
  .wrapp{
    height: 150px;
    background-color: red;
    /* overflow: hidden; */
    /* overflow-y: scroll; */
  }
</style>