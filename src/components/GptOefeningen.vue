<template>
  <div class="container mt-5">
    <h1>Custom Directive: v-focus</h1>
    <p>De input hieronder krijgt automatisch focus wanneer de pagina
      laadt:</p>
    <button v-copy="'Dit is de te kopiëren tekst'">Kopieer tekst</button>
  </div>
</template>
<script>
export default {
  name: 'App',
};
</script>
<style>
.container {
  max-width: 500px;
  margin: 50px auto;
}
</style>