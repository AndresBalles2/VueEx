<script setup>
    import { ref } from "vue";
    
    const isChecked = ref(true)

    const users = [ "Pepe", "Ana", "Juana", "Lola " ]
</script>

<template>

    <div class=" ml-[700px] mt-[400px] bg-slate-200 max-w-[600px] p-14 rounded-xl hover:cursor-pointer hover:bg-slate-300 bg">

        <input type="checkbox" id="check" v-model="isChecked" />
        <label for="check" class="font-semibold select-none"> Clic</label>

        <div class="bg-slate-500 text-white rounded-md py-1 px-2 max-w-[125px] my-2 font-medium select-none"
        :class="{'bg-green-500': isChecked }">
            This is a message
        </div>

        <div v-if="isChecked" class="font-semibold text-blue-500">
            Nice!😀
        </div>

        <div v-else class="font-semibold text-red-500">
            You can see it 'cause didn't comply the "if" 😭
        </div>

        <ul class="flex gap-5">
            <li v-for="( user , index ) in users" :key="index">

                {{ index }} {{ user }}

            </li>
        </ul>

    </div>
    
</template> 