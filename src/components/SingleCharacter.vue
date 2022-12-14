<script>
export default {
    props: {
        character: Object
    }
}
</script>

<template>
    <div class="card">
        <img :src="character.image" alt="">
        <div class="name">{{ character.name }}</div>
        <div class="species">{{ character.species }}</div>
        <div class="status">{{ character.status }}</div>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/partials/partials.scss' as *;

.card {
    padding: 1rem;
    background-color: $primaryColor;
    width: calc((100% - 4rem) / 5);
    text-align: center;

    img {
        max-width: 100%;
    }

    .name {
        margin: 1rem;
        font-size: 1.2rem;
    }

    .species,
    .status {
        color: grey;
        font-weight: 400;
        font-size: 1.1rem;
        margin-bottom: 0.3rem;
    }

    .status {
        font-size: 0.8rem;
    }
}
</style>