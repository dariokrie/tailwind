<script setup lang="ts">
import { ref } from 'vue';

interface UpdateEntry {
  date: string;
  title: string;
  description: string;
  imageUrl: string;
  href: string;
}

const updates = ref<UpdateEntry[]>([
  {
    date: '01-01-2025',
    title: 'Eclipse Boundaries NYES 04 by SOHIM',
    description: 'NYES (New Years Eve Sets) brings the New Year to life with exclusive DJ mixes. Each year, a single mix is crafted and released on SoundCloud under our label, Eclipse Boundaries. These sets capture the energy of celebration and transition. With one release per year, NYES delivers a unique and unforgettable way to welcome the year ahead.',
    imageUrl: 'https://i1.sndcdn.com/artworks-8ORzWo1tx5AHadzv-19BXmg-t500x500.jpg',
    href: 'https://soundcloud.com/eclipse_boundaries/nyes-04-by-sohim?si=354c0da4e72d4672ae58027daa6b9178&utm_source=clipboard&utm_medium=text&utm_campaign=social_sharing'
  },
  {
    date: '30-11-2024',
    title: 'Eclipse Boundaries Radio 01 by SOHIM & Fabium',
    description: 'We are excited to release the first episode of Eclipse Boundaries Radio. Now up on our SoundCloud!',
    imageUrl: 'https://i1.sndcdn.com/artworks-sV8aJWQe74xmJgzV-Tj53TQ-t500x500.jpg',
    href: 'https://soundcloud.com/eclipse_boundaries/eclipse-boundaries-radio-01-by-sohim-fabium?si=e3f8cf9878ba48e3b1f874a7c3c0e623&utm_source=clipboard&utm_medium=text&utm_campaign=social_sharing'
  }
]);


</script>

<template>
  <div class="max-w-7xl mx-auto p-4">
    <h2 class="text-3xl font-bold mb-8 text-center">UPDATES</h2>
    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">
      <div v-for="(update, index) in updates" :key="index" class="space-y-2">
        <img :src="update.imageUrl" alt="update image" class="w-59 h-59 object-cover" />
        <div class="text-sm text-gray-600">{{ update.date }}</div>
        <h3 class="text-lg font-semibold">{{ update.title }}</h3>
        <p class="text-sm text-gray-600">{{ update.description }}</p>
        <a :href="update.href" class="text-sm text-blue-600 font-semibold hover:underline">READ MORE</a>
      </div>
    </div>
    <button class="mt-8 px-4 py-2 border border-gray-400 hover:border-gray-600 transition-colors text-sm mx-auto block">
      SHOW ALL
    </button>
  </div>
</template>
