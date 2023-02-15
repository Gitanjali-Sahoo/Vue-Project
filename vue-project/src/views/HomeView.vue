<script setup>
import HeroImage from "../components/HeroImage.vue";
import Cards from "../components/Cards.vue";
import Fetch from "../components/Fetch.vue";
// import ImageSlider from '../components/ImageSlider.vue'
import Footer from "../components/Footer.vue";
</script>

<template>
  <HeroImage />

  <Cards />
  <Fetch />
  <!-- <div id="slider-app">
        <ImageSlider />
    </div> -->

  <div id="footer">
    <Footer />
  </div>
</template>
<script>
// export default {
// components: { ImageSlider },

// }
</script>

<style scoped>
/* #slider-app {
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;

        justify-content: center;
    } */
#footer {
  background-color: rgb(225, 220, 197);
  padding: 20px;
  position: sticky;
}
</style>
