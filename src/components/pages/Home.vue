<template>
  <div class="search">
    <img src="../../assets/GithubSearch.png" />
    <div class="search-area">
      <input type="text" v-model="user" class="search-input" />
      <button class="search-btn" v-on:click=getUserInfo>
        <img src="../../assets/search.png" />
      </button>
    </div>
    <h1>info</h1>
    {{ info }}
    <h1>repo -</h1>
    {{ repos }}
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'Home',
  data() {
    return {
      github: '',
      user: '',
      repos: [],
      info: [],
    };
  },
  methods: {
    getUserInfo() {
      // const user = e.target.value;
      axios
        .get(`https://api.github.com/users/${this.user}`)
        .then((response) => {
          this.info = response.data;
        });
      // .catch(error => console.log(error));
      this.$router.Push('HelloWorld');
    },
    getUserRepo() {
      // const user = e.target.value;
      axios
        .get(`https://api.github.com/users/${this.user}/repos`)
        .then((response) => {
          this.repos = response.data;
        });
      // .catch(error => console.log(error));
    },

    getUser() {

    },
  },
};
</script>

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
