<template>
<div>

    <!-- Navbar -->
<nav class="navbar navbar-expand-lg navbar-light bg-dark" >
  <!-- Container wrapper -->
  <div class="container-fluid" >
    <!-- Toggle button -->
    <button
      class="navbar-toggler"
      type="button"
      data-mdb-toggle="collapse"
      data-mdb-target="#navbarSupportedContent"
      aria-controls="navbarSupportedContent"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <i class="fas fa-bars"></i>
    </button>

    <!-- Collapsible wrapper -->
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <!-- Navbar brand -->
      <a class="navbar-brand mt-2 mt-lg-0" href="#">
        <img
          src="https://www.adwebsolutions.com/wp-content/uploads/2018/12/ADWEB-MOSAICO.png"
          height="30"
          
          alt="MDB Logo"
          loading="lazy"
        />
      </a>
      <!-- Left links -->
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item">
          <a class="font" href=""
              ><router-link to="/HomeView">Home</router-link></a
            >
        </li>
        
      </ul>
      <!-- Left links -->
    </div>
    <!-- Collapsible wrapper -->

    <!-- Right elements -->
    <div class="d-flex align-items-center">
      <!-- Icon -->
      <a class="text-reset me-3" href="#">
        <i class="fas fa-shopping-cart"></i>
      </a>

      <!-- Notifications -->
     
     
      <!-- Avatar -->
      
    </div>
    <!-- Right elements -->


  </div>
  <!-- Container wrapper -->
   <div class="login-sucess">
          <p class="font">Bienvenido Admin</p>

          </div>
           <div class="dropdown">
        <a
          
          href="#"
          id="navbarDropdownMenuAvatar"
          role="button"
          data-mdb-toggle="dropdown"
          aria-expanded="false"
        >
        
          <img
            src="https://cdn.pixabay.com/photo/2017/05/29/23/02/logging-out-2355227_1280.png"
            class="rounded-circle"
            height="25"
            alt="Awake"
            loading="lazy"
          />
        </a>

      </div>
</nav>
<!-- Navbar -->

</div>
</template>

<script>
export default {

};
</script>

<style>

a:link, a:visited,  a:hover, a:active
{ 
    color: #fff;
    text-decoration: none;
}


.login-sucess {

  text-align: center;
  color: white;
  
}

</style>