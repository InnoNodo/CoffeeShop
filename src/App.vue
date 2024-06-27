<template>
  <body>
    <div>
      <ParallaxComponent />
    </div>
  </body>
</template>

<script>
import ParallaxComponent from './components/ParallaxComponent.vue';

export default {
  name: 'App',
  components: {
    ParallaxComponent
  }
};

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
