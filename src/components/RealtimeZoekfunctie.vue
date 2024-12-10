<template>
  <div class="container mt-5">
    <h2>Zoekfunctie</h2>
    <input
        v-model="zoek"
        type="text"
        class="form-control mb-3"
        placeholder="Zoek een naam..."
    />
    <ul class="list-group">
      <!-- Door de zoekterm gefilterde lijst -->
      <li v-for="(naam, index) in gefilterdeNamen" :key="index" class="list-group-item">
        {{ naam }}
      </li>
    </ul>
  </div>
</template>

<script>
import { ref, computed } from "vue";

export default {
  setup() {
    // De lijst van namen
    const namen = ref([
      "Jan", "Pieter", "Klaas", "Anna", "Maria", "Joris", "Sophie", "Lotte"
    ]);

    // De zoekterm van de gebruiker
    const zoek = ref("");

    // Gefilterde lijst van namen op basis van de zoekterm
    const gefilterdeNamen = computed(() => {
      return namen.value.filter(naam =>
          naam.toLowerCase().includes(zoek.value.toLowerCase())
      );
    });

    return { zoek, gefilterdeNamen };
  }
};
</script>
