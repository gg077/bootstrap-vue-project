<template>
  <div class="container mt-5">
    <h1 class="mb-4">Temperatuur Converter</h1>
    <!-- Input voor Celsius -->
    <div class="mb-3">
      <label for="celsiusInput" class="form-label">Temperatuur in
        Celsius:</label>
      <input
          v-model="celsius"
          id="celsiusInput"
          type="number"
          class="form-control"
          placeholder="Voer Celsius in"
      />
    </div>
    <!-- Output voor Fahrenheit -->
    <p class="mt-3">
      De temperatuur in Fahrenheit: <strong>[{{fahrenheit}}]</strong>
    </p>
  </div>
</template>

<script>
import { ref, computed } from "vue";

export default {
  setup() {
    const celsius = ref('');
    const fahrenheit = computed(() => (celsius.value * 9) / 5 + 32);
    return { celsius, fahrenheit };

  }
};
</script>


<style scoped>
/* Stijlen voor een nette layout */
.container {
  max-width: 400px;
}
</style>