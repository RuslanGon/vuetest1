<template>
  <div>
    <input type="text" v-model="userName" placeholder="name">
    <input type="email" v-model="userEmail" placeholder="email">
    <input type="password" v-model="userPass" placeholder="password">
    <p class="error">{{ error }}</p>
    <p>{{ users }}</p>
  </div>
  <div class="button-container">
    <button @click="SendData()">Send</button>
    <button @click="resetData()">Reset</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      users: [],
      error: '',
      userName: '',
      userEmail: '',
      userPass: ''
    }
  },
  methods: {
    SendData() {
      if (this.userName === ''){
        this.error = 'not name'
      }else  if (this.userEmail === ''){
        this.error = 'not email'
      }else  if (this.userPass === ''){
        this.error = 'not password'
      }
      this.error = ''
      this.users.push({
        name: this.userName,
        pass: this.userPass,
        email: this.userEmail
      })
    },
    resetData() {
      this.userName = ''
      this.userEmail = ''
      this.userPass = ''
    }
  }
}
</script>

<style scoped>
.error {
  color: red;
}
button:hover {
  background-color: white;
  color: black;
}

button {
  width: 100px;
  padding: 10px;
  cursor: pointer;
  background-color: transparent;
  color: gold;
  border: 1px solid white;
  border-radius: 5px;
}

div {
  margin: 0 auto;
  background-color: black;
  width: 300px;
  gap: 10px;
  display: flex;
  flex-direction: column;
  padding: 15px;
  border-radius: 10px;
  color: white;
}

input {
  height: 40px;
  border: 1px solid white;
  font-size: 20px;
}

input::placeholder {
  color: #ccc;
}

input:focus {
  outline: none;
  border-color: gold;
}
.button-container {
  display: flex;
  flex-direction: row;
  justify-content: center;
  gap: 40px;
}
</style>
