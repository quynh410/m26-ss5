<template>
    <h1>List rendering</h1>
    <!-- in la loc qua -->
    <ul v-for="user in listUser" :key="user.id">
         <li>ID : {{ user.id }}</li>
        <li>Name : {{ user.name }}</li>
    </ul>
</template>

<script setup>
    const listUser = [
        { name: 'John Doe', id: 1 },
        { name: 'Jane Smith', id: 2 },
        { name: 'Alice Johnson', id: 3 }
    ]
</script>

<style>

</style>