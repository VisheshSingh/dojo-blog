<template>
  <div class="home">
    Composition API
    <p>My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">Click me</button>
    <button @click="age++">Increment age</button><br />
    <input type="text" v-model="name" />
  </div>
</template>

<script>
import { ref } from 'vue';
export default {
  name: 'Home',
  setup() {
    let name = ref('v-boy');
    let age = ref(30);

    let handleClick = () => {
      name.value = 'Peter';
      age.value = 29;
    };

    return { name, age, handleClick };
  },
};
</script>
