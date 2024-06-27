<template>
  <div>

    <div class="heading">
      CoffeeShop
    </div>

    <div class="parallax-container">
    
      <div>
        <img src="../assets/images/cover.png" class="cover">
      </div>

      <div>
        <img src="../assets/images/cup.png" class="cup" ref="cup">
      </div>

    </div>
</div>
  
</template>

<script>
export default {
  mounted() {
    document.addEventListener('scroll', this.handleScroll);
  },
  beforeUnmount() {
    // window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll() {
      console.log('pidor');
      const parallax = this.$refs.cup;
      if (parallax) {
        const scrollPosition = window.pageYOffset;
        parallax.style.transform = `translateY(${scrollPosition * 0.25}px)`;
        console.log(scrollPosition)
      }
    },
  },
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

  .parallax-container {
  position: relative;
  height: 100vh;
  overflow: hidden;
}

.parallax {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.parallax img {
  width: 100%;
  height: auto;
}

.content {
  position: relative;
  z-index: 1;
  padding: 20px;
  color: white;
}

</style>
