<template>
  <div class="home">
    <h1>Home</h1>
    <PostList :posts="posts" />
  </div>
</template>

<script>
import PostList from '../components/PostList';
import { ref } from 'vue';

export default {
  name: 'Home',
  components: { PostList },
  setup() {
    const posts = ref([
      { title: 'Top 5 css tips', body: 'lorem ipsum', id: 1 },
      { title: 'learn vue Composition API', body: 'lorem ipsum', id: 2 },
    ]);

    return { posts };
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
