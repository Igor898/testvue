<template>
  <div class="container">
    <Dropdown :options="options" v-model="selectedOption" />
    <Button label="Добавить ID" @click="addId" :disabled="selectedOption === 'Нет'" />
    <Display :ids="createdIds" />
  </div>
</template>

<script setup>
import { ref } from 'vue';
import Dropdown from './components/Dropdown.vue';
import Button from './components/Button.vue';
import Display from './components/Display.vue';

const options = ref(['Нет', 'User', 'Admin', 'Guest']);
const selectedOption = ref(options.value[0]);
const createdIds = ref([]);

const addId = () => {
  if (selectedOption.value !== 'Нет') {
    const newId = `${selectedOption.value}-${Date.now()}`;
    createdIds.value.push(newId);
  }
};
</script>

<style scoped>
.container {
  width: 300px;
  margin: auto;
  text-align: center;
  padding: 20px;
  background: white;
  border-radius: 10px;
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1);
}

.container > * {
  margin-bottom: 10px;
}
</style>