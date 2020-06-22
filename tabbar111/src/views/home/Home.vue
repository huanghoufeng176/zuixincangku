<template>
  <div class="">
    <nav-bar class="home-nav"><div slot="center">购物街</div>></nav-bar>
  </div>
</template>

<script>

import NavBar from 'components/common/navbar/NavBar.vue'

import {getHomeMultidata} from 'network/home.js'

export default {
  components:{
    NavBar,
    
  },
  data(){
    return {
      banners:[],
      recommends:[]
    }
  },
  created(){
    getHomeMultidata(){

    }
  },
  mounted(){},
  watch:{},
  computed:{},
  methods:{},
}
</script>
<style scoped>
  .home-nav{
    background-color: pink;
    color: #fff;
  }
</style>