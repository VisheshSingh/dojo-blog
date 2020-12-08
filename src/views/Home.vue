<template>
  <div class="home">
    Composition API
    <p>My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">Click me</button>
  </div>
</template>

<script>
export default {
  name: 'Home',
  setup() {
    let name = 'v-boy';
    let age = 30;

    let handleClick = () => {
      console.log('hi');
    };

    return { name, age, handleClick };
  },
};
</script>
