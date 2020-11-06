<template>
  <div id="app">
    <Dashboard />
  </div>
</template>

<style>
@import 'assets/styles/global.css';
</style>

<script>
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'

import Dashboard from './components/Dashboard.vue'

export default {
  name: 'App',
  components: {
    Dashboard
  }
}
</script>
