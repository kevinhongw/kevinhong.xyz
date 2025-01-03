<script setup>
const experiences = [
  {
    role: 'Senior Frontend Developer',
    company: 'Tech Solutions Inc.',
    period: '2020 - Present',
    achievements: [
      'Led a team of 5 developers in building a new customer portal',
      'Improved application performance by 40%',
      'Implemented CI/CD pipeline reducing deployment time by 60%',
    ],
  },
  {
    role: 'Full Stack Developer',
    company: 'Digital Innovations Ltd',
    period: '2018 - 2020',
    achievements: [
      'Developed and maintained multiple client projects',
      'Integrated payment processing systems',
      'Mentored junior developers',
    ],
  },
]
</script>
<template>
  <section class="mb-16">
    <h2 class="text-3xl font-bold mb-8 bg-gradient-to-r from-white to-gray-400 bg-clip-text text-transparent">
      Experience</h2>
    <div class="space-y-8">
      <div v-for="(experience, index) in experiences" :key="index"
        class="rounded-xl border border-border/50 bg-card/50 backdrop-blur-sm text-card-foreground p-6 hover:border-border/80 transition-all hover:shadow-lg">
        <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-4 mb-4">
          <div>
            <h3 class="text-xl font-semibold">{{ experience.role }}</h3>
            <p class="text-muted-foreground">{{ experience.company }}</p>
          </div>
          <span
            class="inline-flex items-center rounded-lg bg-primary/10 px-3 py-1.5 text-sm font-medium text-primary-foreground">
            {{ experience.period }}
          </span>
        </div>
        <ul class="space-y-3">
          <li v-for="(achievement, i) in experience.achievements" :key="i" class="flex items-start group">
            <CheckIcon class="h-5 w-5 text-primary mr-3 mt-0.5 shrink-0" />
            <span class="text-muted-foreground">{{ achievement }}</span>
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>