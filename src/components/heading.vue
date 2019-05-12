<template>
    <div class="heading" ref="heading">
        <h1 v-if="size == 1" class="text">{{text}}</h1>
        <h2 v-else-if="size == 2" class="text">{{text}}</h2>
        <h3 v-else-if="size == 3" class="text">{{text}}</h3>
        <h4 v-else-if="size == 4" class="text">{{text}}</h4>
        <h5 v-else-if="size == 5" class="text">{{text}}</h5>
        <p v-else>Непонятный размер: {{size}}</p>
    </div>
</template>
<script>
    
import { Linear, TweenMax } from 'gsap'
    
export default {
  name: 'heading',
  props: {
      text: {
          default: "Heading!"
      },
      size: {
          default: "1"
      },
      x: {
          default: 0
      },
      y: {
          default: 0
      }
  },
  components: {},
  mounted() {
      const heading = this.$refs.heading;
      TweenMax.set(heading, {x: this.x, y: this.y});
  } 
}
</script>
<style scoped>
    .heading
    {
        position:absolute;
    }
</style>