<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'

import AppHeader from './components/icons/app-header.vue'
</script>

<template>
  <div class="app">
  <AppHeader></AppHeader>
  <router-view></router-view>
</div>
</template>

<style lang="scss" >
  .app{
    height: 100vh;
    background-color: lightgreen;
  }
</style>
