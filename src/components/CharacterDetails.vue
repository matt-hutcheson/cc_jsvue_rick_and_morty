<template>
  <option :value='character'>{{character.name}}</option>
</template>

<script>
import {eventBus} from '@/main.js'
export default {
    name: 'character-details',
    props: ['character']
}
</script>

<style>

</style>