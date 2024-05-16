<script setup>

import { ref } from "vue";
import IconGrid from './IconGrid.vue'
import Buguesa from './Buguesa.vue'

const isChecked = ref(true)

const users = ["Pepe", "Ana", "Juana", "Lola ", "Kactuswow", "andreswow"]

function changeToTrue() {
    isChecked.value = true
}


function changeToFalse() {
    isChecked.value = false
}

</script>

<template>


    <main class="max-w-xl w-full">

        <div class="flex justify-end gap-3 mb-2 text-gray-500">
            <button @click="changeToTrue" :class="{ 'text-green-500 bg-gray-300 rounded-md': isChecked }">
                <IconGrid></IconGrid>
            </button>
            <button @click="changeToFalse" :class="{ 'text-green-500 bg-gray-300 rounded-md': !isChecked }">
                <Buguesa></Buguesa>
            </button>
        </div>

        <section class=" grid gap-4" :class="{ 'grid-cols-3': isChecked }, { 'grid-cols-1': !isChecked }">
            <div v-for="(user, index) in  users " class="bg-green-200 p-2"
                :class="{ 'h-40': isChecked }, { 'flex gap-3 items-center': !isChecked }">
                <div class="bg-white " :class="{ 'w-full h-20': isChecked }, { 'w-10 h-10': !isChecked }">
                </div>
                <p class="underline">{{ user }}</p>
            </div>
        </section>
    </main>

</template>