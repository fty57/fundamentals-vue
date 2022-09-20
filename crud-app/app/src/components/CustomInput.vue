<template>
  <div>
    <label>Explique por que você gosta dessa menina?</label><br />
    <textarea v-model="textArea"></textarea><br />
    <p :class="pClass">
      {{ textArea }}
    </p>
  </div>
</template>

<script>
export default {
  name: "CustomInput",
  data() {
    return {
      textArea: "",
      pClass: "pClass",
    };
  },
};
</script>

<style>
.pClass {
  font-size: 16px;
  font-weight: 400;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  color: rgb(182, 46, 46);
}
</style>
