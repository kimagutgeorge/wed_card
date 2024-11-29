<template>
  <div class="wrapper position-relative w-100">
    <div class="nav-bar row position-absolute">
      <!-- <img src="../assets/g6.png"> -->
    </div>
    <div class="container-bg position-absolute w-100">
      <!-- carousel -->
     <div class="comment-wrapper position-absolute">
      <div class="carousel">
        <div
          class="carousel-inner"
          :style="{ transform: `translateX(-${currentIndex * 100}%)` }"
        >
          <div v-for="(image, index) in images" :key="index" class="carousel-item">
            <img :src="image" alt="Carousel image" />
          </div>
        </div>
        <button class="carousel-button prev" @click="prevSlide">❮</button>
        <button class="carousel-button next" @click="nextSlide">❯</button>
      </div>
    </div>
    </div>
  </div>
  <div class="carousel-message">
    🎉 Congratulations, Lewis! Wishing you and your partner a lifetime of love and happiness 💍💐
  </div>
  
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      images: [
        "images/1.png",
        "images/2.png",
        "images/3.png",
        "images/4.png"
      ],
      currentIndex: 0,
      autoplay: null,
    };
  },
  methods: {
    nextSlide() {
      this.currentIndex =
        (this.currentIndex + 1) % this.images.length;
    },
    prevSlide() {
      this.currentIndex =
        (this.currentIndex - 1 + this.images.length) % this.images.length;
    },
    startAutoplay() {
      this.autoplay = setInterval(() => {
        this.nextSlide();
      }, 3000);
    },
    stopAutoplay() {
      clearInterval(this.autoplay);
    },
  },
  mounted() {
    this.startAutoplay();
  },
  beforeUnmount() {
    this.stopAutoplay();
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
*{
  margin:0px !important;
  padding:0px !important;
}
.wrapper{
  width: 100% !important;
}
.wrapper .nav-bar{
  top:20px !important;
  left:20px !important;
  z-index: 2;
}
.wrapper .container-bg{
  height: 90vh !important;
}

.carousel {
  top:5vh !important;
  position: relative;
  width: 90%;
  left:5% !important;
  margin: auto;
  overflow: hidden;
}

.carousel-inner {
  display: flex;
  transition: transform 0.5s ease-in-out;
}

.carousel-item {
  min-width: 100%;
  max-width: 100%;
  display: flex;
  flex-direction: row;
  justify-content: center;
  flex-shrink: 0;
}

.carousel-item img {
  width: auto;
  max-height: 90vh;
  display: block;
}

.carousel-button {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background-color: rgba(0, 0, 0, 0.5);
  color: white;
  border: none;
  border-radius: 50%;
  cursor: pointer;
  width: 40px;
  height: 40px;
  font-size: 18px;
  z-index: 1;
}

.carousel-button.prev {
  left: 10px;
}

.carousel-button.next {
  right: 10px;
}
.nav-bar img{
  width:10%;
}
.carousel-message {
  margin-top: 50px !important;
  padding: 15px 15px !important;
  text-align: center;
  font-size: 24px;
  color: #393c6d;
  border-radius: 10px;
  font-family: "Edu AU VIC WA NT Pre", cursive;
  font-weight: 500;
  display: none;
}
@media screen and (max-width : 1067px) {
  .carousel-message{
    display: block;
  }
  .carousel {
    top:0vh !important;
    position: relative;
    left:0% !important;
    width: 100%;
  }
  .carousel-item {
    min-width: 100%;
  }
  
  .carousel-item img {
    width: 100%;
    height: auto;
    display: block;
  }
  .wrapper .container-bg{
    height: fit-content !important;
  }
}
</style>
