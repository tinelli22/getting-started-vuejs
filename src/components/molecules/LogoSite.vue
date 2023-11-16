<script setup lang="ts">
import { RouterLink } from 'vue-router'

</script>

<template>
    <RouterLink to="/" id="home_link">
      <img src="@/assets/logo.svg" alt="logo of site" />
      <h6 class="head_logo">Logistic</h6>
    </RouterLink>
</template>


<style scoped>
#home_link {
    display: flex;
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