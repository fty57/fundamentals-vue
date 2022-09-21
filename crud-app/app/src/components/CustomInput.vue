<template>
  <div>
    <!-- V-ON é para pegar eventos ou substituir por @ -->
    <button @click="onClick">Enviar</button>
    <br />
    <div @mouseover="onMouseOver" @mouseout="onMouseOut">Mouse over</div>
  </div>
  <br /><br />

  <form action="https://google.com" v-on:submit.prevent="onSubmit">
    <input type="text" @keyup.enter="onKeyUp" />
    <button type="submit">Enviar</button>
  </form>

  <br /><br />

  <div>
    <label>Explique por que você gosta dessa menina?</label><br />
    <textarea v-model="textArea"></textarea><br />
    <p :class="pClass">
      {{ textArea }}
    </p>
  </div>

  <br /><br />

  <div>
    <button v-on:click.stop="say('hello')">Plus +1</button>
    <button v-on:click.once="say('bye')">Plus -1</button>
    <button v-on:click.prevent="warn('warn')">Warn</button>
  </div>
</template>

<script>
export default {
  name: "CustomInput",
  data() {
    return {
      textArea: "",
      pClass: "pClass",
      count: 0,
    };
  },

  methods: {
    onClick(evt) {
      console.log("click", evt);
    },
    onSubmit() {
      console.log("submit");
    },
    onKeyUp(evt) {
      console.log("onKeyUp", evt);
    },
    say(message) {
      alert(message);
    },
    warn(message, event) {
      if (event) {
        event.preventDefault();
      }
      console.log(message);
    },
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
