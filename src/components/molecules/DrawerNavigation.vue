<script setup lang="ts">
import IconClose from '../atoms/icons/IconClose.vue';
defineProps<{
  open: boolean
}>()
</script>

<template>
  <nav :class="{'open': open}">
    <div class="icon_wrapper">
      <IconClose class="icon_close" @click="$emit('clickClose')" />
    </div>
    <slot></slot>
  </nav>
  <div class="background" @click="$emit('clickClose')"></div>
</template>

<style scoped>
nav {
  position: absolute;
  top: 0;
  left: -100%;
  z-index: 2;
  height: 100vh;
  min-width: 210px;
  max-width: 85%;
  transition: all .4s ease-in-out;
  background-color: var(--color-primary);
  padding: 1rem 0;
}

nav.open {
  left: 0;
}

nav.open + .background {
  display: block;
}

.background {
  display: none;
  position: absolute;
  top: 0;
  height: 100vh;
  width: 100%;
  z-index: 1;
  background-color: #101010d9;
}

.icon_close {
  display: block;
  margin-left: auto;
  margin-right: 1rem;
  width: 24px;
}


</style>
