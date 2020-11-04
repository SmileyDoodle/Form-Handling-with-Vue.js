<template>
  <div id="app">
    <Form></Form>
  </div>
</template>

<script>
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

@media screen and (max-width: 992px) {
    body {
      background: #fff; 
    }
}
@media print {
    body {
      background: #fff; 
    }
}
</style>
