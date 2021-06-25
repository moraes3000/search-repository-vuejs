<template> 
  <div id="app">
       <Home />
    <router-view />
  </div>
</template>

<script>
import Home from './components/pages/Home.vue'
export default {
  name: 'App',
  components: {
    Home,
  }
}
</script>

<style>
* {
  margin:0;
  padding: 0;
  box-sizing: border-box;

   font-family: "Rubik", sans-serif;
   color:#757575;
}
</style>
