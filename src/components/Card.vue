<template>
  <div>
    <div class="card" style="width: 18rem">
      <div class="card-header text-end">
        <button
          type="button"
          class="btn btn-success btn-sm me-1"
          @click="isOpenDetails = true"
        >
          <i class="bi bi-search"></i>
        </button>
        <button
          type="button"
          class="btn btn-warning btn-sm me-1"
          @click="$emit('edit-curso-item', producto.id)"
        >
          <i class="bi bi-pencil"></i>
        </button>
        <button
          type="button"
          class="btn btn-danger btn-sm"
          @click="$emit('delete-curso-item', producto.id)"
        >
          <i class="bi bi-trash"></i>
        </button>
      </div>
      <div class="card-body">
        <h5 class="card-title">{{ producto.name }}</h5>
        <p class="card-text">{{ producto.description }}</p>
      </div>
    </div>
    <!-- Modal de VER-->
    <Modal v-if="isOpenDetails" style="z-index: 1060">
      <template v-slot:header>
        <div class="modal-header">
          <h5 class="modal-title">Curso #{{ producto.id }}</h5>
        </div>
      </template>

      <template v-slot:body>
        <div class="modal-body">
          <h2>{{ producto.name }}</h2>
          <p>Descripción del curso: {{ producto.description }}</p>
        </div>
      </template>

      <template v-slot:footer>
        <div class="modal-footer">
          <button @click="closeModalDetails" class="btn btn-secondary">
            Salir
          </button>
        </div>
      </template>
    </Modal>
  </div>
</template>


  
<script>
import { ref } from "vue";
import Modal from "../components/Modal.vue";
export default {
  props: ["producto"],
  components: { Modal },
  setup() {
    const isOpenDetails = ref(false);

    return {
      isOpenDetails,
      openModalDetails: () => (isOpenDetails.value = true),
      closeModalDetails: () => (isOpenDetails.value = false),
    };
  },
};
</script>

<style scoped>
</style>