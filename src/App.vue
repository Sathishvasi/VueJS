<template>
  <div id="app">
    <h1>VUE JS DEMO BY SATHISH</h1>
    <img src="./assets/logo.png">
    <p>Exported as current vue data: {{display}}</p>
    <h3>Exported as external component: </h3><test msg="Message PASSED!!"></test>
    <p>Exported as Router: </p>
    <p><router-link to="/users">Click here to route USERS component</router-link></p>
    <router-view/>
  </div>
</template>

<script>
import Test from './components/Test'
import Users from './components/Users'
export default {
  name: 'App',
  components:{
    Test, Users
  },
  data() {
    return {
      display: 'sathish',
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 50px;
}
</style>
