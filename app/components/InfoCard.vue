<script setup>
defineProps({
  title: { type: String, required: true },
  description: { type: String, required: true },
  icon: { type: String, default: '' }, // optional emoji
})
</script>

<template>
  <div class="rounded-2xl border border-slate-200 bg-white p-6 shadow-sm">
    <p v-if="icon" class="mb-2 text-3xl">{{ icon }}</p>
    <h3 class="text-lg font-semibold text-slate-900">{{ title }}</h3>
    <p class="mt-1 text-slate-600">{{ description }}</p>
  </div>
</template>
