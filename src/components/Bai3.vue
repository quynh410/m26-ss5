<template>
  <div>
    <h1>Quyen cua ban la : {{role}}</h1>
    <p v-if="role === 'admin'">Admin</p>
    <p v-else-if="role === 'user'">User</p>
    <p v-else-if="role === 'guest'">Guest</p>
    <p v-else>Bạn có quyền: Khác</p>
    <!--  -->
    <button @click="setRole('admin')">Chọn Admin</button>
    <button @click="setRole('user')">Chọn User</button>
    <button @click="setRole('edit')">Chọn Guest</button>
  </div>
</template>

<script setup>
import { ref } from "vue";

const role = ref("admin");

const setRole = (newRole) => {
  role.value = newRole;
};
</script>

<style></style>
