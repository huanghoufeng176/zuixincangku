<template>
  <div class="tab-bar-item" @click="itemClick">
    <div v-if="!isActive"><slot name="tab-bar-icon"></slot></div>
    <div v-else><slot name="tab-bar-active"></slot></div>
    <div :style="styleActive"><slot name="tab-bar-text"></slot></div>
  </div>
</template>

<script>
export default {
  props:{
    path:String,
  },
  components:{},
  data(){
    return {
      // isActive:false
    }
  },
  created(){},
  mounted(){},
  watch:{},
  computed:{
    isActive(){
      // return this.$route.path.indexOf(this.path)!==-1
      return this.$route.path.indexOf(this.path)!==-1
    },
    styleActive(){
      return this.isActive?{color:'red'}:{}
    }
  },
  methods:{
    itemClick(){
      console.log(4444)
      // this.$router.push(this.path)
      // this.$router.push(this.path)
      this.$router.push(this.path)
    },
  },
}
</script>
<style scoped>
  .tab-bar-item{
    flex: 1;
    height: 49px;
    text-align: center;
    font-size: 14px;
    /* margin-bottom: 3px; */
  }
  .tab-bar-item img{
    width: 24px;
    height: 24px;
    margin-top: 2px;
  }
</style>