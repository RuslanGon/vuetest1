<template>
  <div>
    <input type="text" v-model="userName" placeholder="name">
    <input type="email" v-model="userEmail" placeholder="email">
    <input type="password" v-model="userPass" placeholder="password">
    <button @click="SendData()">Send</button>
    <button @click="resetData()">Reset</button>

    <p>{{ users }}</p>
 
  </div>
</template>

<script>

export default {

  data() {
    return {
      users: [],
      userName: '',
      userEmail: '',
      userPass: ''
    }
  },
  methods: {
    SendData() {
      if(this.userName === '')return
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
button:hover {
  background-color: white;
  color: black;
}
button {
  margin-left: 100px;
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

input::placeholder {
  color: #ccc;
}

input:focus {
  outline: none;
  border-color: gold ; 
}
</style>