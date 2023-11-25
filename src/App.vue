<script setup>
import UserTable from './components/UserTable.vue';

</script>

<template>
  <div class="pt-6 w-full">
  
    <h1 class="w-full pd-2 ">This is an imported table from Tailwindcss</h1> 
  </div>
  <div class="w-full place-items-center border bg-border-black p-2">
    <UserTable />
  </div>
  

</template>

<style scoped>

body{
  background-color: orangered;
}
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>