<template>
  <div id="app">
    <all-users></all-users>
    <login-form></login-form>
  </div>
</template>

<script>
import AllUsers from '@/components/AllUsers.vue'
import LoginForm from '@/components/LoginForm.vue'


export default {
  name: 'App',
  components: {
    AllUsers,
    LoginForm
    
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
