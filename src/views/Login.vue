<template>
    <div>
      <h1>Login</h1>
      <form @submit.prevent="login">
        <input v-model="email" type="email" placeholder="Email">
        <input v-model="password" type="password" placeholder="Password">
        <button type="submit">Login</button>
      </form>
    </div>
  </template>
  
  <script>
  import { auth } from '../firebaseConfig'
  
  export default {
    data() {
      return {
        email: '',
        password: ''
      }
    },
    methods: {
      login() {
        auth.signInWithEmailAndPassword(this.email, this.password)
          .then(() => {
            this.$router.push('/')
          })
          .catch(error => {
            console.error(error)
          })
      }
    }
  }
  </script>
  