<template>
    <div class="hero-image" :style="heroImgStyle">
        <div class="hero-text">
            <h1>{{title}}</h1>
        </div>
    </div>
</template>

<script>
import Vue from "vue";
import Cookies from "js-cookie";

export default {
  name: "HeroImage",
  components: {},
  props: {
    title: {
      type: String,
      required: false,
      default: "Titlu default",
    },
    height: {
      type: String,
      required: false,
      default: "400",
    },
    imgSrc: {
      type: String,
      required: false,
      default: "http://test.balkanfun.mk/wp-content/uploads/2017/09/galerija.jpg",
    },
  },
  computed: {
    heroImgStyle() {
      return (
        'background-image: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url("' +
        this.imgSrc +
        '"); height: ' +
        this.height +
        "px;"
      );
    },
  },
};
</script>

<style type="text/css" lang="scss">
.hero-image {
  /* Use "linear-gradient" to add a darken background effect to the image (photographer.jpg). This will make the text easier to read */
  /* Set a specific height */
  height: 300px;

  /* Position and center the image to scale nicely on all screens */
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  position: relative;
}

/* Place text in the middle of the image */
.hero-text {
  text-align: center;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  color: white;
}
</style>

