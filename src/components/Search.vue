<script>
import { store } from '../scripts/store.js';

export default {
    data() {
        return {
            store
        }
    },
}
</script>

<template>
    <label for="searchbox">Cerca</label>
    <input id="searchbox" type="text" v-model="store.searchText" @keyup.enter="$emit('performSearch')">

    <select name="parameter" id="parameter" v-model="store.searchParameter">
        <option value="name">Name</option>
        <option value="species">Species</option>
        <option value="status">Status</option>
    </select>
</template>

<style lang="scss" scoped>
label {
    color: black;
}

input {
    margin: 1rem;
}
</style>