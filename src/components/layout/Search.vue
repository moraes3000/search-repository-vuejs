<template>
  <header id="header">
    <div><span>Github</span> <span>Search</span></div>
    <div class="search">
      <input type="text" class="search-input" v-model="inputSearch" />
      <button class="search-btn"><img src="../../assets/search.png" /></button>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Search',
  data() {
    return {
       inputSearch: 'moraes3000',
    };
  },
};
</script>

<style>
#header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 42px;
  margin: 40px 30px;
}
#header .search {
  display: flex;
  align-items: center;
}
#header .search-input {
  height: 50px;
  width: 600px;
  padding: 10px;
}
#header .search-btn {
  /* padding:10px 35px; */
  background: #000;
  width: 100px;
  height: 50px;
}
#header span:first-child {
  font-family: "Roboto Mono", monospace;
}
#header span:last-child {
  font-family: "Rubik", sans-serif;
  font-style: italic;
}
</style>
