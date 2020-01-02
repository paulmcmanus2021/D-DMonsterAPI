<template lang="html">
  <div class="entire-page">
    <h1>Dungeons and Dragons 5th Edition Monsters</h1>
    <div class="main-container">
      <monster-dropdown v-bind:monsters='monsters'></monster-dropdown>
      <monster-detail :monster="selectedMonster"></monster-detail>
    </div>
  </div>
</template>

<script>
import { eventBus } from './main.js'
import MonsterDetail from './components/MonsterDetail.vue'
import MonstersList from './components/MonstersList.vue'
import MonsterDropdown from './components/MonsterDropdown.vue'

export default {
  data(){
    return {
      monsters: [],
      selectedMonster: null    }
  },
  components: {
    "monsters-list": MonstersList,
    "monster-detail": MonsterDetail,
    "monster-dropdown": MonsterDropdown
  },
  mounted(){
    fetch('http://www.dnd5eapi.co/api/monsters')
    .then(res => res.json())
    .then(monsters => this.monsters = monsters)

    eventBus.$on('monster-selected', (monster) => {
      fetch(`http://www.dnd5eapi.co` + monster.url)
      .then(res => res.json())
      .then(monster => this.selectedMonster = monster)
    })
  }
}
</script>

<style lang="css" scoped>
  .entire-page {
    font-family: 'MedievalSharp', cursive;
  }

  h1 {
    text-decoration: underline;
    text-decoration-color: red;
    text-align: center;
  }

  .main-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    }
</style>
