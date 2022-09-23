<template>
  <div class="main">
    <navbar-menu />
    <router-view />    
  </div>
</template>

<script>
import NavbarMenu from "@/components/NavbarMenu";



export default {
  name: 'App',
  components: {
    NavbarMenu
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
