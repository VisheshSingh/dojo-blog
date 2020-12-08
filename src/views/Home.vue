<template>
  <div class="home">
    <h1>Home</h1>
    <input type="text" v-model="search" />
    <p>Searching for - {{ search }}</p>
    <div v-for="name of matchingNames" :key="name">
      {{ name }}
    </div>
  </div>
</template>

<script>
import { ref, computed } from 'vue';
export default {
  name: 'Home',
  setup() {
    let search = ref('');
    let names = ref(['mario', 'luigi', 'peach', 'koopa', 'bowser', 'toads']);

    const matchingNames = computed(() => {
      return names.value.filter((name) => name.includes(search.value));
    });

    return { names, matchingNames, search };
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
