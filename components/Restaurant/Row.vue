<template>
    <div :class=" (rank < 25 && rank%2 === 1 &&'bg-slate-100') || (rank > 25 && rank % 2 === 0 &&'bg-slate-100') "
        class="flex gap-5 px-2 py-2 border-b-2">
        <h4 class="">{{rank}}</h4>
        <NuxtLink :to="`/restaurants/${name}`" class="text-yellow-700 text-xl">{{name}}</NuxtLink>
    </div>
</template>

<script setup lang="ts">
const props = defineProps<{ rank: number, name: string }>();

</script>