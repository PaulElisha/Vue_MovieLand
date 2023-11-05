<template>
  <div class="app">
    <h1>MovieLand</h1>
    <div class="search">
      <input
        type="text"
        placeholder="Search a movie..."
        v-model="searchValue"
      />
      <button @click="handleSearch">Search</button>
    </div>
  </div>
  <Main :data="data" />
</template>

<script>
import axios from "axios";
import Main from "./Main.vue";

export default {
  name: "Header",

  components: {
    Main,
  },
  data() {
    return {
      searchValue: "",
      data: [],
    };
  },
  methods: {
    async handleSearch() {
      const api = "http://www.omdbapi.com?apikey=b6003d8a";

      try {
        const response = await axios.get(`${api}&s=${this.searchValue}`);
        const data = response.data.Search;
        console.log(data);
        this.data = data;
        this.searchValue = "";
      } catch (err) {
        console.log(err);
      }
    },
  },
};
</script>

<style></style>
