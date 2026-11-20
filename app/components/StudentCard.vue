<script setup>
// All student data arrives through props
const props = defineProps({
  name: { type: String, required: true },
  course: { type: String, required: true },
  year: { type: String, required: true },
  bio: { type: String, default: '' },
  color: { type: String, default: 'indigo' },
})

// First letters of the name become the avatar, e.g. "Maya Santos" -> "MS"
const initials = computed(() =>
  props.name.split(' ').map((word) => word[0]).join('').slice(0, 2).toUpperCase()
)

const avatarColors = {
  indigo: 'bg-indigo-100 text-indigo-700',
  emerald: 'bg-emerald-100 text-emerald-700',
  rose: 'bg-rose-100 text-rose-700',
  amber: 'bg-amber-100 text-amber-700',
}
</script>

<template>
  <article class="rounded-2xl border border-slate-200 bg-white p-6 text-center shadow-sm transition hover:shadow-md">
    <div
      :class="avatarColors[color] ?? avatarColors.indigo"
      class="mx-auto flex h-20 w-20 items-center justify-center rounded-full text-2xl font-bold"
    >
      {{ initials }}
    </div>
    <h3 class="mt-4 text-lg font-semibold text-slate-900">{{ name }}</h3>
    <p class="text-sm font-medium text-indigo-600">{{ course }}</p>
    <p class="text-sm text-slate-500">{{ year }}</p>
    <p v-if="bio" class="mt-3 text-sm text-slate-600">{{ bio }}</p>
  </article>
</template>
