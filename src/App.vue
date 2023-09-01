<script setup>
import countries from './data/countries.json'
import Autocomplete from './components/autocomplete/Autocomplete.vue';
import { ref } from 'vue';

const country = ref('')
</script>

<template>
  <div>
    <h1>Selected {{ country }}</h1>
    <Autocomplete :source="countries" v-model="country" />
  </div>
</template>

<style scoped>

</style>
