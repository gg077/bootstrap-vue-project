<template>
  <div>
    <input v-model="name" type="text">
    <p>lengte van de naam: heeft {{namelengt}} charakters</p>
  </div>
</template>

<script>
import {ref, computed} from "vue";

export default {
  setup(){
    const name = ref('');
    const namelengt = computed(() => name.value.length)
    return {name, namelengt}
  }
}
</script>