<template>
  <div class="">
    <router-view></router-view>
    <main-tab-bar></main-tab-bar>
  </div>
</template>

<script>

import MainTabBar from 'components/content/maintabbar/MainTabBar.vue'

export default {
  components:{
    MainTabBar,
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