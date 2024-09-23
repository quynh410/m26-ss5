<template>
  <div>
    <button @click="handleClick" v-if="isShow">An</button>
    <button @click="handleClick" v-else>Hien</button>
  </div>
</template>

<script setup>
import { ref } from "vue";

const isShow = ref(true);

const handleClick = () => {
  isShow.value = !isShow.value;
};
</script>

<style></style>
