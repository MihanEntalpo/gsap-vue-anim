<template>
    <div class="heading anim-container" ref="heading">
        <h1 v-if="size == 1" class="text"><slot>Контент не задан</slot></h1>
        <h2 v-else-if="size == 2" class="text"><slot>Контент не задан</slot></h2>
        <h3 v-else-if="size == 3" class="text"><slot>Контент не задан</slot></h3>
        <h4 v-else-if="size == 4" class="text"><slot>Контент не задан</slot></h4>
        <h5 v-else-if="size == 5" class="text"><slot>Контент не задан</slot></h5>
        <p v-else>Непонятный размер: {{size}}</p>
    </div>
</template>
<script>
    
import { Linear, TweenMax } from 'gsap'
    
export default {
  name: 'heading',
  props: {
      size: {
          default: "1"
      }
  },
  components: {},
  mounted() {
      
  } 
}
</script>
<style scoped>
    .heading
    {
        position:absolute;
    }
</style>