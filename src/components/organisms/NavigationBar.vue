<script setup lang="ts">
import { RouterLink } from 'vue-router'

import DrawerMenu from '../molecules/DrawerMenu.vue';
import DrawerNavigation from '../molecules/DrawerNavigation.vue';
import { ref } from 'vue';

const drawerIsOpen = ref(false);

function setDrawerStatus(val: boolean) {
  drawerIsOpen.value = val;
}
</script>

<template>
  <DrawerMenu @click-menu="setDrawerStatus(true)">
    <RouterLink to="/" class="inner_link">
      <img src="@/assets/logo.svg" alt="logo of site" />
      <h6 class="head_logo">Logistic</h6>
    </RouterLink>
  </DrawerMenu>
  <DrawerNavigation :open="drawerIsOpen" @click-close="setDrawerStatus(false)">
    <ul>
      <li>
        <RouterLink to="/" class="inner_link"> Home </RouterLink>
      </li>
      <li>
        <RouterLink to="/about" class="inner_link"> About </RouterLink>
      </li>
      <li>
        <RouterLink to="/service" class="inner_link"> Service </RouterLink>
      </li>
      <li>
        <RouterLink to="/blog" class="inner_link"> Blog </RouterLink>
      </li>
      <li>
        <RouterLink to="/contact-us" class="inner_link"> Contact Us </RouterLink>
      </li>
    </ul>
  </DrawerNavigation>
</template>

<style scoped>


.menu_icon {
  width: 42px;
  color: var(--color-primary);
}



.inner_link {
  display: flex;
  align-items: center;
}

img {
  width: 32px;
}

.head_logo {
  text-transform: uppercase;
  font-weight: 700;
  font-size: 1.25rem;
  letter-spacing: 3px;
  padding-left: 0.5rem;
}
</style>
