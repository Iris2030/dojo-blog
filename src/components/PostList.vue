<template>
  <div>
    <div class="post-list"></div>
    <div v-for="post in posts" :key="post.id">
      <SinglePost :post="post"/>
    </div>
  </div>
</template>

<script>
import SinglePost from "./SinglePost.vue";
export default {
  components: {
    SinglePost,
  },
  props: ["posts"],
  setup(props) {
    console.log(props.posts);
  },
};
</script>

<style lang="scss" scoped>
</style>