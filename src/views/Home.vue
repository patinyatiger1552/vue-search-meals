<template>
  <div class="flex flex-col p-8 ">
    <div>
       <input type="text" class="rounded border-2 border-gray-200 w-full" placeholder="Search for meals"/>
    </div>
  </div>

  <div class="flex gap-2 justify-center mt-2">
    <router-link :to="{name:'byLetter', params:{letter}}" v-for="letter of letters " :key="letter">
    {{ letter }}
    </router-link>
  </div>
</template>

<script setup>
  import { computed } from 'vue'
  import store from '../store'

  const meals = computed(() => store.state.meals);
  const letters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'.split("")
</script>

<style scoped>
</style>