<template>
  <div>
    <div>
      <button @click="sortAscending">Tăng dần</button>
      <button @click="sortDescending">Giảm dần</button>
    </div>

    <ul>
      <li v-for="(num, index) in numbers" :key="index">{{ num }}</li>
    </ul>
  </div>
</template>

<script setup>
import { ref } from "vue";

// Mảng các số nguyên
const numbers = ref([5, 3, 8, 1, 4]);

// Hàm sắp xếp theo thứ tự tăng dần
const sortAscending = () => {
  numbers.value.sort((a, b) => a - b);
};

// Hàm sắp xếp theo thứ tự giảm dần
const sortDescending = () => {
  numbers.value.sort((a, b) => b - a);
};
</script>

<style scoped>


button {
  padding: 10px;
  margin-right: 10px;
  border: 1px solid black;
  background-color: white;
  cursor: pointer;
}

button:hover {
  background-color: lightgray;
}
</style>
