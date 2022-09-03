<template>
  <div id="app">
    <section  v-if="check_cookie === null">
      <login-form></login-form>
      <p>sign in</p>
    </section>
    <section v-else>
    
    <all-users></all-users>
    </section>
    
  </div>
</template>

<script>
import AllUsers from '@/components/AllUsers.vue'
import LoginForm from '@/components/LoginForm.vue'
import Cookies from 'vue-cookies'



export default {
  data() {
    return {
      check_cookie: Cookies.get(`token`)
    }
  },
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
