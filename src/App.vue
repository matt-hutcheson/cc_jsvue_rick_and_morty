<template lang="html">
  <div>
    <h1>Rick and Morty Characters</h1>
    <character-list :characters='characters'></character-list>
    <show-character :character='selectedCharacter'></show-character>
  </div>
</template>

<script>
import CharacterList from './components/CharacterList.vue';
import ShowCharacter from './components/CharacterShowDetails';
import {eventBus} from '@/main.js'

export default {
  name: "app",
  data() {
    return {
      characters: [],
      selectedCharacter: null
    }
  },
  mounted() {
    fetch('https://rickandmortyapi.com/api/character/')
    .then(result  => result.json())
    .then(characters => this.characters = characters['results']);

    eventBus.$on('character-selected', (character) => {
      this.selectedCharacter = character
    })
  },
  components: {
    'character-list': CharacterList,
    'show-character': ShowCharacter
  }
}
</script>

<style lang="css" scoped>

</style>