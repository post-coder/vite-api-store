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
    <div class="container">
        Elementi in pagina: {{ store.characters.length }}
    </div>
</nav>

</template>

<style lang="scss">

nav {
    margin-bottom: 2em;

    padding: 24px 0;

    border-bottom: solid 1px white;
}

</style>