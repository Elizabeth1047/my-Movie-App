<script setup>
import { Icon } from "@iconify/vue";
import { RouterLink } from "vue-router";
</script>

<template>
    <nav class="flex text-white items-center gap-20 absolute left-0 right-0 mx-6 
                py-4 top-4 bg-transparent border-b-2 border-neutral-400">
        <div class="flex items-center text-3xl font-bold gap-2">
            <icon icon="mingcute:movie-line" width="40"/>
            <span>Lizzyflix</span>
        </div>  
        <ul class="flex items-center font-semibold gap-4">
            <li>Home</li>
            <li>Movies</li>
        </ul>  
        
    </nav>
</template>