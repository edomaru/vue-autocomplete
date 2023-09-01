<template>
    <div>
        <input type="text">
        <ul>
            <li v-for="result in searchResults" :key="result.name">{{ result.name }}</li>
        </ul>
    </div>
</template>
<script setup>
import { computed } from 'vue';

const props = defineProps({
    source: {
        type: Array,
        required: true,
        default: () => []
    }
})

const searchResults = computed(() => props.source)
</script>