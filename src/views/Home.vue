<template>
  <div class="home">
    <h1>Home</h1>
    <div v-if="error">{{ error }}</div>
    <div v-if="posts.length">
      <PostList :posts="posts" />
    </div>
    <div v-else>
      Loading...
    </div>
  </div>
</template>

<script>
import PostList from '../components/PostList';
import { ref } from 'vue';

export default {
  name: 'Home',
  components: { PostList },
  setup() {
    let posts = ref([]);
    const error = ref(null);

    const load = async () => {
      try {
        const res = await fetch(`http://localhost:3000/posts`);
        if (!res.ok) {
          throw new Error('no data available');
        }
        const data = await res.json();
        posts.value = data;
        console.log(posts.value);
      } catch (err) {
        error.value = err.message;
        console.log(error.value);
      }
    };

    load();

    return { posts, error };
  },
};
</script>

<style>
.ref-reactive {
  max-width: 300px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>
