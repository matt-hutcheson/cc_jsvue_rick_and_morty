<template>
  <article>
      <ul>
          <character-details v-for="(character) in characters" :character="character" :key="character.id"></character-details>
      </ul>
  </article>
</template>

<script>
import CharacterDetails from './CharacterDetails.vue'

export default {
  name: 'character-list',
  props: ['characters'],
  components: {
    "character-details": CharacterDetails
  }
}
</script>

<style>

</style>