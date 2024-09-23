<template>
  <div class="container">
    <div class="todo">
      <h3 class="heading">Danh sách công việc</h3>
      <form @submit.prevent="handleAddJob" class="header">
        <input v-model="inputValue" type="text" class="input" />
        <button class="button button-add">Add job</button>
      </form>

      <ul class="list-item">
        <li v-for="job in listJob" :key="job.id" class="item">
          <div class="left">
            <input type="checkbox" :checked="job.status" />
            <label :class="{ completed: job.status }"  :style="{ textDecoration : item.status ? 'line-through' : 'none'}">{{ job.name }}</label>
          </div>
          <div class="right">
            <button
              @click="handleDeleteJob(index)"
              class="button button-delete"
            >
              Delete
            </button>
          </div>
        </li>
      </ul>

      <footer class="footer">
        <p>Công việc hoàn thành:</p>
        <p>
          <b> {{ completedJobs }} </b> / <b> {{ listJob.length }} </b>
        </p>
      </footer>
    </div>
  </div>
</template>

<script setup>
import { reactive, ref, computed } from "vue";

const inputValue = ref("");

// List of jobs stored in local storage
const listJob = reactive(JSON.parse(localStorage.getItem("jobs") || "[]"));

// Function to add a new job
const handleAddJob = () => {
  // Validate input
  if (!inputValue.value) {
    alert("Tên công việc không được để trống");
    return;
  }

  // Check for duplicate job names
  const findJobByName = listJob.find((item) => item.name === inputValue.value);
  if (findJobByName) {
    alert(`Tên công việc "${inputValue.value}" đã tồn tại!`);
    return;
  }

// them cong viec vaof mang
  listJob.push({
    id: Math.ceil(Math.random() * 1000),
    name: inputValue.value,
    status: false, 
  });

  // len local storage
  localStorage.setItem("jobs", JSON.stringify(listJob));

  // Reset input ve mang rong
  inputValue.value = "";
};

// Function to delete a job
const handleDeleteJob = (index) => {
  listJob.splice(index, 1);
  localStorage.setItem("jobs", JSON.stringify(listJob));
};

// Computed property to get the number of completed jobs
const completedJobs = computed(
  () => listJob.filter((job) => job.status).length
);
</script>

<style scoped>
.container {
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

.heading {
  text-align: center;
  font-size: 24px;
  padding-bottom: 24px;
}

.todo {
  width: 600px;
  border: 1px solid #dadada;
  padding: 20px 24px;
  border-radius: 8px;
  box-shadow: rgba(0, 0, 0, 0.16) 0px 1px 4px;
}

.header {
  display: flex;
  align-items: center;
  margin-bottom: 20px;
  gap: 12px;
}

.input {
  height: 36px;
  border: 1px solid #dadada;
  outline: none;
  border-radius: 4px;
  box-shadow: rgba(0, 0, 0, 0.16) 0px 1px 4px;
  flex: 1;
  padding: 0 16px;
}

.button {
  height: 36px;
  border: 1px solid transparent;
  color: #fff;
  outline: none;
  border-radius: 4px;
  padding: 0 16px;
  cursor: pointer;
}

.button-add {
  background-color: blue;
}

.button-delete {
  background-color: red;
}

.list-item {
  display: flex;
  flex-direction: column;
  gap: 20px;
  margin-bottom: 20px;
}

.item {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

input[type="checkbox"] {
  height: 18px;
  width: 18px;
}

.left {
  display: flex;
  align-items: center;
  gap: 8px;
}

.footer {
  display: flex;
  gap: 8px;
}
</style>
