<template lang="html">
  <div>
    <h1>Monsters</h1>
    <div class="main-container">
      <monsters-list :monsters="monsters"></monsters-list>
      <monster-detail :monster="selectedMonster"></monster-detail>
    </div>
  </div>
</template>

<script>
import { eventBus } from './main.js'
import MonsterDetail from './components/MonsterDetail.vue'
import MonstersList from './components/MonstersList.vue'

export default {
  data(){
    return {
      monsters: [],
      selectedMonster: null    }
  },
  components: {
    "monsters-list": MonstersList,
    "monster-detail": MonsterDetail
  },
  mounted(){
    fetch('http://www.dnd5eapi.co/api/monsters')
    .then(res => res.json())
    .then(monsters => this.monsters = monsters)

    eventBus.$on('monster-selected', (monster) => {
      fetch(monster.url)
      .then(res => res.json())
      .then(monster => this.selectedMonster = monster)
    })
  }
}
</script>

<style lang="css" scoped>

.main-container {
    display: flex;
    justify-content: space-between;
    width: 80%;
    margin: 0 auto;
  }

</style>
