<script setup lang="ts">

import "@vueform/multiselect/themes/default.css";
import { ref } from "vue"
import Multiselect from '@vueform/multiselect'
const props = defineProps<{
    personne: PersonneResponse[];
    name: string;
    value: string[];
    multiple: boolean;
    placeholder: string;
}>();

const personneId = ref(props.value)

</script>

<template>
    <Multiselect 
        v-model="personneId"
        :options="personne"
        :searchable="true"
        :mode="multiple ? 'tags' : 'single'"
        label="nom"
        value-prop="id"
        :placeholder="placeholder"
    />
    Valeur : {{ personneId }}
    <input v-for="p in multiple ? personneId : [personneId]" type="hidden" :value="p" :name="name" :key="p" />
    <!-- <input v-else type="hidden" :value="personneId" :name="name" /> -->
</template>