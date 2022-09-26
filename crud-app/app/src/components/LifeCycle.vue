<template>
  <div>
    <h1>Hellow World</h1>
    {{ name }}
  </div>
</template>

<script>
export default {
  name: "LifeCycle",
  data() {
    return {
      name: "Jon Snow",
    };
  },
  // Criação
  // Preparar o componente
  // Ajax, inicializar algumas variáveis
  // Não tem acesso ao template (DOM)

  // Montagem
  // Inicializar uma lib externa (new Lib())
  // Precisa de acesso ao template (DOM)
  // Tem acesso ao template (DOM)

  // Atualização
  // Debug
  // Update

  // Desmontagem
  // Remover tudo o que for necessário (lib-> destroy())
  // para liberar memória

  //$el pegar o elemento raiz

  // HOOKS
  beforeCreate() {
    console.log("beforeCreate");
    console.log("Estado:", this.name);
    console.log("DOM:", this.$el);
  },
  created() {
    console.log("created");
    console.log("Estado:", this.name);
    console.log("DOM:", this.$el);
  },
  beforeMount() {
    console.log("beforeMount");
    console.log("Estado:", this.name);
    console.log("DOM:", this.$el);
  },
  mounted() {
    console.log("mounted");
    console.log("Estado:", this.name);
    console.log("DOM:", this.$el);
  },
  beforeUnmount() {
    console.log("beforeUnmount");
  },
  unmounted() {
    console.log("unmounted");
  },

  watch: {},
  computed: {},
  methods: {},
};
</script>

<style></style>
