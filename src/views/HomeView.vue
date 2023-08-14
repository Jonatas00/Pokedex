<script setup>
import ListaPokemons from '../components/ListaPokemons.vue';
import { onMounted, ref} from 'vue';


const pokemons = ref();
async function obterPokemons() {
  const res = await fetch("https://pokeapi.co/api/v2/pokemon?limit=1008&offset=0");
  const pokemons = await res.json();
  return pokemons.results;
}
 
onMounted(async () => {
  const pokemonsObtidos = await obterPokemons();
  pokemons.value = pokemonsObtidos
})

</script>
<template>
  <main>
    <ListaPokemons :pokemons="pokemons"/>
  </main>
</template>
