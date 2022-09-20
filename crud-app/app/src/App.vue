<template>
  <!-- <CustomHeader v-if="showHeader" /> --> 
  <CustomInput />

  <div v-show="showName">Nome: {{ firstName }} Sobrenome: {{ lastName }}</div>

  <div v-if="accessLevel === 'admin'">Admin</div>
  <div v-else-if="accessLevel === 'marketing'">Marketing</div>
  <div v-else>User</div>

  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Welcome to Your Vue.js App" />
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import CustomInput from "./components/CustomInput.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    CustomInput,
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
