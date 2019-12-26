<template lang="html">
  <li v-on:click ="handleClick">
    {{ monster.name }}
  </li>
</template>

<script>
import { eventBus } from '../main.js'
export default {
  name: 'monster-item',
  props: ["monster"],
  methods: {
    handleClick(){
      eventBus.$emit('monster-selected', this.monster)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
