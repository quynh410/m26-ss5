<template>
  <div>
    <br>
    <h3>Điều khiển hiển thị thông báo</h3>
    <button @click="showMessage">Hiển thị</button>
    <button @click="hideMessage">Ẩn</button>
    <p v-show="isVisible" class="message">
      Thông báo : <b>Welcome to Rikkei Academy</b>
    </p>
  </div>
</template>

<script setup>
import { ref } from "vue";

// Biến isVisible với giá trị mặc định là false
const isVisible = ref(false);

// Hàm để hiển thị thông báo
const showMessage = () => {
  isVisible.value = true;
};

// Hàm để ẩn thông báo
const hideMessage = () => {
  isVisible.value = false;
};
</script>

<style scoped></style>
