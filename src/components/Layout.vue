<script setup>
    const props = defineProps(['numeroUm', 'numeroDois', 'resultado', 'trocarOperacao']);
</script>

<template>
    <div class="p-5 mb-4 mt-4 bg-light rounded-3">
        <h1> Calculadora </h1>
        <p> Digite dois números e escolha uma operação</p>
        <div class="row">
            <div class="col-12">
                <input @keyup="props.numeroUm" type="number" placeholder="Digite o primeiro número" class="form-control mt-4">
                <input @keyup="props.numeroDois" type="number" placeholder="Digite o segundo número" class="form-control mt-4">
            </div>
            <div class="col-12 mt-3">
                <select @change="props.trocarOperacao" class="form-control">
                    <option value="soma">Soma</option>
                    <option value="subtracao">Subtração</option>
                    <option value="multiplicacao">Multiplicação</option>
                    <option value="divisao">Divisão</option>
                </select>
            </div>
            <div>
                <h2 class="mt-5 center"> Resultado:                                                                                <br /> {{ resultado }}</h2>
            </div>
        </div>
    </div>
</template>

<style>
.center {
    text-align: center;
    text-transform: uppercase;
    font-size: 20px;
}
</style>