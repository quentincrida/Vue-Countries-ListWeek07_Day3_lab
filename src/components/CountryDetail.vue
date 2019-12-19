<template lang="html">
  <div v-if="country">
    <h3>{{country.name}}</h3>
    <p>Capital City: {{country.capital}}</p>
    <p>Population: {{country.population}}</p>
    <p v-for=" language in country.languages">Languages: {{language.name}}</p>
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

.lrg-flag {
  height: 100px;
  width: auto;
}
</style>
