<template>
  <div class="search">
    <img src="../../assets/GithubSearch.png" />
    <div class="search-area">
      <input type="text" v-model="user" class="search-input" />
      <button class="search-btn" v-on:click=getUserInfo>
        <img src="../../assets/search.png" />
      </button>
    </div>  
  </div>
</template>


<style  scoped>
.search {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
}

.search-area {
  margin-top: 15px;
  display: flex;
  align-items: center;
}
.search-input {
  height: 50px;
  width: 600px;
  padding: 10px;
}
.search-btn {
  /* padding:10px 35px; */
  background: #000;
  width: 100px;
  height: 50px;
}
</style>
