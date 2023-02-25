<script setup>
import { ref, onBeforeMount , defineAsyncComponent } from 'vue'
 import AsyncBanner from '../components/Banners.vue';
 import Movielist from '../components/Movielist.vue';


 
const movies=ref([])
const bannermovie=ref(null)

  


const getmovie= async ()=>{
  movies.value=await fetch("https://api.themoviedb.org/3/movie/popular?api_key=6626dee37dbdb674157044e41e9f3c88&language=en-US")
  .then(res=>res.json())
  .then(res=>res.results)
}



const getRandomInt=(min, max)=>{
return Math.floor(Math.random() * (max - min) + min)
}
 onBeforeMount(async()=>{
    await getmovie()
   bannermovie.value=movies.value[getRandomInt(0, movies.value.length-1)]
   
 })

</script>






<template>
  <AsyncBanner :banner="bannermovie"/>
  <Movielist
  :movies="movies"/>
</template>