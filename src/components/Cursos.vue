<template>
  <div>
    <div
      class="card"
      v-for="{ nombre, descripcion, img } in cursos"
      :key="nombre"
      style="width: 18rem"
    >
      <img v-bind:src="img" class="card-img-top" alt="imagen" />
      <div class="card-body">
        <h5 class="card-title">{{ nombre }}</h5>
        <p class="card-text">{{ descripcion }}</p>
        <router-link to="/AdminView" class="btn btn-primary"
          >Administrar</router-link
        >
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Cursos",

  data: () => ({
    cursos: [
      {
        codigo: "0001",
        nombre: "HTML",
        estado: true,
        precio: "30000",
        duracion: "1 mes",
        descripcion: "Curso html",
        cupos: 10,
        inscritos: 0,
        img: "https://www.w3.org/html/logo/downloads/HTML5_Logo_512.png",
        url: "https://www.udemy.com/course/universidad-html-aprende-html-desde-cero-hasta-experto-css-html5/",
      },
      {
        codigo: "0002",
        nombre: "CSS",
        estado: false,
        precio: "20000",
        duracion: "1 mes",
        descripcion: "Curso css",
        cupos: 20,
        inscritos: 0,
        img: "https://lineadecodigo.com/wp-content/uploads/2014/04/css.png",
        url: "https://www.udemy.com/es/topic/css/",
      },
      {
        codigo: "0003",
        nombre: "SASS",
        estado: true,
        precio: "40000",
        duracion: "2 mes",
        descripcion: "Curso sass",
        cupos: 30,
        inscritos: 0,
        img: "https://miro.medium.com/max/512/1*9U1toerFxB8aiFRreLxEUQ.png",
        url: "https://www.udemy.com/course/sass-curso/",
      },
      // {
      //   codigo: "0004",
      //   nombre: "VUE",
      //   estado: false,
      //   precio: "50000",
      //   duracion: "3 mes",
      //   descripcion: "Curso vue",
      //   cupos: 15,
      //   inscritos: 0,
      //   img: "https://miro.medium.com/max/512/1*9U1toerFxB8aiFRreLxEUQ.png",
      //   url: "https://www.udemy.com/course/vuejs-fh/",
      // },
    ],
  }),
};
</script>


<style scoped>
.card {
  display: inline-block;
  max-width: fit-content;
  max-height: fit-content;
  margin: 50px;
  text-align: center;
  margin-left: 6%;
  border-radius: 5%;
  background-color: #ffffffd2;
}

.boton {
  border-radius: 20%;
  background: black;
  color: #fff;
}


</style>