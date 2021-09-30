<template>
 <div class="container">
   <h1 class="mt-5 fuente animate__animated animate__flash">{{nombre}}</h1>
   <div class="p-3 cuerpo" style="max-width: 400px; margin: 50px auto; background: #234">
      <div class="w-full rounded m-1 p-3 text-right lead font-weight-bold text-white valor bg-dark" >
          <div>{{valorPrevio}}</div>
          {{calculadorValor || 0}}
      </div>

      <!----CALCULADORA BOTONES--->

      <div class="row no-gutters">
          <div class="col-3" v-for="n in calculadorElem" :key="n">
              <div class="lead text-white text-center m-1 py-3 bg-vue-dark rounded hover-class" :class="{'color': ['C', '*', '/', '-', '+', '%', '=',].includes(n)}"
              @click="accion(n)">
                  {{n}}
              </div>
          </div>
      </div>
   </div>
 </div> 
</template>

<script>
export default {
    data() {
        return {
            nombre: 'Calculadora con vue',
            calculadorValor: '',
            calculadorElem: ['C','*','/','-',7,8,9,'+',4,5,6,'%',1,2,3,'=',0,'.'],
            operador: null,
            valorPrevio: '',
        }
    },
    methods:{
        accion(n){
            if(!isNaN(n) || n === '.'){
                this.calculadorValor += n + '';
            }

            if(n === 'C'){
                this.calculadorValor = '';
            }

            if(n === '%'){
                this.calculadorValor = this.calculadorValor / 100 + ''; 
            }

            if(['/', '*', '-', '+'].includes(n)){
                this.operador = n;
                this.valorPrevio = this.calculadorValor;
                this.calculadorValor = '';
            }

            if(n === '='){
                this.calculadorValor = eval(
                    this.valorPrevio + this.operador + this.calculadorValor
                );

                this.valorPrevio = '';
                this.operador = null;
            }
        }
    }
}
</script>

<style scoped>

    body{
        background: #a13131;
    }

    .fuente{
        font-family: 'Poppins', sans-serif;
    }

    .cuerpo {
        border-radius: 10px;
    }

    .valor{
        height: 95px;
    }

    .bg-vue-dark{
        background: #31475e;
    }
    .hover-class:hover{
        cursor: pointer;
        background: #3d5875;
    }

    .color{
        background: #27ae60;
    }

    .color:hover{
        background: #2ecc71;
    }
</style>