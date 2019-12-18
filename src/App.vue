<template lang="html">
  <div>
    <h1>Countries</h1>
    <div class="main-container">
      <country-select :countries='countries'/>
      <!-- <countries-list :countries='countries'></countries-list> -->
      <country-detail :country='selectedCountry'/>
    </div>
  </div>

</template>

<script>
import CountriesList from './components/CountriesList.vue';
import { eventBus } from './main.js';
import CountryDetail from './components/CountryDetail.vue';
import CountrySelect from './components/CountrySelect.vue';

export default {
  name: 'app',
  data(){
    return {
      countries: [],
      selectedCountry: null
    };
  },
  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
    .then(res => res.json())
    .then(countries => this.countries = countries)

    eventBus.$on('country-selected', (country) => {
      this.selectedCountry = country;
    })
  },
  components: {
    "countries-list": CountriesList,
    "country-detail": CountryDetail,
    "country-select": CountrySelect
  }
}
</script>

<style lang="css" scoped>
  .main-container {
    display: flex;
    justify-content: space-between;
  }


  
</style>
