<template>
  <div id="app">
    <sidenav />
    <router-view/>
  </div>
</template>

<script>
import Sidenav from '@/components/layout/Sidenav';
import Navbar from '@/components/layout/Navbar';

export default {
  components: {
    Sidenav,
    Navbar
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
  margin-top: 60px;
}
</style>
