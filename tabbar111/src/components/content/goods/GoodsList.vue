<template>
  <div class="goods">
    <goods-list-item v-for="item in goods" :goods-item="item"></goods-list-item>
    <!-- {{goods}} -->
  </div>
</template>

<script>

import GoodsListItem from './GoodListItem.vue'

export default {
  props:{
    goods:{
      type:Array,
      default(){
        return []
      }
    }
  },
  components:{
    GoodsListItem
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
  .goods{
    display: flex;
    /* 一行当中不包裹，可以限制在一行中显示几个小的item */
    flex-wrap: wrap;
    justify-content: space-around;
    padding: 2px;
  }
</style>