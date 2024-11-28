<template>
    <div>
      <h1>Home</h1>
      <button @click="logout">Logout</button>
    </div>
  </template>
  
  <script>
  import { auth } from '../firebaseConfig'
  
  export default {
    methods: {
      logout() {
        auth.signOut()
          .then(() => {
            this.$router.push('/login')
          })
      }
    }
  }
  </script>
  