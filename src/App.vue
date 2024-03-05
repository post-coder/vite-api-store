<script>
// per importare axios (dopo essere stato installato) 
import axios from 'axios';

// importiamo lo store
import {store} from './store.js';

import CharactersList from './components/CharactersList.vue';
import CharacterSearch from './components/CharacterSearch.vue';

export default {

  

  data() {
    return {
      characters: [],

      // dichiariamo lo store, utilizzabile nel nostro componente
      store,
    }
  },

  created() {
    // spazio di codice che viene eseguito appena l'applicazione viene lanciata
    
    axios
      .get('https://rickandmortyapi.com/api/character?page=42')
      .then(res => {
        console.log(res.data.results)
        this.store.characters = res.data.results
    }).catch(err => {

      console.log(err)

    })

  },

  components: {
    CharactersList,
    CharacterSearch,
  },

  methods: {

    searchCharacters() {

      axios.get('https://rickandmortyapi.com/api/character?name=rick')
        .then(res => {
          console.log(res.data.results)

          this.store.characters = res.data.results;
        });

      console.log("Ricerca percepita")
    },

  },
}
</script>

<template>
  
    <CharacterSearch @search="searchCharacters()"></CharacterSearch>

    <CharactersList></CharactersList>

</template>

<style lang="scss">



</style>
