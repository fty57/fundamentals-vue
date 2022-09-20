<template>
  <div>
    <!-- v-bind, ordenar o atributo para ele ser dinâmico -->

    <h1 :class="{ title: true, 'title-home': isHome }">Curso Vue 3</h1>

    <p :class="pClass">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Eos modi quo ex
      delectus doloribus repellat harum molestias voluptate beatae, a voluptatum
      dicta accusamus, laborum atque amet accusantium aperiam fugit consectetur.
    </p>

    <p :style="styleClass">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolorum nihil et
      cupiditate in porro suscipit aliquam magnam iure laudantium molestiae,
      quos reprehenderit itaque consectetur molestias dolores ipsam esse at
      sapiente.
    </p>

    <div :class="boxClass">
      <p :class="pBox">box</p>
    </div>

    <div v-for="(obj, index) in todos" :key="obj.id" class="todos-item">
      <img v-if="obj.imgSrc" :src="obj.imgSrc" alt="" />
      {{ index }} - {{ obj.title }}
    </div>
  </div>
</template>

<script>
export default {
  name: "CustomHeader",
  data() {
    return {
      isHome: false,
      classVar: "title",
      pClass: ["text", "text-home"],
      styleClass: {
        color: "aqua",
        backgroundColor: "black",
        "font-size": "20px",
      },
      boxClass: ["box", "box-border"],
      pBox: "box-text",
      imgSrc: "https://via.placeholder.com/150",
      imgAlt: "Foto de Jon Show",
      todos: [
        {
          userId: 1,
          id: 1,
          title: "delectus aut autem",
          completed: false,
          imgSrc: "https://via.placeholder.com/150",
        },
        {
          userId: 1,
          id: 2,
          title: "quis ut nam facilis et officia qui",
          completed: false,
          imgSrc: "https://via.placeholder.com/150",
        },
        {
          userId: 1,
          id: 3,
          title: "fugiat veniam minus",
          completed: false,
        },
        {
          userId: 1,
          id: 4,
          title: "et porro tempora",
          completed: true,
        },
        {
          userId: 1,
          id: 5,
          title:
            "laboriosam mollitia et enim quasi adipisci quia provident illum",
          completed: false,
        },
      ],
    };
  },
};
</script>

<style>
.title {
  font-size: 20px;
  color: blue;
}

.title-home {
  font-size: 40px;
  color: green;
}
.text {
  color: yellow;
}

.text-home {
  color: #42b983;
}

.box {
  margin: 1%;
  width: 25vw;
  height: 25vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: violet;
}

.box-border {
  border: 5px solid;
  border-radius: 5px;
  border-color: #000;
}

.box-text {
  color: cyan;
  font-size: 35px;
  font-weight: 700;
  text-transform: uppercase;
}

.todos-item {
  background: #000;
  margin: 0 0 5px 0;
  padding: 3px 6px;
  color: #fff;
}
.classA {
  background-color: red;
}

.classA {
  color: white;
}
</style>
