<script setup>

import { reactive } from 'vue';

const calc = reactive({
      operacao: '+',
      valor1: '',
      valor2: '',
      resultado:'0'
})


const calculadora = () => {
    switch(calc.operacao){

      case '+':
      calc.resultado = calc.valor1 + calc.valor2
      break;

      case '-':
      calc.resultado = calc.valor1 - calc.valor2
      break;

      case 'x':
      calc.resultado = calc.valor1 * calc.valor2
      break;

      case '/':
      calc.resultado = calc.valor1 / calc.valor2
      break;

      default:
        calc.resultado = 0

    }
} 

</script>

<template>
  <div class="container">
    <h1 class="pt-4 pb-5">Calculdor Aritimética</h1>
    <div class="row">
      <div class="col-2">

        <input id="nbm1" class="form-control
        " type="number"  v-model="calc.valor1" @input="calculadora()">
      </div>
      <div class="col-1 ">
        <select class="form-control" v-model="calc.operacao" @change="calculadora()">
          <option class="operation" value="+">+</option>
          <option class="operation" value="-">-</option>
          <option class="operation" value="x">x</option>
          <option class="operation" value="/">/</option>
        </select>
      </div>
      <div class="col-2">
        <input id="nbm2" class="form-control
        " type="number" v-model="calc.valor2" @input="calculadora()">
      </div>
      <div class="col-md-2">
        <span>
          {{calc.resultado}}
        </span>

      </div>
    </div>
  </div>
</template>

<style scoped>
  .operation{
    text-align: center;
  }
  span{
    font-size: 28px;
    font-weight: bold;
  }
</style>
