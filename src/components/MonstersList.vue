<template lang="html">
  <div id="monstersList">
    <ul>
      <list-component  v-for="(monster, index) in monsters.results" :monster="monster" :key="index"></list-component>

    </ul>
  </div>

</template>

<script>
import ListComponent from './ListComponent.vue'
export default {
  name: 'monsters-list',
  props: ['monsters'],
  components: {
    "list-component": ListComponent
  }
}
</script>


<style lang="css" scoped>
</style>
