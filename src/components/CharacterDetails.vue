<template>
  <option :value='character'>{{character.name}}</option>
</template>

<script>
export default {
    name: 'character-details',
    props: ['character']
}
</script>

<style>

</style>