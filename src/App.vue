<template>
  <div id="app">
    <Core />
  </div>
</template>

<script>
import Core from './components/Core.vue'

export default {
  name: 'App',
  components: {
    Core
  }
}
</script>

<style>
body {
  background-color: rgb(24, 26, 27);
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
