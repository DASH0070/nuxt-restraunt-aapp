<template>
    <div>
        <Html>
            <Head>
                <Title v-if="restaurant">{{restaurant.name}}</Title>
                <Title v-else>{{'ERROR'}}</Title>
            </Head>
        </Html>
        <div v-if="restaurant" class="flex items-start">
            <img :src="restaurant.imageUrl" class="w-[50%] flex-grow mx-auto" />
            <div class=" w-[90%] flex flex-col mt-10 px-10 items-start gap-10">
                <h1 class="text-5xl text-yellow-600">{{ restaurant.rank + ' ' + restaurant.name}}</h1>
                <div class="flex gap-10 items-center">
                    <p class="text-2xl text-blue-600">Revenue(in billion): <br /> ${{restaurant.revenue}}</p>
                    <p class="text-2xl text-green-600">Number of Stores: <br /> {{restaurant.numberOfStores}}</p>
                </div>
                <p class="text-slate-700 text-lg">{{restaurant.content}}</p>
            </div>
        </div>
        <NuxtLayout name="error" v-else></NuxtLayout>
    </div>
</template>

<script setup lang="ts">
import restaurants from '../../data.json';
const route = useRoute();
const name = route.params.name;
const restaurant = restaurants.find((r) => r.name === name);
</script>