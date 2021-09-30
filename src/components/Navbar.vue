<template>
  <!-- Image and text --> 
<nav class="navbar navbar-light bg text-light">
  <a class="navbar-brand d-flex" href="#">
    <img src="../assets/logo.png" width="30" height="30" class="d-inline-block align-top my-1 mr-2" alt="">
    <h2 class="navbar-brand text-light">Proyect Vue</h2>
  </a>

  <div class="d-flex font">
  <router-link to="/" class="nav-link">Home</router-link> 
  <router-link to="/about" class="nav-link">Modal</router-link> 
  <router-link to="/calculadora" class="nav-link">Calculadora</router-link>

  </div>
</nav>
</template>

<script>
export default {

}
</script>

<style scoped>
  .bg{
    background: #2d3436;
  }

  .nav-link{
    font-weight: 700;
    color: white;
    text-decoration: none;
    transition: 0.4s ease;
  }

  .nav-link:hover{
    color: #2ecc71;
  }

</style>