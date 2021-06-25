<template>
  <div>
    <Search />
    <div class="container">   
      <Aside/>
      <main id="repositorios">
        <Repository/>
      </main>
    </div>
  </div>
</template>

<script>
import Search from "../layout/Search.vue";
import Repository from '../layout/Repository'
import Aside from '../layout/Aside.vue'
export default {
  name: "Detalhe",
  components: {
    Search,  
    Aside,  
    Repository,
  },
};
</script>

<style  scoped>
.container {
  display: flex;
  margin: 30px;
}
</style>