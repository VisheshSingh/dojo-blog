<template>
  <div class="home">
    <h1>Home</h1>
    <div class="ref-reactive">
      <div>
        <h2>Refs</h2>
        <p>{{ ninjaOne.name }}-{{ ninjaOne.age }}</p>
        <button @click="updateNinjaOne">Update Ref</button>
      </div>
      <div>
        <h2>Reactive</h2>
        <p>{{ ninjaTwo.name }}-{{ ninjaTwo.age }}</p>
        <button @click="updateNinjaTwo">Update Reactive</button>
      </div>
    </div>
  </div>
</template>

<script>
import { reactive, ref } from 'vue';
export default {
  name: 'Home',
  setup() {
    let ninjaOne = ref({ name: 'Peter', age: 19 });
    let ninjaTwo = reactive({ name: 'Miles', age: 17 });

    let updateNinjaOne = () => {
      ninjaOne.value.name = 'Mario';
      ninjaOne.value.age = 29;
    };
    let updateNinjaTwo = () => {
      ninjaTwo.name = 'Luigi';
      ninjaTwo.age = 28;
    };

    return { updateNinjaOne, updateNinjaTwo, ninjaOne, ninjaTwo };
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
