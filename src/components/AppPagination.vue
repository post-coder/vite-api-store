<script>
import {store} from '../store.js';

export default {
    name: 'AppPagination',


    data() {
        return {
            store,
        }
    }

}

</script>

<template>

<nav>
    Elementi in pagina: {{ store.characters.length }}
</nav>

</template>

<style>
</style>