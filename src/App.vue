<script setup lang="ts">
import { RouterView } from 'vue-router'
import NavigationBar from './components/organisms/NavigationBar.vue';
</script>

<template>
  <header>
    <NavigationBar />
  </header>

  <RouterView />
</template>
