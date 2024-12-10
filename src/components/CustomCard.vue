<template>
  <div class="card p-3">
    <div class="card-header bg-light">
      <slot name="header">standaard header</slot>
    </div>
    <div class="card-body text-danger">
      <slot>standaard inhoud</slot>
    </div>
  </div>
</template>

<script setup>
</script>