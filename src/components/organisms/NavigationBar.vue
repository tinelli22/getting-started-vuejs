<script setup lang="ts">
import { RouterLink } from 'vue-router'
import { ref } from 'vue';

import DrawerMenu from '../molecules/DrawerMenu.vue';
import DrawerNavigation from '../molecules/DrawerNavigation.vue';
import LogoSite from '../molecules/LogoSite.vue';

const drawerIsOpen = ref(false);

function setDrawerStatus(val: boolean) {
  drawerIsOpen.value = val;
}
</script>

<template>
  <DrawerMenu @click-menu="setDrawerStatus(true)">
   <LogoSite />
  </DrawerMenu>
  <DrawerNavigation :open="drawerIsOpen" @click-close="setDrawerStatus(false)">
    <ul>
      <li @click="setDrawerStatus(false)">
        <RouterLink to="/" active-class="active_class"> Home </RouterLink>
      </li>
      <li @click="setDrawerStatus(false)">
        <RouterLink to="/about" active-class="active_class"> About </RouterLink>
      </li>
      <li @click="setDrawerStatus(false)">
        <RouterLink to="/service"> Service </RouterLink>
      </li>
      <li @click="setDrawerStatus(false)">
        <RouterLink to="/blog"> Blog </RouterLink>
      </li>
      <li @click="setDrawerStatus(false)">
        <RouterLink to="/contact-us"> Contact Us </RouterLink>
      </li>
    </ul>
  </DrawerNavigation>
</template>

<style scoped>

ul li a {
  display: block;
  height: 100%;
  padding: 1rem;
}

ul li {
  min-height: 2rem;
}

.active_class {
 color: var(--color-primary); 
 font-weight: 700;
 background-color: var(--color-background);
}

.menu_icon {
  width: 42px;
  color: var(--color-primary);
}


</style>
