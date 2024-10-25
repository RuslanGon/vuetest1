<template>
    <div>
      <input type="text" placeholder="Name" /><br>
      <input type="email" placeholder="Email" />
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {

      };
    }
  }
  </script>
  
  <style scoped>
  input {
    margin-bottom: 10px; 
    padding: 8px;
    font-size: 14px;
    border: 1px solid #ccc;
    border-radius: 4px;
  }
  
  input::placeholder {
    color: #888;
  }
  </style>
  