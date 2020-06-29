<template>
  <div class="">
    <swiper>
      <swiper-item v-for="item in banners">
        <a :href="item.link">
          <img :src="item.image" alt=""  @load="imageLoad">
        </a>
      </swiper-item>
    </swiper>
  </div>
</template>

<script>
import {Swiper,SwiperItem} from 'components/common/swiper'
export default {
  components:{
    Swiper,SwiperItem
  },
  props:{
    banners:{
      type:Array,
      default(){
        return []
      }
    }
  },
  data(){
    return {
      isLoad:false
    }
  },
  created(){},
  mounted(){},
  watch:{},
  computed:{},
  methods:{
    imageLoad(){
      if(!this.isLoad){
        this.$emit('isLoad')
        this.isLoad = true
      }
    }
  },
}
</script>
<style scoped>
</style>