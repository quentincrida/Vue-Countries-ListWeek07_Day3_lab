<template lang="html">
  <div>
    
    <ul>
      <list-item v-for="(country, index) in countries" :country="country" :key="index"></list-item>
    </ul>
  </div>
</template>

<script>
import ListItem from './ListItem.vue';
import CountrySelect from './CountrySelect.vue'


export default {
  name: 'countries-list',
  props: ['countries'],
  components: {
    "list-item": ListItem,
    "country-select": CountrySelect
  }
}
</script>

<style lang="css" scoped>
</style>
