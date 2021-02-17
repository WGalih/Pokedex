<template>
    <div class="container">
      <SearchPokemon 
        :apiUrl="apiUrl" 
        @setPokemonUrl="setPokemonUrl" />
      <ListPokemon 
        :imgUrl="imgUrl" 
        :apiUrl="apiUrl"
        @setPokemonUrl="setPokemonUrl" />
      <DetailPokemon 
        v-if="showDetail"
        :pokemonUrl="pokemonUrl"
        :imgUrl="imgUrl"
        @closeDetail="closeDetail" />
    </div>
</template>

<script>
  import SearchPokemon from './SearchPokemon.vue';
  import ListPokemon from './ListPokemon.vue';
  import DetailPokemon from './DetailPokemon.vue';
  export default {
    data: () => {
      return {
        imgUrl: 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/',
        apiUrl: 'https://pokeapi.co/api/v2/pokemon/',
        pokemonUrl: '',
        showDetail: false
      }
    },
    components: {
      SearchPokemon,
      ListPokemon,
      DetailPokemon
    },
    methods: {
      setPokemonUrl(url) {
        this.pokemonUrl = url;
        this.showDetail = true;
      },
      closeDetail() {
        this.pokemonUrl = "";
        this.showDetail = false;
      }
    }
  }
</script>

<style lang="scss" scoped>
  @import url('https://fonts.googleapis.com/css2?family=Poppins&display=swap');
  .container {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    padding: 10px;
    width: calc(100% - 20px);
    min-height: calc(100vh - 20px);
    padding-top: 50px;

    font-family: 'Acme', arial;
    font-size: 1rem;
    font-weight: normal;
  }
</style>