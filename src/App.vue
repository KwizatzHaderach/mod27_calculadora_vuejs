<script setup>
    import { reactive } from 'vue';
    import Cabecalho from './components/Cabecalho.vue';
    import Calculadora from './components/Calculadora.vue';
    import Total from './components/Total.vue';

    const estado = reactive({
      numero1: '',
      numero2: '',
      filtro: 'soma',
      total: '',
    })


    const soma =() => {
      const totalSoma = +estado.numero1  + +estado.numero2
      estado.total = totalSoma;
      return estado.total
    }

    const subtracao = () => {
      const totalSub = estado.numero1 - estado.numero2
      estado.total = totalSub;
      return estado.total
    }

    const multiplicacao = () => {
      const totalMulti = estado.numero1 * estado.numero2
      estado.total = totalMulti;
      return estado.total
    }
    const divisao = () => {
      const totalDiv = estado.numero1 / estado.numero2
      estado.total = totalDiv;
      return estado.total
    }


</script>

<template>  

    <div class="container">
        <Cabecalho/>
        <Calculadora :trocar-filtro="evento => estado.filtro = evento.target.value" :valor1=" evento => estado.numero1 = evento.target.value" :valor2=" evento => estado.numero2 = evento.target.value"/>
        <Total :filtro="estado.filtro" :somar="soma()" :subtrair="subtracao()" :multiplicar="multiplicacao()" :dividir="divisao()"/>
    </div>
</template>