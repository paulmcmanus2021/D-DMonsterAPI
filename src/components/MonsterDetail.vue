<template lang="html">
  <div v-if="monster" id="monsterDetail">
    <div id="detailWrapper">
      <h1>{{monster.name}}</h1>
        <ul>
          <li>Armor Class: {{monster.armor_class}}</li>
          <li>Strength:{{monster.strength}}</li>
          <li>Dexterity: {{monster.dexterity}}</li>
          <li>Constitution: {{monster.constitution}}</li>
          <li>Intelligence: {{monster.intelligence}}</li>
          <li>Wisdom: {{monster.wisdom}}</li>
          <li>Charisma: {{monster.charisma}}</li>
      </ul>
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
h1 {
  text-decoration: underline;
  text-decoration-color: red;
  font-family: 'MedievalSharp', cursive;}

li {
  font-size: 30px;
  font-variant: small-caps;
}

</style>
