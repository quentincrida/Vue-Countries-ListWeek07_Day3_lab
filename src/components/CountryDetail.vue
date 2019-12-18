<template lang="html">
  <div v-if="country">
    <h3>{{country.name}}</h3>
    <p>{{country.capital}}</p>
    <p>{{country.population}}</p>
    <p>{{country.languages}}</p>
    <img class="lrg-flag" :src="country.flag"/>
  </div>
</template>

<script>

export default {
  name: 'country-detail',
  props: ['country']
}
</script>

<style lang="css" scoped>
</style>
