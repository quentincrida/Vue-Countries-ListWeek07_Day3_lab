<template lang="html">
  <option v-on:change="handleSelect">{{country.name}}</option>
</template>

<script>
import { eventBus } from '../main.js';

export default {
  name: 'country-select',
  props: ['country'],
  methods: {
    handleSelect(){
      event.$emit('country-selected', this.country)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
