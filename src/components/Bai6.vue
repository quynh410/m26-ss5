<template>
  <div>
    <h3>Các số thỏa mãn điều kiện:</h3>
    <ul>
      <li v-for="(num, index) in filteredNumbers" :key="index">{{ num }}</li>
    </ul>
  </div>
</template>

<script setup>
import { reactive, computed } from "vue";
const arr = reactive([5, 12, 15, 22, 9, 18, 25, 30, 7, 33]);

// lẻ, chia hết cho 3, và lớn hơn 10
const filteredNumbers = computed(() => {
  return arr.filter((num) => num % 2 !== 0 && num % 3 === 0 && num > 10);
});
</script>

<style scoped></style>
