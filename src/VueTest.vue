<script setup>
import {ref} from "vue";
const show = ref(false);
const items = ref([{message: "show" }, {message: "v-for" }])

</script>
<template>
  <h1>v-if Example </h1>
  <h2 v-if="show">Button to show off v-if rendering</h2>
  <h2 v-else>v-else toggled</h2>
  <button @click="show = !show">Check</button>

  <h1>v-show Example</h1>
  <h2 v-show="Boolean">Now rendering v-show</h2>

  <h1>v-for Example</h1>
  <li v-for="item in items" :key="item">
  {{ item.message }}

  
  </li>

  <p>Form Input Handling message: {{ message }}</p>
  <input v-model="message" placeholder="Enter text" /> 

</template>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
