<script>

export default {

}

</script>

<template>
    <div class="container">

        <div id="search-bar">
            <input type="search" name="saerchText" placeholder="Cerca">
            <button @click="$emit('search')" class="btn">Cerca</button>
        </div>
        
    </div>

</template>

<style lang="scss" scoped>
.container {
    padding: 24px 0;
}

#search-bar {
    display: flex;
    gap: 12px;

    margin-bottom: 1em;

    input {
        padding: 6px 8px;
    }

    button {
        padding: 8px 12px;
    }
}


</style>