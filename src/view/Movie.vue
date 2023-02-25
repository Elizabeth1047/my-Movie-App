<script setup>
import { useRouter } from "vue-router";
import Navbar from "../components/Navbar.vue";
import { ref } from "vue";
import { defineAsyncComponent } from "vue";
import getimage from "../lib/getimage";
import { Icon } from "@iconify/vue";
const router = useRouter();
const movieid = router.currentRoute.value.params.id;
console.log(movieid);
const movie=ref(null)




movie.value =  await fetch (`https://api.themoviedb.org/3/movie/${movieid}?api_key=6626dee37dbdb674157044e41e9f3c88&language=en-US`) 
 .then(res=>res.json())
 console.log(movie.value)

const {
  title,
  overview,
  backdrop_path: background,
  poster_path:poster,
  release_date,
  vote_average:vote,
  popularity,
  runtime
} = movie.value;
const Movieduration =
  Math.round(runtime/60)

const description =
  overview.length <= 200 ? overview : overview.slice(0, 200) + "...";
</script>

<template>
  <div class="h-screen w-screen grayscale-0"
   :style="{
    backgroundImage:'url('+getimage(background)+')'
  }">
  <Navbar/>
  <div class="w-full h-full 
      bg-gradient-to-r from-black to-transparent">
      <div class="pt-20 w-full h-full grid grid-cols-2 items-center">
        <img
        :src="getimage(poster)"
        class="w-[400px] mx-auto rounded-lg"
        />
        <div>
            <h1 class="text-4xl font-semibold mb-4">{{ title }}</h1>
            <p class="text-sm text-neutral-300 w-2/3">{{ overview }}</p>
            <div class="flex flex-col text-sm gap-2 mt-3"> 
                <div class="flex items-center gap-2"> 
                    <icon icon="uiw:date"/>
                    <span>{{ release_date }}</span>
                </div>
                <div class="flex items-center gap-2"> 
                    <icon icon="ic:round-star"/>
                    <span>{{Math.round(vote)  }}/10</span>
                </div>
                <!-- <div class="flex items-center gap-2"> 
                    <icon icon="ic:ion:people" color="white"/>
                    <span>{{ popularity }}</span>
                </div> -->
                <div class="flex items-center gap-2"> 
                    <icon icon="ic:twotone-access-time-filled" color="white"/>
                    <span>{{ Movieduration }}hrs/{{ runtime }}mins</span>
                </div>
                
            </div>
        </div>
      </div>
    </div>
  </div>
</template>
