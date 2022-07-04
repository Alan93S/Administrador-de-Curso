<template>

  <!-- Modal de AGREGAR-->
  <Modal v-if="isOpenAdd" title="Hola mundo" style="z-index: 1060">
    <template v-slot:header>
      <div class="modal-header">
        <h5 class="modal-title">
          <template v-if="edit === false"> Crear curso </template>
          <template v-else> Editar curso {{ editCurso.id }} </template>
        </h5>
      </div>
    </template>

    <template v-slot:body>
      <div class="modal-body">
        <form>
          <div class="form-group mb-3">
            <label for="name" class="me-2">Nombre:</label>
            <input
              id="name"
              type="text"
              name="name"
              v-model="name"
              placeholder="Ingrese nombre"
            />
          </div>
          <div class="form-group">
            <label for="description" class="me-2">Descripción:</label>
            <input
              type="textarea"
              id="description"
              name="description"
              v-model="description"
              placeholder="Ingrese descripción"
            />
          </div>
        </form>
      </div>
    </template>

    <template v-slot:footer>
      <div class="modal-footer">
        <button type="button" class="btn btn-primary" @click="addCurso">
          <template v-if="edit === false"> Crear </template>
          <template v-else> Editar </template>
        </button>
        <button type="button" class="btn btn-secondary" @click="closeModal">
          Salir
        </button>
      </div>
    </template>
  </Modal>
</template>

<script>
import Modal from "@/components/Modal.vue";
import NavBar from "@/components/NavBar.vue"
export default {
  name: "AddCursosItem",
  components: {
    Modal,NavBar
  },
  props: ["isOpenAdd", "editCurso"],
  data() {
    return {
      name: "",
      description: "",
      edit: false,
      id: "",
    };
  },
  methods: {
    addCurso(e) {
      e.preventDefault();
      if (this.edit === false) {
        const newCurso = {
          id: Math.floor(Math.random() * 100),
          name: this.name,
          description: this.description,
        };
        if (newCurso.name !== "" && newCurso.description !== "") {
          this.$emit("add-curso-event", newCurso);
          this.name = "";
          this.description = "";
        }
      } else {
        const cursoToEdit = {
          description: this.description,
          name: this.name,
          id: this.id,
        };
        this.$emit("edit-curso-event", cursoToEdit);
        this.closeModal();
      }
    },
    closeModal() {
      this.name = "";
      this.description = "";
      this.id = "";
      this.edit = false;
      this.$emit("close-modal-add");
    },
  },
  watch: {
    editCurso: {
      handler() {
        this.name = this.editCurso.name;
        this.description = this.editCurso.description;
        this.id = this.editCurso.id;
        this.edit = true;
      },
      deep: true,
    },
    name: {
      handler() {
        if (this.name === "") {
          this.edit = false;
        }
      },
    },
    description: {
      handler() {
        if (this.description === "") {
          this.edit = false;
        }
      },
    },
  },
};
</script>