<template>
    <div>

<h2>Id:{{ props.movie.id }}</h2>
<h2>Titulo:{{ props.movie.titulo}}</h2>
<h2>Año:{{ props.movie.anio }}</h2>
<h2>Generos:{{ props.movie.generos }}</h2>
<h2>Director:{{ props.movie.director}}</h2>
<img :src="props.movie.portada" alt="">  
<br> 
<button @click="" color="blue">Likes:{{ props.movie.likes}}</button>

      </div>
</template>

<script setup lang="ts">

import type { Pelicula } from '../interfaces/Pelicula';
const props = defineProps <{movie:Pelicula}>()




</script>

<style scoped>

</style>