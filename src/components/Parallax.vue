<template>
  <div class="heading">
    CoffeeShop
  </div>
  <div>
    <img src="../assets/images/cover.png" class="cover">
  </div>
  <div>
    <img src="../assets/images/cup.png" class="cup">
  </div>
</template>

<script>
export default {
  name: 'MainPage',
  props: {
    msg: String
  }
}
</script>

<style scoped>
  .heading {
    display: flex;
    justify-content: center;
    font-family: Arial, Helvetica, sans-serif;
    font-size: 100px;
    margin-bottom: 10px
  }

  .cover {
    height: 100px;
    margin-bottom: -5px;
  }

  .cup {
    width: 450px;
    margin-right: 23px;
  }

  .navigation-panel {
    display: flex;

  }

</style>
