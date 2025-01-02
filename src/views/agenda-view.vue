<script setup lang="ts">
import { ref } from 'vue';

interface AgendaEntry {
  date: string;
  event: string;
  location: string;
  status: string;
  flag: string;
}

const agendaEntries = ref<AgendaEntry[]>([
  {
    date: '30-10-2024',
    event: 'Radio 01',
    location: 'Studio @SOHIM',
    status: 'INVITE ONLY',
    flag: '🇨🇭',
  },
  {
    date: '31-12-2024',
    event: 'NYES 04',
    location: 'Lucerne Homeparty',
    status: 'INVITE ONLY',
    flag: '🇨🇭',
  },
  {
    date: '31-01-2025',
    event: 'Radio 02 by Midas Heijdra',
    location: '',
    status: '',
    flag: '',
  }
]);

</script>

<template>
  <div class="max-w-4xl mx-auto p-4">
    <h2 class="text-3xl font-bold mb-8 text-center">AGENDA</h2>
    <div class="space-y-4">
      <div v-for="(entry, index) in agendaEntries" :key="index" class="grid grid-cols-4 gap-4 items-center border-b-2 border-gray-200 py-2">
        <div class="text-sm text-gray-600">{{ entry.date }}</div>
        <div class="text-sm font-semibold">{{ entry.event }}</div>
        <div class="text-sm text-gray-600">{{ entry.location }}</div>
        <div class="text-sm text-right">
          <span v-if="entry.status === 'SOLD OUT'" class="text-red-600">{{ entry.status }}</span>
          <span v-else class="text-green-600">{{ entry.status }}</span>
          <span class="ml-2">{{ entry.flag }}</span>
        </div>
      </div>
    </div>
    <button class="mt-8 px-4 py-2 border border-gray-400 hover:border-gray-600 transition-colors text-sm mx-auto block">
      SHOW ALL
    </button>
  </div>
</template>
