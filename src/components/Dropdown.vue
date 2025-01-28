<template>
  <div class="dropdown">
    <select v-model="selectedValue" @change="emitSelection">
      <option v-for="option in options" :key="option" :value="option">
        {{ option }}
      </option>
    </select>
  </div>
</template>

<script setup>
import { defineProps, defineEmits, ref } from "vue";

const props = defineProps({
  options: Array,
});

const selectedValue = ref(props.options[0]);
const emit = defineEmits(["update:modelValue"]);

const emitSelection = () => {
  emit("update:modelValue", selectedValue.value);
};
</script>

<style scoped>
.dropdown select {
  padding: 10px;
  border-radius: 5px;
  border: 1px solid #ccc;
  background-color: white;
  cursor: pointer;
}
</style>
