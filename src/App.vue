<template>
  <div id="app">
    <Intro/>
  </div>
</template>

<script>
import Intro from './components/Intro.vue'

export default {
  name: 'app',
  components: {
    Intro
  }
}
</script>

<style>
body {
  margin: 0;
  overflow: hidden;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width: 100vw;
  height: 100vh;
}
</style>
