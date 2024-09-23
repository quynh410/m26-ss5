<template>
  <div>
    <button @click="addRandomNumber">Random number</button>
    <p>{{ numbers }}</p>
  </div>
</template>

<script setup>
import { ref } from 'vue';

// Mảng rỗng để chứa các số nguyên
const numbers = ref([]);

// Hàm để tạo và thêm số ngẫu nhiên vào mảng
const addRandomNumber = () => {
  const randomNum = Math.floor(Math.random() * 10) + 1; // Tạo số ngẫu nhiên từ 1 đến 10
  numbers.value.push(randomNum); // Thêm số vào mảng
};
</script>

<style scoped>
button {
  padding: 10px 20px;
  border: 1px solid black;
  background-color: white;
  cursor: pointer;
}

button:hover {
  background-color: lightgray;
}

p {
  font-size: 18px;
  font-weight: bold;
  margin-top: 10px;
  color: black;
}
</style>
