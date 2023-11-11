<script setup lang="ts">
import IconMenu from '../atoms/icons/IconMenu.vue';


</script>

<template>
  <div class="drawer_wrapper">
    <slot></slot>
    <IconMenu @click="$emit('clickMenu')" />
  </div>
</template>

<style scoped>
.drawer_wrapper {
  display: flex;
  justify-content: space-between;
  padding: 1rem;
}
</style>
