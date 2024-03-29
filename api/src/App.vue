<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <API/>
  <SignUpForm/>
</template>

<script>
import API from './components/API.vue'
import SignUpForm from './components/SignUp.vue'

export default {
  name: 'App',
  components: {
    API,
    SignUpForm
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
