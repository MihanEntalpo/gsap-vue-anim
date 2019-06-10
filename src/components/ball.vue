<template>
    <div class="anim-container" >
        <div class="ball">
        </div>
    </div>
</template>

<script> 
import { TimelineLite, Linear } from 'gsap'
import ac from './mixins/ac.vue'
export default { 
  mounted() { 
     
  },
  props: {
     
  },
  computed: {
      
  }
} 
</script>

<style scoped>
    .ball{
            width:80px;
            height:80px;
            border-radius:100px;
            background-color:red;
            z-index:9000;
    }
</style>