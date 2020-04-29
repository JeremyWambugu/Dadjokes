<template>
  <div>
    <nuxt-link to="/jokes">Back to jokes</nuxt-link>
    <h2>{{jokes}}</h2>
    <hr />
    <small>Joke ID:{{$route.params.id }}</small>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      jokes: {}
    };
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json"
      }
    };
    try {
      const res = await axios.get(
        `https://icanhazdadjoke.com/j/${this.$route.params.id}`,
        config
      );
      this.jokes = res.data.joke;
      console.log(this.jokes);
    } catch (error) {
      console.log(error);
    }
  }
};
</script>

<style>
</style>