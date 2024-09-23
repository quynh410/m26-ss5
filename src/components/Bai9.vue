<template>
  <div>
    <p>Giới tính: {{ gender }}</p>
    <button @click="randomGender">Random gender</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';

// Mảng chứa các giới tính
const genders = ['Nam', 'Nữ', 'Khác'];

// Biến phản ứng để lưu giới tính hiện tại (mặc định là 'Nam')
const gender = ref('Nam');

// Hàm để chọn giới tính ngẫu nhiên
const randomGender = () => {
  const randomIndex = Math.floor(Math.random() * genders.length);
  gender.value = genders[randomIndex];
};
</script>

<style scoped>


button:hover {
  background-color: lightgray;
}
</style>
