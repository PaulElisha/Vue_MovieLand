<template>
  <div class="movie">
    <div>
      <p>{{ data.Year }}</p>
    </div>

    <div>
      <img
        :src="
          data.Poster !== 'N/A'
            ? data.Poster
            : 'https://via.placeholder.com/400'
        "
        alt="{{data.Title}}"
      />
    </div>

    <div>
      <span> {{ data.Type }} </span>
      <h3>{{ data.Title }}</h3>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from "vue";

const props = defineProps(["data"]);
</script>

<style></style>
