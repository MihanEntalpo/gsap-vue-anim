<template>
    <div class="background" :style="style">
        <slot></slot>
    </div>
</template>
<script>
export default { 
  name: "background",
  mounted() { 
    
  },
  props: {'image':{'default':'paper0.png'}},
  computed: {
      style() {
          let src = require("../assets/background/" + this.image);
          return "background-image: url(" + src + ")";
      }
  }
} 
</script>
<style scoped>
    .background
    {
        position:absolute;
        left:0px;
        top:0px;
        width:100%;
        height:100%;
    }
</style>