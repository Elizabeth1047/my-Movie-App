<script setup>
 import Moviecards from './Moviecards.vue'
const { movies } = defineProps({
    movies: Array
})
</script>


<template>
    <div class="bg-black">
    <div class="flex w-[95%] m-auto gap-10  mx-8  md:mx-15 py-10 overflow-x-auto scrollbar-hide  ">
       <Moviecards
           v-for="movie in movies"
           :key="movie"
           :movie="movie"/>
        </div>
        <div class="flex w-[95%] m-auto gap-10 mx-8 md:mx-15 my-10 overflow-auto scrollbar-hide">
       <Moviecards
           v-for="movie in movies"
           :key="movie"
           :movie="movie"/>
        </div>
        <div class="flex w-[95%] m-auto gap-10 mx-8 md:mx-15 my-10 overflow-auto scrollbar-hide">
       <Moviecards
           v-for="movie in movies"
           :key="movie"
           :movie="movie"/>
        </div>
        </div>
</template>