<script setup>

import { ref } from 'vue'

const arregloCarros = ref([true, true, false, true, true, true, true, true, true, true])
const arregloMotos = ref([true, true, false, true, true, true, true, true, true, true])
const counter = ref(0)

function changeColor(index, arr, precio) {
    if (!arr[index]) {
        counter.value += precio
    }
    arr[index] = !arr[index]
}

</script>

<template>

    {{ counter }}

    <section class=" grid grid-cols-4 p-3 gap-3">

        <div @click="changeColor(index, arregloCarros, 1000)" v-for="(arr, index) in arregloCarros" class="w-full h-72"
            :class="{ 'bg-green-500': arr }, { 'bg-red-500': !arr }">
        </div>

    </section>

    <section class=" grid grid-cols-4 p-3 gap-3">

        <div @click="changeColor(index, arregloMotos, 500)" v-for="(arr, index) in arregloMotos" class="w-full h-72"
            :class="{ 'bg-green-500': arr }, { 'bg-red-500': !arr }">
        </div>

    </section>

</template>