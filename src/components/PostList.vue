<template>
  <div v-for="post of posts" :key="post.id">
    <SinglePost :post="post" />
  </div>
</template>

<script>
import SinglePost from './SinglePost';

export default {
  name: 'PostList',
  props: ['posts'],
  components: { SinglePost },
  setup(props) {
    console.log(props.posts);
  },
};
</script>

<style></style>
