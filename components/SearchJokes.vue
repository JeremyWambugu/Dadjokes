<template>
  <form @submit.prevent="onSubmit">
    <input type="text" v-model="text" placeholder="Search jokes ... " />
    <input class="btn btn-outline-success" type="submit" value="Search Jokes" />
  </form>
</template>

<script>
export default {
  name: "SearchJokes",
  data() {
    return {
      text: ""
    };
  },
  methods: {
    onSubmit() {
      this.$emit("search-text", this.text);
      this.text = "";
    }
  }
};
</script>

<style>
</style>