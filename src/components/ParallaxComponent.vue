<template>
  <div class="parallax-container">
    <div class="heading" ref="heading">
        CoffeeShop
    </div>

    <div class="cover-container">
      <img src="../assets/images/cover.png" class="cover" ref="cover">
      <div class="vapour-container" ref="vapourContainer">
        <div class="vapour" ref="vapour">
          <span style="--v:1;"></span>
          <span style="--v:2;"></span>
          <span style="--v:5;"></span>
          <span style="--v:4;"></span>
          <span style="--v:6;"></span>
          <span style="--v:19;"></span>
          <span style="--v:7;"></span>
          <span style="--v:8;"></span>
          <span style="--v:9;"></span>
          <span style="--v:10;"></span>
          <span style="--v:11;"></span>
          <span style="--v:18;"></span>
        </div>
      </div>
    </div>

    <div class="cup-container">
      <img src="../assets/images/cup.png" class="cup" ref="cup">
    </div>         
  </div>
</template>

<script>
export default {
  mounted() {
    document.addEventListener('scroll', this.handleScroll);
  },
  beforeUnmount() {
    document.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll() {
      const scrollPosition = window.pageYOffset;
      const screenHeight = window.innerHeight;

      console.log('Scroll position:', scrollPosition);

      // Параллакс для элементов
      const parallaxCup = this.$refs.cup;
      const parallaxCover = this.$refs.cover;
      const parallaxHeading = this.$refs.heading;
      const parallaxVapour = this.$refs.vapour;
      const vapourContainer = this.$refs.vapourContainer
      
      if (scrollPosition < screenHeight) {
        
        parallaxHeading.style.transform = `translateY(${scrollPosition}px)`;
        parallaxCover.style.transform = `translateY(${scrollPosition * 0.8}px)`;
        parallaxVapour.style.transform = `translateY(${scrollPosition * 1.3}px)`;
        parallaxCup.style.transform = `translateY(${scrollPosition * 1.3}px)`;
        vapourContainer.style.transform = `translateY(${scrollPosition * 1.3}px)`;
      
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
    font-size: 100px;
    font-weight: 700;
    margin-bottom: 50px;
  }

  .parallax-container {
    height: 1000px;
    position: relative;
  }



  .cover {
    height: 100px;
  }

  .cup-container {
    position: relative;
  }

  .cup {
    width: 450px;
    margin-right: 23px;
    z-index: 2;
  }
  
  .cover-container {
    z-index: 2;
    height: 100px;
    position: relative;
  }

  .vapour-container {
    position: absolute;
    top: 0;
    z-index: 1;
    width: 100%;
    height: 100px;
    overflow: hidden;
  }

  .vapour {
    position: absolute;
    top: 0;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    z-index: 1;
    justify-content: center;
    
  }

  .vapour span {
    position: relative;
    display: block;
    min-width: 8px;
    height: 120px;
    background: #fff;
    border-radius: 50%;
    animation: animate 5s linear infinite;
    opacity: 0;
    filter: blur(10px);
    animation-delay: calc(var(--v) * -0.5s);
  }

  @keyframes animate {
    0% {
      transform: translateY(0) scaleX(1);
      opacity: 0;
    }
    15% {
      opacity: 1;
    }
    50% {
      transform: translateY(-150px) scaleX(5);
    }
    95% {
      opacity: 0;
    }
    100% {
      transform: translateY(-300px) scaleX(10);
    }
  }
</style>
