<script setup>
import countries from './data/countries.json'
import Autocomplete from './components/autocomplete/Autocomplete.vue';
</script>

<template>
  <div>
    <Autocomplete :source="countries" />
  </div>
</template>

<style scoped>

</style>
