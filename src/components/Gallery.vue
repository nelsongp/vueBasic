<template>
  <div class="gallery">
    <h2>{{title}}</h2>
    <div v-for="(image, i) in images" :key="i">
      <img v-bind:src="require('../assets/' + image.imageName)" alt />
      <Photographer :name="image.photographerName" :link="image.photographerLink" />
    </div>
  </div>
</template>

<script>
import Photographer from "./Photographer";
export default {
  props: ["title"],
  components: {
    Photographer
  },
  data() {
    return {
      images: [
        {
          imageName: "logo.png",
          url: "http://www.google.com",
          photographerLink: "http://www.outlook.com",
          photographerName: "Hola1"
        },
        {
          imageName: "logo.png",
          url: "http://www.google.com",
          photographerLink: "http://www.outlook.com",
          photographerName: "Hola2"
        }
      ]
    };
  }
};
</script>
