<template>
  <div v-if="repos.name">
    <header id="header">
      <div><span>Github</span> <span>Search</span></div>
      <div class="search">
        <input type="text" class="search-input" v-model="inputSearch" />
        <button
          class="search-btn"
          v-on:click="
            getUser();
            getRepository();
          "
        >
          <img src="../../assets/search.png" />
        </button>
      </div>
    </header>
    <!-- <Search /> -->
    <div class="container">
      <!-- <Aside /> -->
      <aside id="sidebar">
        <img class="img-perfil" :src="repos.avatar_url" />
        <h2>{{ repos.name }}</h2>
        <ul>
          <li>
            <img src="../../assets/organization.png" />{{ repos.company }}
          </li>
          <li><img src="../../assets/location.png" />{{ repos.location }}</li>
          <li><img src="../../assets/star.png" />{{ repos.followers }}</li>
          <li>
            <img src="../../assets/repository.png" />{{ repos.following }}
          </li>
          <li>
            <img src="../../assets/followers.png" />{{ repos.public_gists }}
          </li>
        </ul>
      </aside>
      <main id="repositorios">
        <!-- <Repository :title='repostorio' /> -->
        <section v-for="repo in repostorio" v-bind:key="repo.id">
          <strong> <a :href=repo.svn_url target="_blank">{{ repo.name }}</a></strong>
          <p>{{ repo.description }}</p>
          <span><img src="../../assets/star.png" /> {{ repo.forks }}</span>
        </section>
      </main>
    </div>
  </div>

  <div class="search-home" v-else>
    <img src="../../assets/GithubSearch.png" />
    <div class="search-area">
      <input type="text" v-model="inputSearch" class="search-input" />
      <button
        class="search-btn"
        v-on:click="
          getUser();
          getRepository();
        "
      >
        <img src="../../assets/search.png" />
      </button>
    </div>
    <!-- <Home /> -->
  </div>
</template>

<script>
// import Search from "../layout/Search.vue";
// import Repository from "../layout/Repository";
// import Aside from "../layout/Aside.vue";
// import Home from "./Home.vue";
import axios from "axios";
export default {
  name: "Detalhe",

  data() {
    return {
      inputSearch: "",
      repostorio: null,
      repos: [],
    };
  },
  components: {
    // Home,
    // Search,
    // Aside,
    // Repository,
  },

  methods: {
    getUser() {
      axios
        .get(`https://api.github.com/users/${this.inputSearch}`)
        .then((response) => {
          this.repos = response.data;
          // this.repos = response;
        });
    },
    getRepository() {
      axios
        // .get("https://api.github.com/users/moraes3000/repos")
        .get(`https://api.github.com/users/${this.inputSearch}/repos`)
        .then((response) => {
          this.repostorio = response.data;
          // this.repos = response;
        });
    },
  },
};
</script>

<style  scoped>
.container {
  display: flex;
  margin: 30px;
}

/* home */
.search-home {
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
/* search */
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
/* aside */
#sidebar h2 {
   color: #000;
  font-size: 36px;
  line-height: 42.66px;
  font-family: "Rubik", sans-serif;
}
#sidebar span {
  font-size: 24px;
  line-height: 28.44px;
}
#sidebar ul {
  list-style: none;
  margin-top: 50px;
}
#sidebar ul li {
  display: flex;
  align-items: center;
  margin-bottom: 15px;
}

.img-perfil {
  width: 310px;
  height: 300px;
}
/* repository */
#repositorios {
  margin-left: 85px;
}
#repositorios section {
  margin-bottom: 37px;
}

#repositorios strong {
  font-size: 36px;
  line-height: 42.66px;
}
#repositorios strong a{
  color: #000;
}
#repositorios p {
  font-size: 24px;
  line-height: 28.44px;
}
#repositorios span {
  display: flex;
  align-items: center;
}
</style>