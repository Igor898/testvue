<template>
  <div class="display">
    <h3>Список ID:</h3>
    <ul>
      <li v-for="id in ids" :key="id">{{ id }}</li>
    </ul>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';

defineProps({
  ids: Array,
});
</script>

<style scoped>
.display {
  margin-top: 20px;
  padding: 10px;
  background-color: #f8f9fa;
  border-radius: 5px;
  border: 1px solid #ddd;
}

.display ul {
  list-style: none;
  padding: 0;
}

.display li {
  padding: 5px 0;
}
</style>
