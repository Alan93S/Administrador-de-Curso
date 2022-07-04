<template>
  
  <div>
    
      <div>
    <router-view/>
      </div>

      <Footer/>
  </div>
</template>

<script>

import NavBar from "@/components/NavBar.vue"
import Footer from "@/components/Footer.vue"
export default {

components: {

  NavBar, Footer
},


}
</script>

<style>


body {
  background-color: lightblue;
}
</style>
