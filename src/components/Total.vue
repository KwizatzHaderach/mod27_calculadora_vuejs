
<script setup>
    const props = defineProps(['filtro', 'somar', 'subtrair', 'multiplicar', 'dividir'])
</script>

<template>
    <div class="row">
        <div class="">
            <p class="">Resultado =</p>
            <div class="">
                <p class="mt-10 fw-bold" v-if="props.filtro === 'soma'">{{ props.somar }}</p>
                <p class="mt-10 p-2 fw-bold" v-else-if="props.filtro === 'subtracao'">{{ props.subtrair }}</p>
                <p class="mt-10 p-2 fw-bold" v-else-if="props.filtro === 'multiplicacao'">{{ props.multiplicar }}</p>
                <p class="mt-10 p-2 fw-bold" v-else>{{ props.dividir }}</p>
            </div>
        </div>
    </div>
</template>