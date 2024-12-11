<template>
  <div class="container mt-5">
    <h2>Before Update</h2>
    <p>Huidige waarde: {{ count }}</p>
    <p>Vorige waarde: {{ previousCount }}</p>
    <button class="btn btn-primary" @click="increment">Verhoog</button>
  </div>
</template>
<script>
import { ref, watch } from 'vue';
export default {
  setup() {
    const count = ref(0);
    const previousCount = ref(null);
    const increment = () => {
      count.value++;
    };
    72
// Watcher om `beforeUpdate` na te bootsen
    watch(count, (newVal, oldVal) => {
      previousCount.value = oldVal;
    });
    return {
      count,
      previousCount,
      increment,
    };
  },
};
</script>