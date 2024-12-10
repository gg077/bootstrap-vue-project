<template>
  <div class="container mt-5">
    <h1>Checklist</h1>
    <div class="input-group mb-3">
      <input
          type="text"
          class="form-control"
          v-model="newTask"
          placeholder="Voeg een nieuwe taak toe" />
      <button class="btn btn-success" @click="addTask">Toevoegen</button>
    </div>
    <ul class="list-group">
      <li
          v-for="(task, index) in tasks"
          :key="index"
          class="list-group-item d-flex justify-content-between align-items-center">
        <div>
          <input
              type="checkbox"
              class="form-check-input me-2"
              v-model="task.completed" />
          <span :class="{ 'text-decoration-line-through': task.completed }">{{ task.name }}</span>
        </div>
        <button class="btn btn-danger btn-sm" @click="removeTask(index)">
          Verwijderen
        </button>
      </li>
    </ul>
  </div>
</template>

<script>
import { ref } from 'vue';
export default {
  setup() {
    const tasks = ref([]);
    const newTask = ref('');
    const addTask = () => {
      tasks.value.push({ name: newTask.value.trim(), completed: false });
      newTask.value = '';

    };
    const removeTask = (index) => {
      tasks.value.splice(index, 1);
    };
    return { tasks, newTask, addTask, removeTask };
  }
};
</script>

<style scoped>
.text-decoration-line-through {
  text-decoration: line-through;
}
</style>