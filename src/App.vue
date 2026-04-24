<script setup>
import { RouterView } from 'vue-router'
import AppNavbar from './components/AppNavbar.vue';
</script>

<template>
  <header>
    <AppNavbar />
    <div>
      <RouterView />
    </div>
  </header>
</template>
