<template>
  <div>
    <h1 v-if="template">Condition Rendering</h1>
    <h1 v-else>Ẩn phần tử</h1>
    <button @click="handleClick">Toggle</button>

    <p>Tuổi hiện tại: {{ age }}</p>
    <button @click="incrementAge">Tăng tuổi</button>
    <button @click="decrementAge">Giảm tuổi</button>
    <p v-if="age >= 18">Đủ tuổi thi</p>
    <p v-else>Chưa đủ tuổi thi</p>
    <!--  -->
<h1>Quyen cua ban la : {{role}}</h1>
    <p v-if="role === 'admin'">Admin</p>
    <p v-else-if="role === 'user'">User</p>
    <p v-else-if="role === 'guest'">Guest</p>
    <p v-else>Bạn có quyền: Khác</p>
    <!--  -->
    <button @click="setRole('admin')">Chọn Admin</button>
    <button @click="setRole('user')">Chọn User</button>
    <button @click="setRole('edit')">Chọn Edit</button>
    <button @click="setRole('other')">Chọn Other</button>
  </div>
</template>

<script setup>
import { ref } from "vue";

const template = ref(false);
const age = ref(0);
const role = ref("admin")

const handleClick = () => {
  template.value = !template.value;
};
const incrementAge = () => {
  age.value++;
};
const decrementAge = () => {
  age.value--;
};

const setRole = (newRole) => {
  role.value = newRole;
};
// tạo  1 biến có giá trị có thể là admin user và edit , other 
// kiểm tra điểu kiền và render tên quyền tương ứng 



</script>

<style></style>
