<template>
  <aside id="sidebar">
    <img class="img-perfil" :src="repos.avatar_url" />
    <h2>{{ repos.name }}</h2>
    <ul>
      <li><img src="../../assets/organization.png" />{{ repos.company }}</li>
        <li><img src="../../assets/location.png" />{{ repos.location }}</li>
      <li><img src="../../assets/star.png" />{{ repos.followers }}</li>
      <li><img src="../../assets/repository.png" />{{ repos.following }}</li>
      <li><img src="../../assets/followers.png" />{{ repos.public_gists }}</li>
    </ul>
  </aside>
</template>


<script>
import axios from "axios";

export default {
  name: "Aside",

  data() {
    return {
      repos: [],
    };
  },

  created() {
    axios.get("https://api.github.com/users/moraes3000").then((response) => {
      this.repos = response.data;
      // this.repos = response;
    });
  },
};
</script>

<style>
#sidebar h2 {
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
</style>