<template lang="html">

  <select v-on:change="handleSelect" v-model="selectedCountry">
    <!-- <country-select v-for="(country,index) in countries" :country="country" :key="index"></country-select> -->


    <option v-for="(country,index) in countries" :key="index" :value="country" >{{country.name}}</option>
  </select>
</template>

<script>
import { eventBus } from '../main.js';

export default {
  name: 'country-select',
  props: ['countries'],
  data(){
    return {
      selectedCountry: null
    }
  },
  methods: {
    handleSelect(){
      eventBus.$emit('country-selected', this.selectedCountry)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
