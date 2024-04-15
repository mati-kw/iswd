<template>
    <div>
      <h1>Login</h1>
      <form @submit.prevent="login">
        <input v-model="username" type="text" placeholder="Username" />
        <input v-model="password" type="password" placeholder="Password" />
        <button type="submit">Login</button>
      </form>
    </div>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    data() {
      return {
        username: '',
        password: ''
      };
    },
    methods: {
      login() {
        const payload = {
          username: this.username,
          password: this.password
        };
        axios.post('http://localhost:8000/api/token/', payload)
          .then(response => {
            console.log(response.data);
            // Store the token in local storage or vuex
            localStorage.setItem('access_token', response.data.access);
            localStorage.setItem('refresh_token', response.data.refresh);
            // Redirect to home page or wherever needed
            this.$router.push('/');
          })
          .catch(error => {
            console.error('There was an error!', error);
          });
      }
    }
  }
  </script>
  