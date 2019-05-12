<template>
    <div class="background" :style="style">
        
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
          console.log(src);
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
        width:100vw;
        height:100vh;
    }
</style>