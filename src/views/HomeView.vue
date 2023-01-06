<template>
  <div class="home">
    <div v-if="error">{{ error }}</div>
    <div v-if="posts.length">
      <PostList v-if="showPosts" :posts="posts"/>
    </div>
    <div v-else>...loading</div>
<button @click="showPosts = !showPosts">Toggle posts</button>
<button @click="posts.pop()">Deleta a posts</button>
  </div>
</template>

<script>
import getPosts from '../composables/getPosts'
import PostList from '../components/PostList.vue'
import { ref } from 'vue'

export default {
  name: 'HomeView',
  components: {
    PostList,
  },

  setup(){
 
  const {posts, error, load} = getPosts()
  const showPosts = ref(true)

  load()

  return {posts, showPosts, error }
}
}
</script>
