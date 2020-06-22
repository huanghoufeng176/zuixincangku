<template>
  <div class="tab-bar">
    <slot></slot>
  </div>
</template>

<script>
export default {
  components:{},
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
  .tab-bar{
    background-color: #f6f6f6;
    display: flex;
    position: fixed;
    left: 0;
    right: 0;
    bottom: 0;
  }
</style>