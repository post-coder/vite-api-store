<script>
import AppPagination from "./AppPagination.vue";
import CharacterItem from "./CharacterItem.vue";

import {store} from '../store.js';

export default {
    name: 'CharactersList',

    components:  {
        AppPagination,
        CharacterItem
    },

    data() {
        return  {
            store,
        }
    }
}
</script>

<template>
    <AppPagination></AppPagination>

    <div class="container">

        <ul>
            <CharacterItem 
                v-for="currentCharacter in store.characters"
                :character="currentCharacter"
            ></CharacterItem>
           
        </ul>
    </div>
</template>

<style lang="scss">
@use '../styles/variables' as *;

ul {
    list-style-type: none;

    display: flex;
    flex-flow: row wrap;
    
    gap: $characterListGap;
}

</style>