<template>
  <div class="container mt-5">
    <h2>API Data Fetch</h2>
    <ul v-if="items.length">
      <li v-for="item in items" :key="item.id">{{ item.title }}</li>
    </ul>
    <p v-else>Laden...</p>
  </div>
</template>
<script>
import { ref, onMounted } from 'vue';
import axios from 'axios';
export default {
  setup() {
    const items = ref([]);
    const fetchItems = async () => {
      try {
        const response = await
            axios.get('https://jsonplaceholder.typicode.com/posts');
        items.value = response.data.slice(0, 10);
      } catch (error) {
        console.error('API-fout:', error);
      }
    };
    onMounted(() => {
      fetchItems();
    });
    return {
      items,
    };
  },
};
</script>