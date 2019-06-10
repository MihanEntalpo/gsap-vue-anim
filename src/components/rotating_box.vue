<template>
    <div ref="box_anim" class="box_anim anim-container" ><div ref="box" class=box :style="style"></div></div>
</template>

<script> 
import { TimelineLite, Linear } from 'gsap'
export default { 
  mounted() { 
    const box_anim = this.$refs.box_anim;
    const timeline = new TimelineLite();
    
    timeline.to(box_anim, 1 / this.speed, {rotation: "+=90", ease:Linear.easeNone, repeat: -1 });
  },
  props: {'color':{'default':'red'}, 'size':{'default':'100'}, 'speed':{'default':1}},
  computed: {
      style() {
          return "width:" + (this.size || 100) + "px; height:" + (this.size || 100) + "px; background-color: " + (this.color || 'red')
      }
  }
} 
</script>

<style scoped>
    .box_anim {
        position:absolute;
    }
</style>