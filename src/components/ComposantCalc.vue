<script setup lang="ts">
import { ref } from "vue";
import BtnCalc from "./BtnCalc.vue"

const nb1 = ref(0);
const modeDecimal = ref(false);
const rang = ref(0);   

function increment()
{
    nb1.value+=1;
}

function decrement()
{
    nb1.value-=1;
}
</script>

<template>
    <h1>Calculatrice</h1>
    <p>Résultat: {{ nb1 }}</p>
    <div class="grid grid-cols-3 grid-rows-3 gap-5">
        <BtnCalc v-for="chiffre in 9" v-model="nb1" :value ="chiffre" :modeDecimal="modeDecimal"/>
        <button @click="nb1=0">Clear</button>
        <BtnCalc v-model="nb1" :value="0" />
        <button @click="nb1 = Math.floor(nb1 /10)"><</button>
    </div>
</template>