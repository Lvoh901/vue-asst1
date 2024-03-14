<template>
  <div class="login-page">
    <form class="form" @submit.prevent="login">
      <h1>Welcome</h1>
      <input type="text" v-model="username" placeholder="username" />
      <input type="password" v-model="password" placeholder="password" />
      <p>Forgot Password?<a href="/reset">Reset</a></p>

      <button type="submit">Login</button>

      <div>
        <p>Not a Member? <a href="/signup"> SignUp</a></p>
      </div>
    </form>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      username: '',
      password: ''
    }
  },
  methods: {
    async login() {
      try {
        const response = await axios.post('http://localhost:4002/login', {
          username: this.username,
          password: this.password
        })

        console.log(response.data.message) // Success message from the server
      } catch (error) {
        console.error(error.message)
      }
    }
  }
}
</script>

<style scoped>
.login-page {
  width: 360px;
  padding: 8% 0 0;
  margin: auto;
}

.form {
  position: relative;
  background: #ffffff;
  max-width: 360px;
  margin: 0 auto 100px;
  padding: 45px;
  text-align: center;
}

.form input {
  font-family: Georgia, 'Times New Roman', Times, serif;
  outline: 0;
  background: #f2f2f2;
  width: 100%;
  border: 0;
  margin: 0 0 15px;
  padding: 15px;
  box-sizing: border-box;
  font-size: 14px;
}

.form input::placeholder {
  font-family: Georgia, 'Times New Roman', Times, serif;
  text-transform: capitalize;
}

.form button {
  font-family: 'Roboto', sans-serif;
  outline: 0;
  background: #808080;
  width: 100%;
  border: 0;
  padding: 15px;
  color: #ffffff;
  font-size: 14px;
}
</style>
