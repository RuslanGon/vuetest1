<template>
  <div>
    <input type="text" v-model="userName" placeholder="name">
    <input type="email" v-model="userEmail" placeholder="email">
    <input type="password" v-model="userPass" placeholder="password">
    <p class="error">{{ error }}</p>
  </div>
  <User  v-for="(el, index) in users" :key="index" :el="el" :index="index" :deleteUser="deleteUser" />

  <div v-if="users.length == 0">
    <p>not users</p>
  </div>
  <div v-else-if="users.length == 1">
    <p>We have one user</p>
  </div>
  <div class="button-container">
    <button @click="SendData()">Send</button>
  </div>

</template>

<script>
import User from './components/User.vue'
export default {
  components: { User},
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
      if (this.userName === '') {
        this.error = 'Please enter a name';
        return;
      } else if (this.userEmail === '') {
        this.error = 'Please enter an email';
        return;
      } else if (this.userPass === '') {
        this.error = 'Please enter a password';
        return;
      }

      this.error = '';


      this.users.push({
        name: this.userName,
        email: this.userEmail,
        pass: this.userPass
      });
    },
    deleteUser(index) {
      this.users.splice(index, 1)
    }
  }
}
</script>

<style scoped>
.users {
  background-color: rgb(220, 219, 219);
  color: black;
}
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
