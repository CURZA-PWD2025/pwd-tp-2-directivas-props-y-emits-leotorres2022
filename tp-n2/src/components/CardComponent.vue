<template>
    <div class="peliculas">

<h2>Id:{{ props.movie.id }}</h2>
<h2>Titulo:{{ props.movie.titulo}}</h2>
<h3>Año:{{ props.movie.anio }}</h3>
<h3>Generos:{{ props.movie.generos }}</h3>

<h3>Director :{{ props.movie.director}}</h3>
<img :src="props.movie.portada" alt="" height="500" width="300" />  
<br> 
<button @click="DarLike" color="blue">
             {{ props.movie.likes }}
        </button>
      </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import type { Pelicula } from '../interfaces/Pelicula';
const props = defineProps <{movie:Pelicula}>()
const emit = defineEmits(['update-likes']);
const isLiked = ref(false); 


const DarLike= () => {
    isLiked.value = !isLiked.value;
    if (isLiked.value) {
        props.movie.likes++;
    } else {
        props.movie.likes--;
    }
    emit('update-likes', props.movie.likes);
};



</script>

<style scoped>
.peliculas {
    border: 1px solid black;
    padding: 10px;
    margin: 10px;
    border-radius: 5px;
    background-color: #f9f9f9;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}
.peliculas h2 {
    color: #333;
    font-size: 1.5em;
    margin: 5px 0;
}
</style>