<script>
// per importare axios (dopo essere stato installato) 
import axios from 'axios';

// importiamo lo store
import {store} from './store.js';

import CharactersList from './components/CharactersList.vue';

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
      .get('https://rickandmortyapi.com/api/character?page=10')
      .then(res => {
        console.log(res.data.results)
        this.store.characters = res.data.results
    }).catch(err => {
      console.log(err)
    })

  },

  components: {
    CharactersList,
  },

  methods: {

  },
}
</script>

<template>
  <CharactersList></CharactersList>
</template>

<style lang="scss">



</style>
