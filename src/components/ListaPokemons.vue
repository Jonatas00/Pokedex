<script setup>
import { computed, ref } from 'vue';

const pokemons = defineProps(["pokemons"])
const urlBaseImagem = `https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/`
const searchPokemonField = ref("")
const pokemonsFiltered = computed(() => {
  if (pokemons.pokemons && searchPokemonField.value) {
    return pokemons.pokemons.filter( pokemon => pokemon.name.includes(searchPokemonField.value.toLowerCase()))
  }
  return pokemons.pokemons
})

</script>
<template>
  <div class="container">
    <input type="text" v-model="searchPokemonField" placeholder="Pesquise pelo nome do pokemon">
    <div class="listaPokemons">
      <div class="cardPokemon" v-for="pokemon in pokemonsFiltered">
        {{ pokemon.name }}
        <img :src="urlBaseImagem + pokemon.url.split('/')[6] + '.png'" :alt="pokemon.name" width="200">
      </div>
    </div>
  </div>
</template>
<style scoped>
  .container {
    width: 85%;
    margin: 0 auto;
    background-color: #222;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  input {
    width: 70%;
    height: 50px;
    text-align: center;
    font-size: 16px;
    margin: 15px;
    border-radius: 10px;
    outline: none;
    border:none;
  }
  input:focus {
    border: 2px solid rgb(207, 132, 132);
  }
  .listaPokemons {
    overflow-y: scroll;
    overflow-x: hidden;
    display: flex;
    padding: 5px;
    justify-content: center;
    flex-wrap: wrap;
    gap: 10px;
    height: calc(100vh - 200px);
    width: 100%;
  }
  .cardPokemon {
    border: 1px solid #222;
    background-color: whitesmoke;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    text-align: center;
    flex-wrap: nowrap;
    padding: 15px;
    max-height: 250px;
  }
  .container, .cardPokemon {
    border-radius: 10px;
  }

  /* Scroll Bar */
  ::-webkit-scrollbar {
    width: 20px;
  }
  ::-webkit-scrollbar-track {
    box-shadow: inset -1px 0 5px rgb(207, 201, 201);
    border-radius: 5px;
  }
  ::-webkit-scrollbar-thumb {
    background: rgb(255, 255, 255);
    border-radius: 5px;
    border: 1px solid rgb(248, 153, 153);
  }
</style>