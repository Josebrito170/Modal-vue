<template>
    <div class="container text-center">
      <h1 class="animate__animated animate__backInDown fuente">Bienvenidos a un poco de Vue cli con carencia de creatividad</h1>
    </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  }
}
</script>

<style scoped>
  
  .fuente{
    margin-top: 250px;
    font-size: 70px;
    font-family: 'Poppins', sans-serif;
  }

</style>
