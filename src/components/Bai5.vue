<template>
  <div>
    <h3>Các số chẵn trong mảng: {{ arr }}</h3>
    <ul v-for="(num, index) in evenNumbers" :key="index">
      <li>{{ num }}</li>
    </ul>
  </div>
</template>

<script setup>
import { reactive, computed } from "vue";

const arr = reactive([1, 2, 3, 4, 5, 6, 7, 8, 9, 10]);

const evenNumbers = computed(() => {
  return arr.filter((num) => num % 2 === 0);
});
</script>

<style scoped></style>
