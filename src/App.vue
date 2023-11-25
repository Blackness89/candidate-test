<script setup>
import UserTable from './components/UserTable.vue';

</script>

<template>
  <div>
  
    <h1 class="mod">Junior Front-End developer test</h1> 
  </div>
  <div >
    <UserTable />
  </div>
  

</template>

<style>



body{
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background-color: lightcyan;
  min-height: 100vh;
}
.mod{
  display: flex;
  align-items: center;
  justify-content: center;
}
.tables{
  border: 1px;
  border-color: black;
}
.head-list{
  text-decoration-line: underline;
}
.all-label{
  display: flex;
  align-items: center;
  justify-content: center;
  padding-right: 5px;
  border: 1px;
}

</style>