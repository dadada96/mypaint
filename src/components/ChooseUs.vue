<template>
  <section class="grid grid-cols-1 sm:grid-cols-2 gap-18 text-start py-4 px-10 lg:px-30">
    <div v-for="item in reasonData" :key="item.title" class="flex">
      <div class="bg-red-500 h-[80px] w-[80px] rounded-md p-2">
        <img :src="item.icon" alt="shield-icon" class="invert">
      </div>
      <div class="flex-1 px-6">
        <h1 class="text-[20px] font-bold">{{ item.title }}</h1>
        <p class="text-[18px] mt-5">{{ item.description }}</p>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue';
import shieldIcon from '@/assets/icons/shield-halved-solid-full.svg';
import starIcon from '@/assets/icons/star-regular-full.svg';
import userCheckIcon from '@/assets/icons/user-check-solid-full.svg';
import brushIcon from '@/assets/icons/brush-solid-full.svg';
import desktopIcon from '@/assets/icons/display-solid-full.svg';
import chartIcon from '@/assets/icons/chart-column-solid-full.svg';

const reasonData = ref([
  {
    icon: shieldIcon,
    title: 'Double Shield Warranty.',
    description: 'Warranty covering both paint performance and 1-month workmanship. This ensures long-term durability and quality, giving you complete peace of mind.'
  },
  {
    icon: starIcon,
    title: 'Reliable Commitment.',
    description: 'We stick with your project from start to finish. No disappearing acts or leaving your project abandoned. Say goodbye to unreliable painters.'
  },
  {
    icon: userCheckIcon,
    title: 'Expertly Trained Painters.',
    description: 'Our crew includes skilled professionals with expertise in various specialties, from murals and textured finishes to large-scale building projects.'
  },
  {
    icon: brushIcon,
    title: 'Clean & Organized Work.',
    description: 'We use protective coverings to prevent spills and ensure your floors and furniture stay spotless. Once we’re done, we tidy up, leaving no mess behind.'
  },
  {
    icon: desktopIcon,
    title: 'Hassle-Free Process.',
    description: 'We offer a smooth experience with quick quotes, free consultation, and on-site assessments, guided by a Project Advisor who supports you from start to finish, including after-sales warranty assistance.'
  },
  {
    icon: chartIcon,
    title: 'Project Management Experts.',
    description: 'Whether it’s painting a single room, a detailed feature wall, or an entire building, we ensure efficient planning, seamless coordination, and timely execution for projects of any scale.'
  },
])
</script>