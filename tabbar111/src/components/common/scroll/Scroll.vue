<template>
    <div class="wrapper" ref="wrapper">
      <div class="content">
        <slot></slot>
      </div>
    </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  props:{
    probeType:{
      type:Number,
      default:0
    }
  },
  components:{},
  data(){
    return {
      scroll:null
    }
  },
  created(){},
  mounted(){
    //1.创建bscroll
    this.scroll=new BScroll(this.$refs.wrapper,{
      click:true,
      probeType:this.probeType
    })
    //2.监听滚动的位置
    this.scroll.on('scroll',position=>{
      // console.log(position)
      this.$emit('scroll',position)
    })
  },
  watch:{},
  computed:{},
  methods:{},
}
</script>
<style scoped>

</style>