<script setup>
import { mapActions, storeToRefs } from 'pinia';
import { useMainStore } from '../store/main';
import { onMounted, ref } from 'vue';
import axios from 'axios'

const text = ref('')
const mainStore = useMainStore()
const { counter } = storeToRefs(mainStore)

onMounted(() => {
    axios.get('https://api.adviceslip.com/advice')
        .then(function (response) {
            text.value = response.data.slip.advice;
        })
})
</script>

<template>
    <div>
        <h2>About</h2>
        <h3>count is: {{ counter }}</h3>
    </div>
    <v-card>
        <v-card-title>
            <span>Example axios, </span>
        </v-card-title>
        <v-card-text>
            <span>advice: {{ text }}</span>
        </v-card-text>
    </v-card>
</template>