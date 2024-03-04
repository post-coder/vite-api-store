<script>
import AppPagination from "./AppPagination.vue";

import {store} from '../store.js';

export default {
    name: 'CharactersList',

    components:  {
        AppPagination
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
    <ul>
        <li v-for="currentCharacter in store.characters">
            {{currentCharacter.name}}
        </li>
    </ul>
</template>

<style lang="scss">
</style>