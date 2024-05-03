<script setup>

import { reactive } from 'vue';

const estado = reactive({
  num1: '',
  num2: '',
  operacao: '',
  resultado: 0
});

const calcular = () => {
  if (estado.operacao === 'somar') {
    estado.resultado = estado.num1 + estado.num2;
  } else if (estado.operacao === 'multiplicar') {
    estado.resultado = estado.num1 * estado.num2;
  } else if (estado.operacao === 'dividir') {
    estado.resultado = estado.num1 / estado.num2;
  }
};

</script>

<template>
  
  <div class="container">
    <header class="mt-3 p-5 bg-dark rounded-3">
      <h1 class="text-danger mb-3">Calculadora aritmética</h1>
      <p class="text-white">
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Laborum, vel delectus tenetur ut, magnam atque provident temporibus molestias
      </p>
      <form @submit.prevent="calcular">
        <div class="row">
          <div class="col-5">
            <input v-model="estado.num1" class="form-control" type="number" placeholder="Digite um número">
          </div>
          <div class="col-5">
            <input v-model="estado.num2" class="form-control" type="number" placeholder="Digite outro número">
          </div>
          <div class="col-2">
            <select v-model="estado.operacao" class="p-1" name="" @change="calcular">
              <option value="">Operações</option>
              <option value="multiplicar">Multiplicar</option>
              <option value="somar">Somar</option>
              <option value="dividir">Dividir</option>
            </select>
          </div>
        </div>
        <span class="text-white text-center mt-3 fs-3">
          Resultado: {{ estado.resultado }}
        </span>
      </form>
    </header>
  </div>
  
</template>

<style scoped>

</style>
