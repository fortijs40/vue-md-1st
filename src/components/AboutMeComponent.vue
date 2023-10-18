<template>
    <div class="info">
      <h1>ABOUT ME</h1>
      <h3>Name: <val>{{ user.name }}</val></h3>
      <h3>Surname: <val>{{ user.surname }}</val></h3>
      <h3>Code: <val>{{ user.code }}</val></h3>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        user: {
          name: "Ralfs",
          surname: "Laipiņš",
          code: "IT21014",
        },
      };
    },
  };
  </script>
<style>
    val, h1{
        color: white;
        font-weight: bold;
    }
</style>  