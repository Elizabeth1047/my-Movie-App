<script setup>
 import Moviecards from './Moviecards.vue'
const { movies } = defineProps({
    movies: Array
})
</script>


<template>
    <div class="bg-black">
    <div class="flex w-[90%] m-auto gap-10  mx-20 py-10 overflow-x-auto scrollbar-hide px-5 ">
       <Moviecards
           v-for="movie in movies"
           :key="movie"
           :movie="movie"/>
        </div>
        <div class="flex w-[90%] m-auto gap-10 mx-20 my-10 overflow-auto scrollbar-hide  px-5">
       <Moviecards
           v-for="movie in movies"
           :key="movie"
           :movie="movie"/>
        </div>
        <div class="flex w-[90%] m-auto gap-10 mx-20 my-10 overflow-auto scrollbar-hide  px-5">
       <Moviecards
           v-for="movie in movies"
           :key="movie"
           :movie="movie"/>
        </div>
        </div>
</template>