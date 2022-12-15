<script>
import { store } from './scripts/store.js'
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import CharactersList from './components/CharactersList.vue';
import Search from './components/Search.vue';

export default {
  components: { AppHeader, CharactersList, Search },
  data() {
    return {
      store,
    }
  },
  methods: {
    getCharacters() {
      if (store.searchText !== "") {
        store.apiURL += `?${store.searchParameter}=${store.searchText}`
      }

      axios
        .get(this.store.apiURL)
        .then(res => {
          store.characterList = res.data.results;
        })
        .catch(err => {
          console.log(err);
        })

      store.apiURL = 'https://rickandmortyapi.com/api/character'
    }
  },

  mounted() {
    this.getCharacters();
  },
}
</script>

<template>
  <AppHeader msg="Rick and Morty Api" />
  <main>
    <div class="container">
      <Search @performSearch="getCharacters" />
      <CharactersList :characters="store.characterList" />
    </div>
  </main>
</template>

<style lang="scss">
.container {
  padding: 2rem;
}
</style>
