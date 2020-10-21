<template>
  <article v-if="character">
      <h3>{{character.name}}</h3>
      <p>Status: {{character.status}}</p>
      <p>Species: {{character.species}}</p>
  </article>
</template>

<script>
export default {
    name: 'show-character',
    props: ['character']
}
</script>

<style>

</style>