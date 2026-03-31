<script setup>
  import { reactive } from 'vue';
  import Layout from './components/Layout.vue';



const estado = reactive({
  number1: 0,
  number2: 0,
  operacao: '',    
})

const getOperacao = () => {
  const a = +estado.number1;
  const b = +estado.number2;

  switch (estado.operacao) {
    case 'soma': return a + b;
    case 'subtracao': return a - b;
    case 'divisao': return a / b;
    case 'multiplicacao': return a * b;
    default: return a + b;
  }
}

</script>

<template>
  <div class="container">
    <Layout :numero-um="evento => estado.number1 = +evento.target.value" 
      :numero-dois="evento => estado.number2 = +evento.target.value"
      :trocar-operacao="evento => estado.operacao = evento.target.value"
      :resultado="getOperacao()"/>
    
  </div>
</template>

