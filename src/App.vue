<template>
  <body>
    <Parallax msg="Welcome to Your Vue.js App"/>
  </body>
</template>

<script>
import Parallax from './components/Parallax.vue';

export default {
  name: 'App',
  components: {
    Parallax
  }
}
</script>

<style>
body {
  background-color: #ffda91;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
