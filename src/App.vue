<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <Form></Form>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Form from './components/Form.vue'


export default {
  name: 'App',
  components: {
    Form
  }
}
</script>

<style>
body {
  background: rgb(204,204,204); 
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  font-size: 18px;
}
</style>
