<script setup>
import { onMounted, ref } from 'vue';
import axios from 'axios'

const text = ref('')

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
    </div>
    <div>
      <span>Example axios, advice: </span>
      <span>{{ text }}</span>
    </div>
</template>