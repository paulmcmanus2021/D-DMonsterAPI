<template>
  <div>
    <h1>Dungeons and Dragons 5th Edition Monsters</h1>
    <div class="main-container">
      <monster-list v:bind:monsters="monsters"></monster-list>
    </div>
  </div>
</template>

<script>
import MonsterList from './components/MonsterList';

export default {
  name: 'app',
  data() {
    return {
      monsters: []
    }
  },

mounted(){
  fetch('http://www.dnd5eapi.co/api/monsters')
  .then(res => res.json())
  .then(monster => this.monsters = monster)
},
components: {
  "monster-list" : MonsterList
}
}
</script>

<style lang="css" scoped>

</style>
