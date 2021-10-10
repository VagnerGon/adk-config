<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import HelloWorld from './components/HelloWorld.vue'
import Configs from './components/Configs.vue'

</script>

<template>
  <img alt="Vue logo" src="https://simplyture.com/wp-content/uploads/2021/08/logo.svg" width="300" />
  <HelloWorld msg="ADK config" />

  <Configs />
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
