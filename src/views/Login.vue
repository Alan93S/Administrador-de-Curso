<template>


<div>
<div class="card mb-3">
    <div class="row g-0 d-flex align-items-center">
      <div class="col-lg-4 d-none d-lg-flex">
        <img src="https://mdbootstrap.com/img/new/ecommerce/vertical/004.jpg" alt="Trendy Pants and Shoes"
          class="w-100 rounded-t-5 rounded-tr-lg-0 rounded-bl-lg-5" />
      </div>
      <div class="col-lg-8">
        <div class="card-body py-5 px-md-5">

          <form action class="form" @submit.prevent="login">
            <!-- Email input -->
            <div class="form-outline mb-4">
              <input
              v-model="email"
               type="email" 
               id="email" 
               class="form-control" 
               required
               placeholder="Ingrese su correo o usuario" />
              <label class="form-label" for="#email" >Correo Electronico</label>
            </div>

            <!-- Password input -->
            <div class="form-outline mb-4">
              <input v-model="password" type="password" id="password" class="form-control"  placeholder="Ingrese su contraseña"/>
              <label class="form-label" for="#password">contraseña</label>
            </div>

            <!-- 2 column grid layout for inline styling -->
            <div class="row mb-4">
              <div class="col d-flex justify-content-center">
                <!-- Checkbox -->
                <div class="form-check">
                  <input class="form-check-input" type="checkbox" value="" id="form2Example31" checked />
                  <label class="form-check-label" for="form2Example31"> Recordar datos </label>
                </div>
              </div>

              <div class="col">
                <!-- Simple link -->
                <a href="#!">Olvido Contraseña?</a>
              </div>
            </div>

            <!-- Submit button -->
            <button type="submit" class="btn btn-primary btn-block mb-4" value="Login">Ingresar</button>
            <p v-if="error" class="error">Has introducido mal el email o la contraseña.</p>
         
          </form>

        </div>
      </div>
    </div>
  </div>
  
  <div class="usuario-login">
  <p>Usuario: eve.holt@reqres.in</p>
  <p>clave: pistol</p>
  </div>
  </div>

</template>

<script>
import auth from "@/logic/auth";
export default {
  data: () => ({
    email: "",
    password: "",
    error: false
  }),
  methods: {
   async login() {
  try {
    await auth.login(this.email, this.password);
    const user = {
      email: this.email
    };
    auth.setUserLogged(user);
    this.$router.push("/HomeView");
  } catch (error) {
    console.log(error);
    this.error = true;
  }
}
  }
}
</script>

<style lang="scss" scoped>

.error {

  color: red;
}
.usuario-login{

  background-color:black
  color white;
}
</style>