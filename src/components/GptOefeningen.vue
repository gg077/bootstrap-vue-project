<template>
  <div class="container mt-5">
    <h2>Mijn Lijst</h2>
    <input v-model="listitem" type="text" class="form-control mb-2" placeholder="Voeg een item toe..."/>
    <button @click="voegtoe" class="btn btn-success mb-3">Toevoegen</button>
    <ul class="list-group">
      <li v-for="(item, index) in items" :key="index" class="list-group-item">{{item}}</li>
    </ul>
  </div>
</template>
<script>
import { ref } from 'vue';
export default {
  setup() {
    const listitem = ref('');
    const items = ref([]);
    const voegtoe = () =>{
      items.value.push(listitem.value.trim());
    }
    return {listitem, items, voegtoe}
  },
};
</script>
