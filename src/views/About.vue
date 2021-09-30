<template>
  <div class="about">
    <header class="header" id="header">
      <a href="#modal" class="cta animate__animated animate__heartBeat">Dame click</a>
    </header>

    <section class="modal" id="modal">
      <div class="modal-container">
        <figure class="modal-picture">

          <img src="../assets/ilustration.svg" class="modal-img">

          <h2 class="modal-title">¡Buen trabajo!
            <span class="modal-title-bold color">Usuario</span>
          </h2>
          <p class="modal-p">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Vitae illum sequi qui aspernatur perferendis Lorem ipsum dolor sit.</p>

          <a href="#header" class="modal-close">Estoy de acuerdo</a>

        </figure>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  
}
</script>

<style scoped>

@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;500;700&display=swap');

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body{
  font-family: 'Montserrat', sans-serif; 
}

.header{
  display: flex;
  height: 100vh;
  widows: 100%;
}

.cta{
  margin: auto;
  background-color: #00b894;
  color: #ffffff;
  text-decoration: none;
  padding: 1.2rem 3rem;
  border-radius: .4rem;
  transition: all .4s ease;
}

.cta:hover{
  background-color: #55efc4;
}

.modal{
  position: fixed;
  background-color: #333;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  display: flex;

  --opacity: 0;
  --pointer:none;

  opacity: var(--opacity);
  pointer-events: var(--pointer);
  transition: opacity .5s;
}

.modal:target{
  --opacity: 1;
  --pointer:unset;
}

.modal-container{
  margin: auto;
  background: #ffffff;
  width: 90%;
  max-width: 600px;
  max-height: 90%;
  overflow: hidden;
  text-align: center;
  padding: 2.5rem 1.5rem;
  border-radius: 1rem;
}

.modal:target .modal-container{
  animation: show 1s;
}

@keyframes show {
  0%{
    transform: translateY(-150vh);
  }

  100%{
    transform: translateY(0);
  }
}

.modal-picture{
  width: 90%;
  margin: 0 auto;
  max-width: 400px;
  margin-bottom: 2rem;
}

.modal-img{
  width: 100%;
  display: block;    
}

.modal-title{
  font-size: 2.5rem;
  font-weight: 500;
}

.modal-title-bold{
  font-weight: 700;
}

.color{
  color: #333;
}

.modal-p{
  margin-top: 1rem;
  margin-bottom: 1rem;
  line-height: 1.5rem;
}

.modal-close{
  border: 1px solid;
  padding: 1rem 3rem;
  text-decoration: none;
  font-weight: 700;
  color: #333;
  border-radius: .4rem;
  transition: all .4s ease;
}

.modal-close:hover{
  color: #ff7675;
}

</style>
