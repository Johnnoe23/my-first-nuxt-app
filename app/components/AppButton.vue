<script setup>
// Props: values the parent passes in to customize this button
const props = defineProps({
  label: { type: String, required: true },
  color: { type: String, default: 'indigo' }, // indigo | emerald | rose | slate
  to: { type: String, default: '' },          // if set, the button acts as a link
})

// Tailwind needs to see full class names, so we list them out
const colors = {
  indigo: 'bg-indigo-600 hover:bg-indigo-700',
  emerald: 'bg-emerald-600 hover:bg-emerald-700',
  rose: 'bg-rose-600 hover:bg-rose-700',
  slate: 'bg-slate-700 hover:bg-slate-800',
}

const colorClass = computed(() => colors[props.color] ?? colors.indigo)
</script>

<template>
  <!-- With a "to" prop: renders a link. Without: renders a normal button. -->
  <NuxtLink
    v-if="to"
    :to="to"
    :class="colorClass"
    class="inline-block rounded-lg px-5 py-2.5 font-semibold text-white shadow-sm transition"
  >
    {{ label }}
  </NuxtLink>
  <button
    v-else
    type="button"
    :class="colorClass"
    class="rounded-lg px-5 py-2.5 font-semibold text-white shadow-sm transition"
  >
    {{ label }}
  </button>
</template>
