<script setup>


import { ref, onMounted } from 'vue'


const pokemonList = ref([])


const loadPokemon = async () => {
  try {
    const response = await fetch('https://pokeapi.co/api/v2/pokemon?limit=5')
    const data = await response.json()
    const pokemonData = await Promise.all(
      data.results.map(async (pokemon) => {
        const res = await fetch(pokemon.url)
        return await res.json()
      })
    )
    pokemonList.value = pokemonData
  } catch (error) {
    console.error('Failed to load Pokémon:', error)
  }
}


onMounted(loadPokemon)


</script>

<template>
  <div>
    <div
      v-for="pokemon in pokemonList"
      :key="pokemon.id"
      class="card w-full max-w-sm mx-auto shadow-lg bg-white border border-gray-200 rounded-xl overflow-hidden hover:shadow-2xl transition-all duration-300 ease-in-out"
    >
      <div>
        <div>
          <img
            :src="pokemon.sprites.front_default"
            :alt="pokemon.name"
          />
          <img
            :src="pokemon.sprites.back_default"
            :alt="pokemon.name"
          />
        </div>
      </div>
      <div>
        <h2>
         Name : {{ pokemon.name }}
        </h2>
        <div>
          <p>Type 1 :  
            <span>{{ pokemon.types[0]?.type.name }}</span>
          </p>
          <p v-if="pokemon.types[1]">
            Type 2 : <span>{{ pokemon.types[1]?.type.name }}</span>
          </p>
        </div>
        <p>Base stats </p>
        <div>
          <p>HP = {{ pokemon.stats[0].base_stat }}</p>
          <p>Attack = {{ pokemon.stats[1].base_stat }}</p>
          <p>Defense = {{ pokemon.stats[2].base_stat }}</p>
          <p>Special-Attack = {{ pokemon.stats[3].base_stat }}</p>
          <p>Special-Defense = {{ pokemon.stats[4].base_stat }}</p>     
          <p>Speed = {{ pokemon.stats[5].base_stat }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

