<script setup>
const year = new Date().getFullYear()
</script>

<template>
  <footer class="border-t border-slate-200 bg-white">
    <div class="mx-auto flex max-w-5xl flex-col items-center justify-between gap-2 px-4 py-6 text-sm text-slate-500 sm:flex-row">
      <p>© {{ year }} Student Hub · My First Nuxt Application</p>
      <p>
        <NuxtLink to="/" class="hover:text-indigo-600">Home</NuxtLink>
        ·
        <NuxtLink to="/profile" class="hover:text-indigo-600">Profile</NuxtLink>
      </p>
    </div>
  </footer>
</template>
