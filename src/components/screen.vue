<template>
    <div class="anim-container screen" :style="style"><slot></slot></div>
</template>

<script> 
export default { 
  mounted() { 
    
  },
  props: {
     width: {
         default: 1024
     },
     height: {
         default: 768
     }
  },
  computed: {
      style: function(){ 
          return 'width:' + this.width + "px;height:" + this.height + "px;"; 
      }
  }
} 
</script>

<style scoped>
    .screen
    {
        border:5px solid grey;
        padding:2px;
        display: block;
        position: absolute;
    }
</style>