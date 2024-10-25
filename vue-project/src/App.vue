<template>
  <div>
    <input type="text" placeholder="name">
    <input type="email" placeholder="email">
    <input type="password" placeholder="password">
  </div>
</template>

<script>



export default {

  data() {
    return {

    }
  },
  methods: {

  }
}
</script>

<style scoped>
div {
  margin: 0 auto;
  background-color: black;
  width: 300px;
  height: 100%;
  gap: 10px;
  display: flex;
  flex-direction: column;
  padding: 15px 15px;
  border-radius: 10px;
  color: white;
}

input {
  height: 40px;
  border: 1px solid white;
  font-size: 20px;

}
</style>