<template>
  <li v-on:click="handleClick">{{character.name}}</li>
</template>

<script>
import {eventBus} from '@/main.js'
export default {
    name: 'character-details',
    props: ['character'],
    methods: {
        handleClick() {
            eventBus.$emit('character-selected', this.character)
        }
    }
}
</script>

<style>

</style>