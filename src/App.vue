<template>
  <div id="app">
    <TwoLists msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import TwoLists from './components/Two-lists.vue'

export default {
  name: 'app',
  components: {
    TwoLists
  }
}
</script>

<style>
body {
  background: rgb(231, 231, 231);
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  padding: 4em; 
}
</style>
