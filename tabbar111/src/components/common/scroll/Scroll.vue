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
    },
    pullUpLoad:{
      type:Boolean,
      default:false
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
      probeType:this.probeType,
      pullUpLoad:this.pullUpLoad
    })
    //2.监听滚动的位置
    this.scroll.on('scroll',position=>{
      // console.log(position)
      this.$emit('scroll',position)
    })
    //3.上拉加载更多
    this.scroll.on('pullingUp',()=>{
      this.$emit('pullingUp')
    })
  },
  watch:{},    
  computed:{},
  methods:{
    scrollTo(x,y,time=30){
      this.scroll.scrollTo(x,y,time)
    },
    finishPullUp(){
      this.scroll.finishPullUp()
    },
    refresh(){
      this.scroll && this.scroll.refresh()
      console.log('----')
    }
  },
}
</script>
<style scoped>

</style>