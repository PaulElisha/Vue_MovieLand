<template>
  <div class="app">
    <h1>Vue MovieLand</h1>
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

<script setup>
import axios from "axios";
import Main from "./Main.vue";
import { ref } from "vue";

const searchValue = ref("");
const data = ref([]);

const handleSearch = async () => {
  const api = "https://www.omdbapi.com/?i=tt3896198&apikey=30326135";

  try {
    const response = await axios.get(`${api}&s=${searchValue.value}`);
    data.value = response.data.Search;
    console.log(response);
    searchValue.value = "";
  } catch (err) {
    console.log(err);
  }
};
</script>

<style></style>
