<template lang="html">
  <div>
    <h1>Rick and Morty Characters</h1>
    <character-list :characters='characters'></character-list>
  </div>
</template>

<script>
import CharacterList from './components/CharacterList.vue';
import {eventBus} from '@/main.js'

export default {
  name: "app",
  data() {
    return {
      characters: []
    }
  },
  mounted() {
    fetch('https://rickandmortyapi.com/api/character/')
    .then(result  => result.json())
    .then(characters => this.characters = characters['results']);
  },
  components: {
    'character-list': CharacterList
  }
}
</script>

<style lang="css" scoped>

</style>