<template lang="html">
  <div>
    <label for="monster-dropdown">Choose a Monster:</label>
    <select v-on:change="handleChange" name="monster-dropdown" v-model="monsterChoice">
      <option v-for="(monster, index) in monsters.results" :key="index" :value="monster">
        {{ monster.name }}
      </option>
    </select>
  </div>
</template>

<script>
import { eventBus } from '../main.js'
export default {
  name: "monster-dropdown",
  data(){
    return {
      monsterChoice: null
    }
  },
  props: ["monsters"],
  methods: {
    handleChange : function (){
      eventBus.$emit('monster-selected', this.monsterChoice)

    }
  }
}
</script>

<style lang="css" scoped>



</style>
