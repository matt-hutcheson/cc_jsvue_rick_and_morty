<template>
  <article>
      <select v-on:change="handleSelect" v-model="selectedCharacter">
        <option value="" disabled selected>--Select Character--</option>
        <character-details v-for="(character) in characters" :character="character" :key="character.id"></character-details>
      </select>
  </article>
</template>

<script>
import CharacterDetails from './CharacterDetails.vue'
import {eventBus} from '@/main.js'

export default {
  name: 'character-list',
  props: ['characters'],
  components: {
    "character-details": CharacterDetails
  },
  data() {
    return {
      selectedCharacter: null
    }
  },
  methods: {
    handleSelect() {
        eventBus.$emit('character-selected', this.selectedCharacter)
    }
  }
}
</script>

<style>

</style>