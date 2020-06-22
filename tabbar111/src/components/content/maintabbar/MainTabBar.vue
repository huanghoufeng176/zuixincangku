<template>
  <div class="main-tab-bar">
    <tab-bar>
      <tab-bar-item path="/home">
        <img slot="tab-bar-icon" src="~assets/img/tabbar/home.svg" alt="">
        <img slot="tab-bar-active" src="~assets/img/tabbar/home_active.svg" alt="">
        <div slot="tab-bar-text">首页</div>
      </tab-bar-item>
      <tab-bar-item path="/category">
        <img slot="tab-bar-icon" src="~assets/img/tabbar/category.svg" alt="">
        <img slot="tab-bar-active" src="~assets/img/tabbar/category_active.svg" alt="">
        <div slot="tab-bar-text">档案</div>
      </tab-bar-item>
      <tab-bar-item path="/cart">
        <img slot="tab-bar-icon" src="~assets/img/tabbar/shopcart.svg" alt="">
        <img slot="tab-bar-active" src="~assets/img/tabbar/shopcart_active.svg" alt="">
        <div slot="tab-bar-text">商品</div>
      </tab-bar-item>
      <tab-bar-item path="/profile">
        <img slot="tab-bar-icon" src="~assets/img/tabbar/profile.svg" alt="">
        <img slot="tab-bar-active" src="~assets/img/tabbar/profile_active.svg" alt="">
        <div slot="tab-bar-text">我的</div>
      </tab-bar-item>
    </tab-bar>
  </div>
</template>

<script>

import TabBar from 'components/common/tabbar/TabBar.vue'
import TabBarItem from 'components/common/tabbar/TabBarItem.vue'

export default {
  components:{
    TabBar,
    TabBarItem
  },
  data(){
    return {
    }
  },
  created(){},
  mounted(){},
  watch:{},
  computed:{},
  methods:{},
}
</script>
<style scoped>
</style>