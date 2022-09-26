<template>
  <div class="Card">
    <h1>
      <slot name="CardTitle"></slot>
    </h1>
    <p>
      <slot name="CardDescription"></slot>
    </p>

  </div>
</template>

<script>
export default {
  data() {},
  methods: {
    getImgUrl(pic) {
      return require("../assets/movies/" + pic);
    },
  },
};
</script>

<style></style>
