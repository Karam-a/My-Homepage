<template>
    <Portfolio />
  </template>
  
  <script>
  import Portfolio from './components/Portfolio.vue'
  
  export default {
    name: 'App',
    components: {
      Portfolio
    }
  }
  </script>
  
  <style>
  html, body {
    margin: 0;
    padding: 0;
    min-height: 100vh;
  }
  
  #app {
    height: 100vh;
  }
  </style>