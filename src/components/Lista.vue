<script setup>
const pokemon = defineProps(["name", "url"])
</script>

<template>
    <div class="col-4">
        <div class="card mb-4">
            <h3 class="text-center">{{pokemon.name}}</h3>
            <img :src="url" alt="pokemon">
        </div>
    </div>
</template>

<style scoped>
.card img {
    height: 80vh;
    background-color: #a9c2c9;
}
.card{
    background-color: #c5f7f0;
}
h3 {
    text-transform: uppercase;
    font-weight: bold;
    
}
</style>