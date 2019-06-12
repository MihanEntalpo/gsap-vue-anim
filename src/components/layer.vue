<template>
    <div class="anim-container layer" :style="style"><slot></slot></div>
</template>

<script> 
export default { 
  mounted() { 
    
  },
  props: {
     "opacity": {
         "default": 1
     }
  },
  computed: {
      "style": function(){ return "opacity:" + this.opacity; }
  }
} 
</script>

<style scoped>
    .anim-container.layer
    {
        position:absolute;
        left:0px;
        top:0px;
        width:100vw;
        height:100vh;
    }
</style>