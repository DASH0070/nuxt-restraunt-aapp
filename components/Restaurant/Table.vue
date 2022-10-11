<template>
    <div class="my-12 flex flex-col items-left w-min mx-auto">
        <h1 class="mb-12 text-4xl border-b-4 border-slate-800 pb-4">Top 50 Restaurant</h1>
        <div class="flex gap-10">
            <div class="flex flex-col min-w-min w-96">
                <RestaurantRow v-for="restaurant in restaurantOrganized.first" :key="restaurant.id"
                    :rank="restaurant.rank" :name="restaurant.name"></RestaurantRow>
            </div>
            <div class="flex flex-col min-w-min w-96">
                <RestaurantRow v-for="restaurant in restaurantOrganized.second" :key="restaurant.id"
                    :rank="restaurant.rank" :name="restaurant.name"></RestaurantRow>
            </div>
        </div>
    </div>
</template>

<style scoped>

</style>

<script setup lang="ts">
import restaurants from '../../data.json';
const restaurantOrganized = {
    first: [...restaurants].splice(0, 25),
    second: [...restaurants].splice(25, 25)
}
</script>