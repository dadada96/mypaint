<template>
  <div class="px-8 bg-(--color-background) h-[80px] flex items-center">
    <nav class="w-full flex justify-between">
      <div>
        <RouterLink to="/">Logo</RouterLink>
      </div>
      <ul class="flex gap-2">
        <li>
          <RouterLink to="/" class="rounded-full p-2">House Painting</RouterLink>
        </li>
        <!-- <li>
          <RouterLink to="/commercial-painting" class="rounded-full p-2">Commercial Painting</RouterLink>
        </li>
        <li>
          <RouterLink to="/be-our-painters" class="rounded-full p-2">Be Our Painters</RouterLink>
        </li> -->
      </ul>
    </nav>
  </div>
</template>

<script setup>
import { RouterLink } from 'vue-router';
</script>
