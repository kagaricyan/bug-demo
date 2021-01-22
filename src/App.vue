<template>
  <div id="app">
    <ant-table-demo/>
  </div>
</template>

<script>
import AntTableDemo from '@/components/AntTableDemo';

export default {
  name: 'App',
  components: {
    AntTableDemo,
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
