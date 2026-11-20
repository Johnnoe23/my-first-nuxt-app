<script setup>
// Student data: an array of objects. Each object is passed to one StudentCard.
const students = [
  { name: 'Jade Valiant Balansag', course: 'BS Information Technology', year: '3nd Year', bio: 'Loves designing clean user interfaces.', color: 'indigo' },
  { name: 'Darryl Bentonio', course: 'BS Information Technology', year: '3rd Year', bio: 'Enjoys solving problems with JavaScript.', color: 'emerald' },
  { name: 'Daniel Bucio', course: 'BS Information Technology', year: '3st Year', bio: 'Curious about web apps and databases.', color: 'rose' },
  { name: 'Ehren Cabodbod', course: 'BS Information Technology', year: '3th Year', bio: 'Building a capstone project with Vue.', color: 'amber' },
]
</script>

<template>
  <div class="mx-auto max-w-5xl px-4 py-10">
    <!-- Hero: name, introduction, avatar, welcome message -->
    <section class="flex flex-col-reverse items-center gap-8 rounded-3xl bg-gradient-to-br from-indigo-600 to-violet-600 p-8 text-white shadow-lg md:flex-row md:p-12">
      <div class="text-center md:text-left">
        <p class="text-indigo-100">👋 Welcome to my first Nuxt website!</p>
        <h1 class="mt-2 text-4xl font-extrabold sm:text-5xl">Hi, I'm John Noe O. Gonzales</h1>
        <p class="mt-4 max-w-xl text-indigo-100">
          I'm a first-time Nuxt learner studying web development. This site shows how pages,
          components, and props work together. Take a look around and meet my classmates!
        </p>
        <div class="mt-6 flex flex-wrap justify-center gap-3 md:justify-start">
          <AppButton label="View My Profile" to="/profile" color="slate" />
          <a href="#classmates" class="rounded-lg bg-white px-5 py-2.5 font-semibold text-indigo-600 shadow-sm transition hover:bg-indigo-50">
            Meet Classmates
          </a>
        </div>
      </div>

      <!-- Avatar made with Tailwind (no image file needed) -->
      <div class="flex h-40 w-40 shrink-0 items-center justify-center rounded-full border-4 border-white/70 bg-white/20 text-6xl font-bold shadow-xl md:h-48 md:w-48">
        JN
      </div>
    </section>

    <!-- Reusable InfoCards -->
    <section class="mt-10 grid gap-6 sm:grid-cols-3">
      <InfoCard icon="🧭" title="Page Navigation" description="Move between pages using the menu or the buttons." />
      <InfoCard icon="🧩" title="Components" description="Header, footer, and cards are reused across the site." />
      <InfoCard icon="🎨" title="Tailwind CSS" description="Styling is done with utility classes, no big CSS files." />
    </section>

    <!-- Student cards: v-for loops through the array and passes props -->
    <section id="classmates" class="mt-14 scroll-mt-24">
      <h2 class="text-2xl font-bold text-slate-900">Meet the Students</h2>
      <p class="mt-1 text-slate-600">Each card below is the same component with different props.</p>

      <div class="mt-6 grid gap-6 sm:grid-cols-2 lg:grid-cols-4">
        <StudentCard
          v-for="student in students"
          :key="student.name"
          :name="student.name"
          :course="student.course"
          :year="student.year"
          :bio="student.bio"
          :color="student.color"
        />
      </div>
    </section>
  </div>
</template>
