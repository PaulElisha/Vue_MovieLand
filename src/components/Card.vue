<template>
  <div class="movie">
    <div>
      <p>{{ data.Year }}</p>
    </div>

    <div>
      <img :src="data.Poster" alt="{{data.Title}}" />
    </div>

    <div>
      <span> {{ data.Type }} </span>
      <h3>{{ data.Title }}</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: ["data"],
};
</script>

<style></style>
