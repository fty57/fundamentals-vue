<template>
  <div class="card">
    <BaseAlert v-if="showAlert" variant="success" @close="onClose" />
  </div>
</template>

<script>
import BaseAlert from "./components/BaseAlert.vue";

export default {
  name: "App",
  components: {
    BaseAlert,
  },
  data() {
    return {
      showAlert: true,
    };
  },
  methods: {
    onClose() {
      this.showAlert = !this.showAlert;
      console.log("on close");
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
