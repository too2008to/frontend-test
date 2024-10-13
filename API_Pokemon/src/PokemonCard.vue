<script setup>
import { ref } from 'vue'
import axios from 'axios'
import PokemonCard from './components/PokemonCard.vue'

const pokemons = ref([])
const loading = ref(false)

const fetchPokemonList = async () => {
  loading.value = true
  try {
    const response = await axios.get('https://pokeapi.co/api/v2/pokemon?offset=0&limit=151')
    const results = response.data.results

    const promises = results.map(async (pokemon) => {
      const details = await axios.get(pokemon.url)
      return details.data
    })

    pokemons.value = await Promise.all(promises)
  } catch (error) {
    console.error('Error fetching Pokémon data:', error)
  } finally {
    loading.value = false
  }
}
</script>

<template>

  
  <div class="min-h-screen bg-base-200 p-8">
    <h1 class="text-4xl font-extrabold text-center text-primary mb-6">API Pokémon</h1>
    <button
      @click="fetchPokemonList"
      class="btn btn-primary mb-8 mx-auto block w-52"
      :disabled="loading"
    >
      {{ loading ? 'Loading...' : 'Get Pokémon Dex' }}
    </button>

    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
      <PokemonCard v-for="pokemon in pokemons" :key="pokemon.id" :pokemon="pokemon" />
    </div>
  </div>


</template>


