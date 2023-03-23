<script setup>
import { onMounted, ref, reactive } from 'vue'
import Lista from './Lista.vue';
let pokemons =  reactive(ref());
let url  = ref("https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/")

onMounted(() => {
  fetch("https://pokeapi.co/api/v2/pokemon?limit=649&offset=0")
    .then(res => res.json())
    .then(res => {pokemons.value = res.results})
})


</script>

<template>
  <!-- <ul>
    <li v-for="pokemon in pokemons" :key="pokemon.name">
      {{ pokemon.name }}
    </li>
  </ul> -->
  <div class="card">
    <div class="row">
      <Lista v-for="pokemon in pokemons" 
      :key="pokemon.name"
      :name="pokemon.name"
      :url="url + pokemon.url.split('/')[6] + '.svg'" 
      />
    </div>
  </div>
</template>

<style scoped></style>
