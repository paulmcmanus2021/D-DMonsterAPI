<template lang="html">
  <div v-if="monster" id="monsterDetail">
    <div id="detailWrapper">
      <h2>{{monster.name}}</h2>
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
