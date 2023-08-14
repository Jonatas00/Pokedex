<script setup>
const pokeAPI = "https://pokeapi.co"
</script>
<template>
  <div class="container">
    <h1>Sobre o projeto</h1>
    <p>Esse projeto da pokedéx foi feito utilizando a <a :href="pokeAPI" target="_blank">PokeAPI</a></p>
    <p><strong>Framework:</strong> VueJS</p>
  </div>
</template>
<style scoped>
  .container {
    width: 80%;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 25px;
  }
</style>
