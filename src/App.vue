<template>
 
  <div id="app">
 <navbar></navbar>
 <bread></bread>
 <!-- <router-view></router-view>-->
  <list ></list>
  
    <footerM></footerM>  
  </div>
  
</template>

<script>
import navbar from './components/navbar.vue'
import footerMat from './components/footerMat.vue'
import breadS from './components/breadS.vue'
import list from './components/list.vue'


export default {
  name: 'app',
  components: {navbar: navbar, footerM: footerMat, bread: breadS, list:list}
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
