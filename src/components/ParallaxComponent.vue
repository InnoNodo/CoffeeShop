<template>
  <div>

    <div class="heading" ref="heading">
      CoffeeShop
    </div>

    <div class="parallax-container">
    
      <div>
        <img src="../assets/images/cover.png" class="cover" ref="cover">
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
      const parallaxCup = this.$refs.cup;
      const parallaxCover = this.$refs.cover;
      const parallaxHeading = this.$refs.heading;
      if (parallaxCover) {
        const scrollPosition = window.pageYOffset;
        parallaxCup.style.transform = `translateY(${scrollPosition * 1.3}px)`;
        parallaxCover.style.transform = `translateY(${scrollPosition * 0.8}px)`
        parallaxHeading.style.transform = `translateY(${scrollPosition}px)`
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
    font-family: "Cooper BT", serif;
    font-size: 75px;
    font-weight: 700;
    font-size: 100px;
    margin-bottom: 10px
  }

  .cover {
    height: 100px;
    margin-bottom: -105px;
  }

  .cup {
    margin-top: 100px;
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
