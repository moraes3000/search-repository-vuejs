<template> 
  <div id="app">
       <!-- <Home /> -->
       <Detalhe/>
    <router-view />
  </div>
</template>

<script>
// import Home from './components/pages/Home.vue'
import Detalhe from './components/pages/Detalhe.vue'
export default {
  name: 'App',
  components: {
    Detalhe,
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
