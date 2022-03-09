<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import SizeSelector from './components/SizeSelector.vue';
import { ref } from 'vue';

const selectedSize = ref('m')
</script>

<template>
  <img alt="Vue logo" src="./assets/logo.png" />

  <SizeSelector 
    :selected-size="selectedSize" 
    @on-change-size="selectedSize = $event" 
    msg="Vue 3 + TypeScript + Vite"/>
  <h3>Talla Seleccionada: {{selectedSize}}</h3>

</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 20px;
}
button{
  padding: 5px;
  margin-right: 5px;
  margin-top: 10px;
  border:none;
  border-radius: 5px;
  width: 75px;
  cursor: pointer;
}
.active{
  background-color: black;
  color: white;
  transition: all .3s ease-out;
}
</style>
