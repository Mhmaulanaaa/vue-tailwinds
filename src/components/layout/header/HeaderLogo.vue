<template>
  <router-link to="/" class="lg:hidden">
    <img
      class="dark:hidden"
      src="/images/logo/medis.png"
      alt="Logo"
      width="150"
      height="150"
    />
    <img
      class="hidden dark:block"
      src="/images/logo/medis.png"
      alt="Logo"
      width="150"
      height="150"
    />
  </router-link>
</template>

<script setup>
import { RouterLink } from "vue-router";
</script>
