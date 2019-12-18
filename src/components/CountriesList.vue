<template lang="html">

</template>

<script>
import ListItem from './ListItem.vue'

export default {
  name: 'countries-list',
  props: ['countries'],
  components: {
    "list-item": ListItem
  }
}
</script>

<style lang="css" scoped>
</style>
