<script setup>
import { mapActions, storeToRefs } from 'pinia';
import { useMainStore } from '../store/main';

const mainStore = useMainStore()

const { counter } = storeToRefs(mainStore)
const { increment } = mapActions(useMainStore, ["increment"])
</script>

<template>
    <div>
        <h1>Home</h1>
    </div>
    <div class="w-fit mx-auto mt-8">
      <div>
        <span>Pinia example: </span>
      </div>
      <button class="main-button" type="button" @click="increment">count is {{ counter }}</button>
    </div>
</template>

<style scoped>
.main-button{
    border: 1px solid #e7e4e4;
}
</style>