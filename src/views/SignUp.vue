<template>
    <div>
      <h1>Sign Up</h1>
      <form @submit.prevent="signUp">
        <input v-model="email" type="email" placeholder="Email">
        <input v-model="password" type="password" placeholder="Password">
        <button type="submit">Sign Up</button>
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
      signUp() {
        auth.createUserWithEmailAndPassword(this.email, this.password)
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
  