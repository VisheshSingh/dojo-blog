<template>
  <div class="home">
    Composition API
    <p ref="paragraph">My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">Click me</button>
  </div>
</template>

<script>
import { ref } from 'vue';
export default {
  name: 'Home',
  setup() {
    let name = 'v-boy';
    let age = 30;
    let paragraph = ref(null);

    let handleClick = () => {
      console.log(paragraph, paragraph.value);
      paragraph.value.classList.add('test');
      paragraph.value.textContent = 'wohuuuu!!!';
    };

    return { name, age, handleClick, paragraph };
  },
};
</script>
