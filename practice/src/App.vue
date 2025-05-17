<template>
    <div>
        <h1>day and night</h1>
        <input type="range" min="0" max="100" v-model="day_night" />
        <p>value: {{ day_night }}</p>
    </div>
</template>

<script setup>
import { ref } from 'vue'

const day_night = ref(50) //Default value
</script>

<style scoped>
input[type='range'] {
    width: 300px;
    margin-top: 20px;
}
</style>
