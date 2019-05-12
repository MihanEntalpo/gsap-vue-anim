<template>
  <div id="app">
  
    <animtest />
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import animtest from './components/animtest.vue'

export default {
  name: 'app',
  components: {
    animtest
  }
}
</script>

<style lang="scss">
  @import '@/scss/base.scss';
</style>
