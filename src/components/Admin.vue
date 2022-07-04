
<template>
<div>
  <NavBar/>
</div>

  <div class="container">
   

    <hr>
   
    <!--  -->
  </div>
</template>

<script>

import {useStore} from 'vuex'
import { computed, onMounted } from 'vue'
import Card from '@/components/Card'


import datos from "/public/cursos.json"
import NavBar from "@/components/NavBar.vue"
export default {
  name: 'App',
  components: {
    Card, NavBar
  },
  data() {
    return {
      buscar: ''
    }
  },
  setup(){
    const store = useStore()
    onMounted(async() => {
      store.dispatch('fetchData')
    })
    
    // const productos = computed(() => store.state.productos)

    // return {productos}
  },

computed: {
    productos() {
      return datos.filter(producto => {
        return producto.nombre.toLowerCase().includes(this.buscar.toLowerCase());
      });
    },
 
  }
  
}
</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=Finlandica:ital@1&display=swap');

body {

  background-color: black
}

.font {

font-family: 'Finlandica', sans-serif;

}

</style>