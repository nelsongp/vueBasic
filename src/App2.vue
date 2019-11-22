<template>
  <div id="app2">
    <h1>Revealing Text Components</h1>
    <GlitchText :text="this.revealString" :speed="100" />
    <GlitchText :text="this.revealString" :speed="200" />
    <GlitchText :text="this.revealString" :speed="300" />
    <button class="change" v-on:click="changeText">Change the text</button>
    <!--Gallery v-bind:title="galleryTitle"></Gallery-->
  </div>
</template>

<script>
import GlitchText from "./components/GlitchText";
export default {
  name: "app",
  components: {
    GlitchText
  },
  data() {
    return {
      revealString: "Berlin, Germany, 1989"
    };
  },
  methods: {
    changeText() {
      this.revealString = "Washington, United States, 1963";
    }
  }
};
</script>
<!--script>
import Gallery from "./components/Gallery.vue";

export default {
  name: "app",
  components: {
    Gallery
  },
  data() {
    return {
      galleryTitle: "Photography Gallery"
    };
  }
};
</script-->