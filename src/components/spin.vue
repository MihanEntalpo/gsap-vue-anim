<template>
    <div ref="spinner" class="anim-container spinner" ><slot><div class="">Контент не указан</div></slot></div>
</template>

<script> 
import { TimelineLite, Linear } from 'gsap'
export default { 
  mounted() { 
    const spinner = this.$refs.spinner;
    const timeline = new TimelineLite();
    timeline.set(spinner, {transformOrigin:"50% 50%"});
    timeline.to(spinner, 1 / this.speed, {rotation: "+=360", ease:Linear.easeNone, repeat: -1 });
  },
  props: {
      'speed':{'default':1}
  },
  computed: {
      
  }
} 
</script>

<style scoped>
    .spinner {
        
    }
</style>