<template>
  <article v-if="character">
      <h3>{{character.name}}</h3>
      <p>Status: {{character.status}}</p>
      <p>Species: {{character.species}}</p>
      <p>Type: {{character.type}}</p>
      <p>Gender: {{character.gender}}</p>
      <p>Origin: {{character.origin.name}}</p>
      <p>Location: {{character.location.name}}</p>
      <img :src='character.image' alt="profile pic">
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