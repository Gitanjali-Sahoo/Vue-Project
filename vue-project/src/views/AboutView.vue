<template>
    
  <div id="slider-app">
    <ImageSlider />
  </div>
  <!-- <div id="footer">
    <Footer />
  </div> -->

</template>
<script setup>
import ImageSlider from "../components/ImageSlider.vue";
// import Footer from "../components/Footer.vue";
</script>
<style scoped>
#slider-app {
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;

        justify-content: center;

    }
    #footer {
  background-color: rgb(225, 220, 197);
  padding: 20px;
  width: 100%;
}</style>
