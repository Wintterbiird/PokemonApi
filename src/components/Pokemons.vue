<script>
export default {
  props: ["pokemon", "index"],
  
};
</script>

<template>
  <div class="pokemon">
    <img :src="pokemon.img" alt="uno de los mil pokémones" :class="{ filter: !pokemon.nitido }" class="img-poke"/>
    
    <p v-show="pokemon.nitido">{{ pokemon.name }}</p>
    <input v-show="!pokemon.nitido" @keyup.enter="$emit('pokemonEncontrado', index)" type="text" v-model="pokemon.input"/>
    <button class="my-2" v-show="!pokemon.nitido" @click="$emit('pokemonEncontrado', index)"> Descubrir </button>
  </div>
</template>

<style scoped>
.pokemon{
  display: flex;
  flex-direction: column;
}

.filter {
  filter: grayscale(100%) blur(5px);
}

.img-poke {
  height: 100px;
}

button {
  border: none;
  background-color: #1c2b5e;
  color: #fff;
  border-radius:20px;
  padding:.5rem;
}

p {
  text-align: center;
}
</style>