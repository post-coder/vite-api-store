<script>
export default {
    name: 'CharacterItem',

    props: {
        character: Object,
    },
}
</script>

<template>
    <li class="character">
        <img :src="character.image" :alt="character.name">
        {{ character.name }} <br>
        <small>({{ character.species }})</small>
    </li>
</template>

<style lang="scss">
@use '../styles/variables' as *;

.character {
    display: flex;
    flex-flow: column;
    gap: .7em;

    width: calc(100% / 3 - $characterListGap / 3 * 2);

    text-align: center;
}





</style>