<template >
  <div class="listado"> 
    <CardComponent v-for="list in peli" :movie="list" @update-likes="handleUpdateLikes(list.id)" />
    </div >  
    

</template>

<script setup lang="ts">
import type { Pelicula } from './interfaces/Pelicula';
import peliculas from './resource/movies';
import { reactive } from 'vue';
import CardComponent from './components/CardComponent.vue';

const peli: Array<Pelicula> = reactive(peliculas);
   
    const handleUpdateLikes = (index: number) => (value: number) => {
    peli[index].likes += value }
</script>
<style scoped>
.listado {
    display: grid;
    grid-template-columns: repeat(3, 1fr); 
    gap: 10px; 
    padding: 10px; 
}

</style>