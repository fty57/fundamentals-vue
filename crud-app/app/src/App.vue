<template>
  <TheHeader>
    <template v-slot:title>
      <h1>Home</h1>
    </template>

    <template v-slot:description>
      <p>dasds</p>
    </template>

    Content do header - menu
  </TheHeader>

  <div v-show="showName">Nome: {{ firstName }} Sobrenome: {{ lastName }}</div>

  <div v-if="accessLevel === 'admin'">Admin</div>
  <div v-else-if="accessLevel === 'marketing'">Marketing</div>
  <div v-else>User</div>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";

export default {
  name: "App",
  components: {
    TheHeader,
  },
  data() {
    return {
      showHeader: true,
      firstName: "Álisson",
      lastName: "Véras",
      showName: false,
      accessLevel: "marketing",
    };
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
