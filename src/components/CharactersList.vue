<script>
import SingleCharacter from './SingleCharacter.vue';

export default {
    components: { SingleCharacter },
    props: {
        characters: Object
    }
}
</script>

<template>
    <div class="container">
        <div class="characters-counter">
            {{ `Found ${characters.length} characters` }}
        </div>

        <section class="characters">
            <SingleCharacter v-for="character in characters" :key="character.id" :character="character" />
        </section>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/partials/partials.scss' as *;

.container {
    padding: 2rem;

    .characters-counter {
        background-color: black;
        height: 3rem;
        line-height: 3rem;
        vertical-align: middle;
        padding: 0 1rem;
    }

    .characters {
        margin: 2rem;
        display: flex;
        gap: 2rem 1rem;
        flex-wrap: wrap;
    }
}
</style>