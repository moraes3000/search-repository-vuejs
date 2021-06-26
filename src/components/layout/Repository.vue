<template>
  <button v-on:click="getRepository">start {{ title }}</button>

  <div>
    <main id="repositorios">
      <section v-for="repo in repostorio" v-bind:key="repo.id">
        <strong> {{ repo.name }}</strong>
        <p>{{ repo.description }}</p>
        <span><img src="../../assets/star.png" /> {{ repo.forks }}</span>
      </section>
    </main>
  </div>
</template>


<script>
// eslint-disable-next-line no-unused-vars
import axios from "axios";

export default {
  name: "Repositorios",
  props: ["title"],
  data() {
    return {
      repostorio: null,
    };
  },
  // created() {
  //   axios
  //     .get('https://api.github.com/users/moraes3000/repos')
  //     // .get(`https://api.github.com/users/${this.title}/repos`)
  //     .then((response) => {
  //       this.repostorio = response.data;
  //       // this.repos = response;
  //       console.log();
  //     });
  // },
  methods: {
    // getRepository() {
    //   alert(`clicou em ${this.title}`);
    //   axios
    //     // .get("https://api.github.com/users/moraes3000/repos")
    //     .get(`https://api.github.com/users/${this.title}/repos`)
    //     .then((response) => {
    //       this.repostorio = response.data;
    //       // this.repos = response;
    //       console.log();
    //     });
    //   alert("chego");
    // },
  },
};
</script>

<style  scoped>
#repositorios {
  margin-left: 85px;
}
#repositorios section {
  margin-bottom: 37px;
}

#repositorios strong {
  color: #000;
  font-size: 36px;
  line-height: 42.66px;
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
