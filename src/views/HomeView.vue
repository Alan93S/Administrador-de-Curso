<template>
<div>

<NavBar/>
  
  <div>
             <link rel="preconnect" href="https://fonts.googleapis.com">
            <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
            <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300&display=swap" rel="stylesheet">
    </div>
  <div>
    <h1 class="font-sub">
      Bienvenidos a Adweb Online
    </h1>
  </div>
  <hr>
  <br>
  <div>
      <h3 class="font-sub">
            Seleccione cualquier curso para comenzar a administrar.
      </h3>
  </div>
  <div>
  <Cursos/>
    </div>

    </div>
</template>

<script>
import Cursos from '/src/components/Cursos'
import NavBar from '/src/components/NavBar'
export default {

components: {

    Cursos, NavBar

    }
}
</script>

<style>

.title {
    text-align: center;
    font-family: 'Roboto', sans-serif;
    color: white
}

.subtitle {

  text-align: center;
    font-family: 'Roboto', sans-serif;
    color: white
}

@import url('https://fonts.googleapis.com/css2?family=Finlandica:ital,wght@1,700&display=swap');

.font-sub {font-family: 'Finlandica', sans-serif;
 text-align: center;
 color: white;}

 body {

  background-color: black;
 }

</style>