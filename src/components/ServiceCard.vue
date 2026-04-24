<template>
  <div class="min-h-[100px] w-full bg-gray-100 p-6 rounded-md">
    <header>
      <img :src="image" alt="service thumbnail" loading="lazy" class="object-cover w-full h-[280px]">
    </header>

    <section class="mt-4">
      <h2 class="text-[24px] font-bold">{{ title }}</h2>
      <p class="text-[18px]/[30px] font-[300] mt-3">{{ subTitle }}</p>
    </section>
  </div>
</template>

<script setup>
defineProps({
  image: {
    type: String,
    required: true,
  },
  title: {
    type: String,
    required: true
  },
  subTitle: {
    type: String,
    required: true
  }
})
</script>