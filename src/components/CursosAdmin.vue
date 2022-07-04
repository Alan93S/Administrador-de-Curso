<template>
  <div class="row">
    <div class="mb-3">
    
    </div>
    <div
      v-for="producto of cursos"
      :key="producto.id"
      class="col-12 col-sm-7 col-md-6 col-lg-4 mb-3"
    >
      <Card
        :producto="producto"
        v-on:delete-curso-item="deleteCurso"
        v-on:edit-curso-item="prepareEditCurso"
      />
    </div>
    <div v-if="!cursos.length">No hay cursos disponibles</div>
  </div>
</template>

<script>
import Card from "@/components/Card";

export default {
  name: "CursosAdmin",
  props: ["cursos"],
  components: {
    Card,
  },
  methods: {
    deleteCurso(id) {
      this.$emit("delete-curso-event", id);
    },
    prepareEditCurso(id) {
      this.$emit("edit-curso-prepare", id);
    },
  },
};
</script>

<style>


</style>