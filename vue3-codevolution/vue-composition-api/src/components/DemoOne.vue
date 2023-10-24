<template>
  <div>{{ name }}</div>
</template>

<script>
import { ref } from 'vue';
export default {
  name: "DemoOne",
  setup() {
    const name = ref('Vishwas');

    setTimeout(() => {
        name.value = 'Codevolution'
        console.log(name);
    }, 2000);

    return {
        name
    }
  }
};
</script>

<style scoped>
</style>