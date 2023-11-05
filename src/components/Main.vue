<template>
  <div class="container">
    <template v-if="data.length > 0">
      <div v-for="data in data" :key="data.imdbID">
        <Card :data="data" />
      </div>
    </template>
    <div class="empty" v-else>
      <h2>No Item Found</h2>
    </div>
  </div>
</template>

<script>
import Card from "./Card.vue";
export default {
  name: "Main",
  props: {
    data: Object,
  },
  components: {
    Card,
  },
  data() {
    return {};
  },
};
</script>

<style></style>
