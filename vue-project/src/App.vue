<template>
    <div>
      <h1>Hello</h1>
      <User />
      <Input />
    </div>
  </template>
  
  <script>
  import User from './components/User.vue'
  import Input from './components/Input.vue'

  
  export default {
    components: { User, Input },
    data() {
      return {
        
      }
    }
  }
  </script>
  
  <style scoped>
  
  </style>
  