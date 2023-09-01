<template>
    <div>
        <input type="text" v-model="search">
        <ul v-show="searchResults.length">
            <li v-for="result in searchResults" :key="result.name" @click="setSelected(result.name)">{{ result.name }}</li>
        </ul>
    </div>
</template>
<script setup>
import { computed, ref } from 'vue';

const props = defineProps({
    source: {
        type: Array,
        required: true,
        default: () => []
    }
})

const search = ref('')

const searchResults = computed(() => {
    if (search.value === '') {
        return []
    }

    return props.source.filter(item => {
        if (item.name.toLowerCase().includes(search.value.toLowerCase())) {
            return item
        }
    })
})

const setSelected = item => {
    search.value = item
}
</script>