<script setup>
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <h2>vite + vue3 + vuetify + pinia + vue-router + axios</h2>

  <p>
    <router-link to="/">Go to Home | </router-link>
    <router-link to="/about">Go to About</router-link>
  </p>

  <router-view></router-view>
</template>

<style scoped>

</style>
