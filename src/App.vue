<template>
  <div id="app">
    <index></index>
<!--    <manager-delete></manager-delete>-->
  </div>
</template>

<script>
import Index from './components/index.vue'
// import ManagerDelete from './components/manager_delete.vue'

export default {
  name: 'App',
  components: {
    Index,
      // ManagerDelete
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
  /*margin-top: 60px;*/
}
</style>
