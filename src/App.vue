<template>
  <div id="app">
    <img class="logo" src="./assets/LogoPokemon.png" alt="Logo Pokemon">
    <Pokemon />
  </div>
</template>

<script>
import Pokemon from './components/Pokemons.vue'

export default {
  name: 'App',
  components: {
    Pokemon
  }
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Poppins&display=swap');
  body{
    margin: 0;
    padding: 0;
    margin-top: 30px;
    background: #EFEFBB;
    background: -webkit-linear-gradient(to right, #D4D3DD, #EFEFBB);
    background: linear-gradient(to right, #D4D3DD, #EFEFBB);
  }

  .logo {
    display: block;
    height: 100px;
    margin-left: auto;
    margin-right: auto;
  }
</style>
