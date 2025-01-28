<template>
  <button @click="handleClick" class="button">
    {{ label }}
  </button>
</template>

<script setup>
import { defineProps, defineEmits } from 'vue';

defineProps({
  label: String,
});

const emit = defineEmits(['click']);

const handleClick = () => {
  emit('click');
};
</script>

<style scoped>
.button {
  padding: 10px 20px;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background 0.3s;
}

.button:hover {
  background-color: #0056b3;
}
</style>
