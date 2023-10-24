<template>
  <h2>Child Component C</h2>
  <h3>Child Component C username - {{ userName }}</h3>
  <h3>Child Component C Composition username - {{ childUsername }}</h3>

  <h3>Child Component C count - {{ childCount }}</h3>
  <h3>Child Component C hero - {{ firstName }} {{ lastName }}</h3>

  <button @click="incrementCount">Increment Count from Child</button>
</template>

<script>
import { inject, toRefs } from "vue";
export default {
  name: "ChildC",
  setup() {
    const childUsername = inject("c_username", "Default username");
    const childCount = inject("c_count", 0);
    const childHero = inject("c_hero", {});
    const incrementCount = inject("incrementCount");

    return {
      childUsername,
      childCount,
      ...toRefs(childHero),
      incrementCount,
    };
  },
  inject: ["userName"],
};
</script>

<style scoped>
</style>