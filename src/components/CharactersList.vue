<script>
import { store } from '../scripts/store'
import SingleCharacter from './SingleCharacter.vue';

export default {
    components: { SingleCharacter },
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <div class="characters-counter">
        {{ `Found ${store.characterList.length} characters` }}
    </div>

    <section class="characters">
        <SingleCharacter v-for="character in store.characterList" :key="character.id" :character="character" />
    </section>
</template>

<style lang="scss" scoped>
@use '../styles/partials/partials.scss' as *;

option {
    color: black;
}

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
</style>