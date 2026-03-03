<script setup lang="ts">
const props = defineProps<{
    value: number;
}>();
const nb1 = defineModel<number>();
</script>

<template>
    <button class="bg-red-400 rounded-full p-2 active:bg-blue-400" @click="nb1 = (nb1 ?? 0) * 10 + value">{{ value }}</button>
</template>