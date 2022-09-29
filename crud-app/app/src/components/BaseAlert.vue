<template>
  <div
    :class="[
      'alert',
      {
        'alert-success': variant === 'success',
        'alert-danger': variant === 'danger',
      },
    ]"
  >
    Seu formulário foi enviado com sucesso!
  </div>

  <div :class="`alert alert-${variant}`">
    Seu formulário foi enviado com sucesso!
  </div>

  <div :class="baseClass">Seu formulário foi enviado com sucesso!</div>

  <div :class="baseClass">{{ test }}</div>
</template>

<script>
export default {
  props: {
    variant: {
      type: String,
      default: "",
    },
    test: {
      type: String,
      default: "test",
    },
  },
  computed: {
    baseClass() {
      return ["alert", this.variant ? `alert-${this.variant}` : ""];
    },
  },
};
</script>

<style scoped>
.alert {
  padding: 5px;
  border-radius: 6px;
  color: gray;
  background: #ddd;
}
.alert-success {
  background: #42b983;
  color: white;
}

.alert-danger {
  background: red;
  color: white;
}
</style>
