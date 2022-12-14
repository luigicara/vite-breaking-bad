<script>
import { store } from './scripts/store.js'
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import CharactersList from './components/CharactersList.vue';

export default {
  components: { AppHeader, CharactersList },
  data() {
    return {
      store,
    }
  },
  methods: {
    getCharacters() {
      axios
        .get(this.store.apiURL)
        .then(res => {
          store.characterList = res.data.results;
        })
        .catch(err => {
          console.log(err);
        })
    }
  },
  mounted() {
    this.getCharacters();
  }
}
</script>

<template>
  <AppHeader msg="Rick and Morty Api" />
  <main>
    <CharactersList :characters="store.characterList" />
  </main>
</template>

<style lang="scss">

</style>
