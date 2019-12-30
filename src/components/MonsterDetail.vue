<template lang="html">
  <div v-if="monster" id="monsterDetail">
    <div id="detailWrapper">
      <h1>{{monster.name}}</h1>
      <h2>Armor Class: {{monster.armor_class}}</h2>
      <h2>Strength:{{monster.strength}}</h2>
      <h2>Dexterity: {{monster.dexterity}}</h2>
      <h2>Constitution: {{monster.constitution}}</h2>
      <h2>Intelligence: {{monster.intelligence}}</h2>
      <h2>Wisdom: {{monster.wisdom}}</h2>
    </div>
  </div>
</template>

<script>
export default {
  name: 'monster-detail',
  props: ['monster']


}
</script>

<style lang="css" scoped>

</style>
