<script setup>
import { mapActions, storeToRefs } from 'pinia';
import { useMainStore } from '../store/main';

const mainStore = useMainStore()

const { counter } = storeToRefs(mainStore)
const { increment } = mapActions(useMainStore, ["increment"])
</script>

<template>
    <div>
        <h3>Home</h3>
    </div>
    <div class="w-fit mx-auto mt-8">
        <v-card>
            <v-card-title>
                <span>Pinia example: </span>
            </v-card-title>
            <v-card-text>
                <v-btn class="main-button" @click="counter++">count is {{ counter }}</v-btn>
            </v-card-text>
        </v-card>
      <div>
        
      </div>
      
    </div>
</template>

<style scoped>
.main-button{
    border: 1px solid #e7e4e4;
}
</style>