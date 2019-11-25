<template>
  <div class="Home">
    <h1>Home</h1>
    <p>Items in the Vue eco system:</p>
    <div class="post-grid">
      <div class="grid-item" v-for="post in posts" :key="post.id">
        <router-link :to="'/post/'+post.id">
          <div class="grid-item">
            <h2>{{post.title}}</h2>
            <img :src="post.image" />
          </div>
        </router-link>
      </div>
    </div>
  </div>
</template>
<script>
import posts from "@/data.js";
export default {
  name: "home",
  components: {},
  data() {
    return {};
  }
};
</script>