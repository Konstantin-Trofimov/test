<template>
  <div>
    <progressbar/>
    <hexagon/>
  </div>
</template>

<script>
import Progressbar from './components/Progressbar.vue'
import Hexagon from './components/Hexagon.vue'

export default {
  name: 'App',
  components: {
    Progressbar,
    Hexagon
  }
}
</script>

<style lang="scss">

* {
  margin: 0;
  padding: 0;
}

#app {
  font-family: monospace, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  // text-align: center;
  color: #2c3e50;
  
}
</style>
