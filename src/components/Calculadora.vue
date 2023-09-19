<script setup>
const props = defineProps(['valor1', 'valor2', 'trocarFiltro',])
</script>

<template>
    <form @submit.prevent="props.cadastraTarefa">
        <div class="row">
            <div class="mb-3">
                <input @keyup="props.valor1" required type="text" placeholder="Primeiro valor"
                    class="form-control">
            </div>
            <div class="">
                <select @change="props.trocarFiltro" class="form-control">
                    <option value ="soma" >Soma + </option>
                    <option value="subtracao">Subtração - </option>
                    <option value="multiplicacao" >Multiplicação *</option>
                    <option value="divisao">Divisão /</option>
                </select>
                <div class="mt-3">
                    <input @keyup="props.valor2" required type="text" placeholder="Segundo valor"
                        class="form-control">
                </div>
            </div>
        </div>
    </form>
</template>