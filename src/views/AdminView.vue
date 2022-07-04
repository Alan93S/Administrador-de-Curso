<template>

<div>
  <NavBar/>
</div>

  <div class="container">
    <h1 class="font-admin">Administrador de cursos</h1>

    <hr />
    <div class="mb-3">
      <button
        id="add-course"
        type="button"
        class="btn btn-primary"
        @click="isOpenAdd = true"
      >
        Agregar nuevo curso
      </button>
    </div>
    <CursosAdmin
      v-bind:cursos="cursos"
      v-on:delete-curso-event="deleteCurso"
      v-on:edit-curso-prepare="prepareCursoToEdit"
    />
  </div>

  <AddCursoVue
    v-bind:isOpenAdd="isOpenAdd"
    v-bind:editCurso="editCurso"
    v-on:add-curso-event="addCurso"
    v-on:close-modal-add="closeModalAdd"
    v-on:edit-curso-event="updateCurso"
  />
</template>

<script>
import AddCursoVue from "@/components/AddCurso.vue";
import CursosAdmin from "@/components/CursosAdmin.vue";

import datos from "/public/cursos.json";
import Admin from "@/components/Admin.vue";
import NavBar from "@/components/NavBar.vue"
export default {
  name: "App",
  components: {
    Admin,
    AddCursoVue,
    CursosAdmin,
    NavBar
  },

  data() {
    return {
      cursos: [],
      isOpenAdd: false,
      editCurso: {
        id: "",
        name: "",
        description: "",
      },
    };
  },
  methods: {
    addCurso(newCurso) {
      this.cursos = [...this.cursos, newCurso];
    },
    updateCurso(cursoToUpdate) {
      let index = this.cursos.findIndex((obj) => obj.id === cursoToUpdate.id);
      this.cursos[index] = cursoToUpdate;
    },
    deleteCurso(id) {
      this.cursos = this.cursos.filter((curso) => curso.id !== id);
    },
    openModalAdd: () => (this.isOpenAdd = true),
    closeModalAdd() {
      this.editCurso = {
        id: "",
        name: "",
        description: "",
      };
      this.isOpenAdd = false;
    },
    prepareCursoToEdit(id) {
      let index = this.cursos.findIndex((curso) => curso.id === id);
      this.editCurso.name = this.cursos[index].name;
      this.editCurso.description = this.cursos[index].description;
      this.editCurso.id = id;
      this.isOpenAdd = true;
    },
  },

  watch: {
    cursos: {
      handler() {
        localStorage.setItem("cursos", JSON.stringify(this.cursos));
      },
      deep: true,
    },
  },

  mounted() {
    if (localStorage.getItem("cursos")) {
      this.cursos = JSON.parse(localStorage.getItem("cursos"));
    } else {
      this.cursos = datos;
    }
  },
};
</script>

<style>

.font-admin {
  font-family: 'Finlandica', sans-serif;
 text-align: center;
 color: white
}
</style>