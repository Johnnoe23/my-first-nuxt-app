<script setup>
// Navigation links live in one array, so adding a page = adding one line
const links = [
  { label: 'Home', to: '/' },
  { label: 'Profile', to: '/profile' },
]

// Controls the mobile menu (open / closed)
const menuOpen = ref(false)
</script>

<template>
  <header class="sticky top-0 z-10 border-b border-slate-200 bg-white/90 backdrop-blur">
    <nav class="mx-auto flex max-w-5xl items-center justify-between px-4 py-4">
      <NuxtLink to="/" class="text-xl font-bold text-indigo-600">
        🎓 Student Hub
      </NuxtLink>

      <!-- Menu button (mobile only) -->
      <button
        class="rounded-lg p-2 text-slate-600 hover:bg-slate-100 md:hidden"
        aria-label="Toggle menu"
        @click="menuOpen = !menuOpen"
      >
        {{ menuOpen ? '✕' : '☰' }}
      </button>

      <!-- Links: hidden on mobile unless the menu is open, always shown on desktop -->
      <ul
        :class="menuOpen ? 'flex' : 'hidden'"
        class="absolute left-0 top-full w-full flex-col gap-1 border-b border-slate-200 bg-white p-4 md:static md:flex md:w-auto md:flex-row md:gap-2 md:border-0 md:p-0"
      >
        <li v-for="link in links" :key="link.to">
          <NuxtLink
            :to="link.to"
            class="block rounded-lg px-4 py-2 font-medium text-slate-600 transition hover:bg-indigo-50 hover:text-indigo-600"
            exact-active-class="bg-indigo-50 !text-indigo-600"
            @click="menuOpen = false"
          >
            {{ link.label }}
          </NuxtLink>
        </li>
      </ul>
    </nav>
  </header>
</template>
