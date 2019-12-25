<template lang="html">
  <div>
    <ul>
      <monster-item v-for="(monster, index) in monsters" v-bind:monster="monster" v-bind:key="index"></monster-item>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'monster-list',
  props: ['monsters'],
  components: {
    // "monster-item" : MonsterItem
  }
}
</script>

<style lang="css" scoped>
</style>
