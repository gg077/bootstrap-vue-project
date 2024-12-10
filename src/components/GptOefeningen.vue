<template>
  <div class="container mt-5 text-center">
    <h2>Countdown Timer</h2>
    <p>Tijd: <strong>{{ timer }}</strong></p>
    <button @click="startCountdown" class="btn btn-success">Start</button>
  </div>
</template>
<script>
import { ref } from 'vue';
export default {
  setup() {
    const timer = ref(10);
    let interval;
    const startCountdown = () => {
      interval = setInterval(() => {
        if (timer.value > 0) {
          timer.value--;
        } else {
          clearInterval(interval);
        }
      }, 1000);
    };
    return { timer, startCountdown };
  },
};
</script>