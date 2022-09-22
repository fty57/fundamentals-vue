<template>
  <div>
    <input v-model="name" type="text" /><br />
    {{ name }} <br /><br /><br />

    <input v-model="user.first_name" type="text" /><br />

    <input v-model="user.last_name" type="text" /><br />
    {{ user.first_name }} {{ user.last_name }} <br />

    <select v-model="pageCount">
      <option value="5">5</option>
      <option value="10">10</option>
      <option value="15">15</option></select
    ><br />
    {{ pageCount }}
  </div>
</template>

<script>
export default {
  name: "WatchersVue",
  data() {
    return {
      name: "",
      pageCount: 5,
      user: {
        first_name: "",
        last_name: "",
      },
    };
  },
  watch: {
    // Então você faz uma função com o mesmo nome dessa váriavel
    name(newValue) {
      if (newValue.length >= 3) {
        this.saveUserName();
      }
    },
    pageCount() {
      this.changePage();
    },
    user: {
      // Disparar o alerta caso o atributo do objeto user for alterado, precisa-se de um handler
      handler() {
        console.log("User alterado");
      },

      // Deep é uma observação mais profunda, elevando a outro nível
      deep: true,
    },
  },
  computed: {},
  methods: {
    saveUserName() {
      console.log(this.name);
    },
    changePage() {
      console.log("Ajax changePage");
    },
  },
};
</script>

<style></style>
