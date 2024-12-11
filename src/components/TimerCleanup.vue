<template>
  <div class="container mt-5">
    <h2>Timer Cleanup</h2>
    <p>Timer: {{ count }}</p>
    <p>Status: <strong>{{ timer ? 'Actief' : 'Gestopt' }}</strong></p>
    <button class="btn btn-danger"
            @click="clearTimer" :disabled="!timer">Stop Timer</button>
    <button class="btn btn-success"
            @click="restartTimer" :disabled="timer">Start Timer</button>
  </div>
</template>
<script>
import { ref, onMounted, onBeforeUnmount } from 'vue';
export default {
  setup() {
    const count = ref(0);
    const timer = ref(null);
    const startTimer = () => {
      timer.value = setInterval(() => {
        count.value++;
      }, 1000);
    };
    const clearTimer = () => {
      clearInterval(timer.value);
      timer.value = null;
    };
    const restartTimer = () => {
      startTimer();
    };
    // Lifecycle hooks
    onMounted(() => {
      startTimer();
    });
    onBeforeUnmount(() => {
      console.log('Timer wordt opgeruimd.');
      clearTimer();
    });
    return {
      count,
      timer,
      startTimer,
      clearTimer,
      restartTimer,
    };
  },
};
</script>