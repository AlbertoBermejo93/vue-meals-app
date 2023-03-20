<template>

  <div class="flex flex-col p-8 justify-center" >


    <div class="flex justify-center gap-2 mt-2">
        <router-link :to="{name: 'byLetter', params: {letter}}" v-for="letter of lettters" :key="letter">
            {{ letter }}
        </router-link>
    </div>

    <pre>{{ ingredients }}</pre>
  </div>
</template>

<script setup>
import { computed, onMounted } from 'vue';
import store from '../store';
import axiosClient from '../axiosClient.js';

const lettters = "ABCDEFGHIJKLMNOPQRSTUVWXYZ".split("");
// const ingredients = ref([]);


onMounted(async () => {
 const response = await axiosClient.get('list.php?i=list')
 console.log(response.data)
//  ingredients.value = response.data
})
</script>