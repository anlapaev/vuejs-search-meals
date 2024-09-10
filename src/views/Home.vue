<template>
    <div>
        <pre>{{meals}}</pre>
    </div>
</template>

<script setup>
import { computed } from 'vue'
import store from '../store/index.js'

const meals = computed(() => {
    return store.state.meals
})
</script>
