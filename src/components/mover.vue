<template>
    <div ref="mover" class="anim-container abs mover" :style="style"><slot><div class="">Контент не указан</div></slot></div>
</template>

<script> 
//import { TimelineLite, Linear } from 'gsap'
export default { 
  mounted() { 
    //const mover = this.$refs.mover;
    //const timeline = new TimelineLite();
    //timeline.to(mover, 0, {x: this.x, y: this.y });
  },
  props: {
      x:{'default':0},
      y:{'default':0}
  },
  computed: {
      style: function(){
          return "left:" + this.x + "px; top:" + this.y + "px;";
      }
  }
} 
</script>

<style scoped>
    
</style>