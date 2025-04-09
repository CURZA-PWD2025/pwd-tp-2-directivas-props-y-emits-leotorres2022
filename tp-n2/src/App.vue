<template>
    <CardComponent v-for="list in peli" :movie="list" />


</template>

<script setup lang="ts">
import type { Pelicula } from './interfaces/Pelicula';
import peliculas from './resource/movies';
import { reactive } from 'vue';
import CardComponent from './components/CardComponent.vue';

let peli : Array <Pelicula> = reactive (peliculas)

</script>
<style scoped>

</style>