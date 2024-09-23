<template>
  <div>
    <h1 v-if="template">Rikkei academy</h1>
    <button @click="handleClick">Hien</button>
  </div>
</template>

<script setup>
import { ref } from "vue";

const template = ref(false);
const handleClick = () => {
  template.value = !template.value;
};
</script>

<style></style>
