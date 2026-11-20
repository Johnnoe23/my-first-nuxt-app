<script setup>
const personalInfo = [
  { label: 'Full Name', value: 'John Noe O. Gonzales' },
  { label: 'Age', value: '21' },
  { label: 'Course', value: 'BS Information Technology' },
  { label: 'Email', value: 'john.noe.gonzales@example.com' },
  { label: 'Location', value: 'Manila, Philippines' },
]

const education = [
  { school: 'Sunrise University', detail: 'BS Information Technology (2024 - Present)' },
  { school: 'Greenfield Senior High School', detail: 'ICT Strand (2022 - 2024)' },
  { school: 'Greenfield Junior High School', detail: 'Junior High School (2018 - 2022)' },
]

const skills = ['HTML', 'CSS', 'Tailwind CSS', 'JavaScript', 'Vue', 'Nuxt', 'Git']
const interests = ['Web Design', 'Open Source', 'UI/UX', 'Game Development']

const hobbies = [
  { icon: '🎮', title: 'Gaming', description: 'Playing puzzle and strategy games with friends.' },
  { icon: '📚', title: 'Reading', description: 'Tech blogs, sci-fi novels, and manga.' },
  { icon: '🎸', title: 'Music', description: 'Learning to play the guitar on weekends.' },
]
</script>

<template>
  <div class="mx-auto max-w-5xl px-4 py-10">
    <!-- Page title -->
    <div class="flex flex-col items-center gap-4 text-center sm:flex-row sm:text-left">
      <div class="flex h-24 w-24 items-center justify-center rounded-full bg-indigo-100 text-3xl font-bold text-indigo-700">JN</div>
      <div>
        <h1 class="text-3xl font-extrabold text-slate-900">John Noe O. Gonzales</h1>
        <p class="text-slate-600">IT student · Nuxt beginner</p>
      </div>
      <div class="sm:ml-auto">
        <AppButton label="← Back to Home" to="/" color="indigo" />
      </div>
    </div>

    <div class="mt-10 grid gap-6 lg:grid-cols-2">
      <!-- Personal information -->
      <section class="rounded-2xl border border-slate-200 bg-white p-6 shadow-sm">
        <h2 class="text-xl font-bold text-slate-900">👤 Personal Information</h2>
        <dl class="mt-4 divide-y divide-slate-100">
          <div v-for="item in personalInfo" :key="item.label" class="flex justify-between gap-4 py-2">
            <dt class="text-slate-500">{{ item.label }}</dt>
            <dd class="text-right font-medium text-slate-800">{{ item.value }}</dd>
          </div>
        </dl>
      </section>

      <!-- Educational background -->
      <section class="rounded-2xl border border-slate-200 bg-white p-6 shadow-sm">
        <h2 class="text-xl font-bold text-slate-900">🎓 Educational Background</h2>
        <ul class="mt-4 space-y-4 border-l-2 border-indigo-200 pl-4">
          <li v-for="item in education" :key="item.school">
            <p class="font-semibold text-slate-800">{{ item.school }}</p>
            <p class="text-sm text-slate-500">{{ item.detail }}</p>
          </li>
        </ul>
      </section>

      <!-- Skills and interests -->
      <section class="rounded-2xl border border-slate-200 bg-white p-6 shadow-sm lg:col-span-2">
        <h2 class="text-xl font-bold text-slate-900">💡 Skills and Interests</h2>

        <h3 class="mt-4 text-sm font-semibold uppercase tracking-wide text-slate-500">Skills</h3>
        <div class="mt-2 flex flex-wrap gap-2">
          <span v-for="skill in skills" :key="skill" class="rounded-full bg-indigo-50 px-3 py-1 text-sm font-medium text-indigo-700">
            {{ skill }}
          </span>
        </div>

        <h3 class="mt-5 text-sm font-semibold uppercase tracking-wide text-slate-500">Interests</h3>
        <div class="mt-2 flex flex-wrap gap-2">
          <span v-for="interest in interests" :key="interest" class="rounded-full bg-emerald-50 px-3 py-1 text-sm font-medium text-emerald-700">
            {{ interest }}
          </span>
        </div>
      </section>
    </div>

    <!-- Hobbies (reusing InfoCard) -->
    <section class="mt-10">
      <h2 class="text-2xl font-bold text-slate-900">🌟 Hobbies</h2>
      <div class="mt-4 grid gap-6 sm:grid-cols-3">
        <InfoCard
          v-for="hobby in hobbies"
          :key="hobby.title"
          :icon="hobby.icon"
          :title="hobby.title"
          :description="hobby.description"
        />
      </div>
    </section>

    <div class="mt-10 text-center">
      <AppButton label="Go to Homepage" to="/" color="emerald" />
    </div>
  </div>
</template>
