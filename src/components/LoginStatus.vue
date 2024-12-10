<template>
  <div class="container mt-5">
    <h1 class="mb-4">Login Status</h1>
    <!-- Sectie voor ingelogde gebruikers -->
    <div v-if="isloggedin" class="logged-in">
      <p>Welkom terug, {{ username }}!</p>
      <button @click="logout" class="btn btn-danger">Uitloggen</button>
    </div>
    <!-- Sectie voor niet-ingelogde gebruikers -->
    <div v-else class="logged-out">
      <input
          v-model="username"
          type="text"
          class="form-control mb-3"
          placeholder="Voer gebruikersnaam in"
      />
      <button @click="login" class="btn btn-primary">Inloggen</button>
    </div>
  </div>
</template>

<script>
import {ref} from "vue";

export default {
  setup() {
    const username = ref('');
    const isloggedin = ref(false)

    const login = () => {
      isloggedin.value = true
    }

    const logout = () => {
      isloggedin.value = false
    }

    return {username, isloggedin, logout, login}
  }
};
</script>

<style scoped>
/* Stijlen voor een nette layout */
.container {
  max-width: 400px;
}
.logged-in {
  text-align: center;
}
.logged-out input {
  text-align: center;
}
</style>