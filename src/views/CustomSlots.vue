<template>
<div>
    <h1>Aprendiendo Slots</h1>
     <button type="button" class="btn btn-primary" @click="isOpen= true " >Abrir Modal</button>

<Modal v-if="isOpen"
 title="Hola mundo"
 @on:close="closeModal">
 
  
 <!-- <h2>titulo del modal</h2>
  <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. </p>
  <button>Salir</button> -->

  <template v-slot:header>
     <h2>Titulo Modal</h2>
  </template>

  <template v-slot:footer>
     <button @click="closeModal" >Salir</button>
    
  </template>
  <template v-slot:body>
     <h2>Lorem, ipsum dolor sit amet consectetur adipisicing </h2>
  </template>

  </Modal>
  </div>
</template>



<script>
import { ref } from 'vue'
import Modal from '../components/Modal.vue'
export default {
    components: {Modal},
    setup() {

        const isOpen = ref(false)

            return {

                isOpen,

                openModal: () => isOpen.value = true,
                closeModal: () => isOpen.value = false
            }

    }
}
</script>

<style>

</style>