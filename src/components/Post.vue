<template>
  <div class="single-posts">
    <h1>{{currentPost.title}}</h1>
    <img :src="'/'+currentPost.image" />
    <p>
      <a :href="currentPost.photographer">Photo Credits</a>
    </p>
    <p>{{currentPost.description}}</p>
    <div v-if="currentPost.link">
      <a :href="currentPost.link">Read More</a>
    </div>
  </div>
</template>

<script>
import posts from "@/data.js";
export default {
  name: "Post",
  data() {
    return { posts, currentPost: {} };
  },
  created() {
    const self = this;
    this.currentPost = post.filter(item => {
      if (item.id == self.$route.params.id) {
        return item;
      }
    })[0];
  }
};
</script>