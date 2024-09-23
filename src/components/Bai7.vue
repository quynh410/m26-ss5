<template>
  <div class="button-group">
    <button
      v-for="num in 3"
      :key="num"
      :class="['button', { active: activeIndex === num }]"
      @click="handleClick(num)"
    >
      Button {{ num }}
    </button>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const activeIndex = ref(1);
const handleClick = (index) => {
  activeIndex.value = index;
};
</script>

<style scoped>
.button-group {
  display: flex;
  gap: 10px;
}

.button {
  padding: 10px 20px;
  border: 2px solid black;
  background-color: white;
  color: black;
  font-size: 16px;
  cursor: pointer;
}

.button.active {
  background-color: red;
  color: white;
}
</style>
