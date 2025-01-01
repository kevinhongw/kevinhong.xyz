<template>
  <div class="min-h-screen bg-background text-foreground">
    <!-- Gradient background -->
    <div class="fixed inset-0 -z-10">
      <div
        class="absolute inset-0 bg-[radial-gradient(ellipse_at_top,_var(--tw-gradient-stops))] from-primary/20 via-background to-background">
      </div>
      <div class="absolute inset-0 bg-grid-white/[0.02] bg-grid-pattern"></div>
    </div>

    <!-- Main content -->
    <main v-if="currentPage === 'home'"
      class="w-full px-4 sm:px-6 lg:px-8 py-12 relative min-h-screen flex flex-col items-center">
      <div class="flex-1 flex items-center">
        <div class="flex flex-col items-center">
          <div class="flex flex-col md:flex-row items-center gap-12 md:gap-16 mb-12">
            <!-- Photo -->
            <div class="relative group">
              <div
                class="absolute -inset-0.5 bg-gradient-to-r from-primary/50 to-primary/30 rounded-full blur opacity-50 group-hover:opacity-75 transition duration-500">
              </div>
              <div class="relative w-48 h-48 md:w-56 md:h-56 rounded-full overflow-hidden border-2 border-border/50">
                <img src="/assets/portrait.jpg" alt="Kevin Hong"
                  class="w-full h-full object-cover group-hover:scale-105 transition duration-500" />
              </div>
            </div>

            <!-- Text content -->
            <div class="text-center md:text-left space-y-6">
              <h1
                class="text-4xl sm:text-5xl lg:text-6xl font-bold bg-gradient-to-r from-white to-gray-400 bg-clip-text text-transparent pb-1">
                Kevin Hong
              </h1>

              <div class="space-y-2">
                <div class="flex flex-col gap-2 text-lg sm:text-xl text-muted-foreground/80">
                  <span class="inline-flex items-center gap-2">
                    <CodeIcon class="h-5 w-5 text-primary/80" />
                    Full Stack Developer
                  </span>
                  <span class="inline-flex items-center gap-2">
                    <UsersIcon class="h-5 w-5 text-primary/80" />
                    Father
                  </span>
                  <span class="inline-flex items-center gap-2">
                    <MusicIcon class="h-5 w-5 text-primary/80" />
                    Musician
                  </span>
                </div>
              </div>

              <p class="text-muted-foreground leading-relaxed max-w-lg">
                Passionate about crafting digital experiences and solving complex problems through code.
                When I'm not building web applications, you'll find me making music or spending quality time with my
                family.
              </p>
            </div>
          </div>

          <!-- About Me Button -->
          <button @click="currentPage = 'about'"
            class="group relative px-8 py-3 rounded-full bg-primary/10 hover:bg-primary/20 transition-colors">
            <span class="relative z-10 text-primary-foreground font-medium inline-flex items-center gap-2">
              About Me
              <ArrowRightIcon class="h-4 w-4 group-hover:translate-x-1 transition-transform" />
            </span>
          </button>
        </div>
      </div>

      <Footer />
    </main>

    <!-- About Page -->
    <div v-else class="min-h-screen bg-background text-foreground dark relative">
      <!-- Navigation -->
      <nav class="sticky top-0 w-full bg-background/60 backdrop-blur-lg border-b border-border/40 z-50">
        <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8">
          <div class="flex items-center justify-between h-16">
            <button @click="currentPage = 'home'"
              class="text-primary hover:text-primary/80 transition-colors inline-flex items-center gap-2">
              <ArrowLeftIcon class="h-5 w-5" />
              <span class="font-medium">Back Home</span>
            </button>
          </div>
        </div>
      </nav>

      <!-- Main content -->
      <main class="pt-8 pb-16 px-4 sm:px-6 lg:px-8 max-w-5xl mx-auto min-h-screen flex flex-col">
        <div class="flex-1">
          <!-- Experience Section -->
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

          <!-- Projects Section -->
          <section>
            <h2 class="text-3xl font-bold mb-8 bg-gradient-to-r from-white to-gray-400 bg-clip-text text-transparent">
              Projects</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
              <div v-for="(project, index) in projects" :key="index"
                class="group rounded-xl border border-border/50 bg-card/50 backdrop-blur-sm text-card-foreground overflow-hidden hover:border-border/80 transition-all hover:shadow-lg">
                <div class="relative aspect-video">
                  <img :src="project.image" :alt="project.title"
                    class="object-cover w-full h-full transition-transform duration-500 group-hover:scale-110" />
                  <div
                    class="absolute inset-0 bg-gradient-to-t from-background to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300">
                    <div class="absolute bottom-0 left-0 right-0 p-6">
                      <a :href="project.link" target="_blank" rel="noopener noreferrer"
                        class="w-full px-4 py-2 bg-primary/90 hover:bg-primary text-primary-foreground rounded-lg backdrop-blur-sm transition-colors inline-flex items-center justify-center gap-2">
                        View Project
                        <ExternalLinkIcon class="h-4 w-4" />
                      </a>
                    </div>
                  </div>
                </div>
                <div class="p-6">
                  <h3 class="text-xl font-semibold mb-2 group-hover:text-primary transition-colors">{{ project.title }}
                  </h3>
                  <p class="text-muted-foreground mb-4">{{ project.description }}</p>
                  <div class="flex flex-wrap gap-2">
                    <span v-for="tech in project.technologies" :key="tech"
                      class="inline-flex items-center rounded-lg bg-secondary/50 px-3 py-1.5 text-sm font-medium text-secondary-foreground backdrop-blur-sm">
                      {{ tech }}
                    </span>
                  </div>
                </div>
              </div>
            </div>
          </section>
        </div>

        <Footer />
      </main>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import {
  CodeIcon,
  UsersIcon,
  MusicIcon,
  ArrowRightIcon,
  ArrowLeftIcon,
  CheckIcon,
  ExternalLinkIcon,
  TwitterIcon,
  GithubIcon,
  LinkedinIcon,
  InstagramIcon
} from 'lucide-vue-next'


const currentPage = ref('home')

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

const projects = [
  {
    title: 'E-commerce Platform',
    description: 'A modern e-commerce platform built with Vue.js and Node.js',
    image: '/placeholder.svg?height=300&width=400',
    technologies: ['Vue.js', 'Node.js', 'MongoDB'],
    link: 'https://project1.com'
  },
  {
    title: 'Task Management App',
    description: 'A collaborative task management application',
    image: '/placeholder.svg?height=300&width=400',
    technologies: ['React', 'GraphQL', 'PostgreSQL'],
    link: 'https://project2.com'
  },
]

const socials = [
  {
    name: 'GitHub',
    url: 'https://github.com/yourusername',
    icon: GithubIcon
  },
  {
    name: 'LinkedIn',
    url: 'https://linkedin.com/in/yourusername',
    icon: LinkedinIcon
  },
  {
    name: 'Twitter',
    url: 'https://twitter.com/yourusername',
    icon: TwitterIcon
  },
  {
    name: 'Instagram',
    url: 'https://instagram.com/yourusername',
    icon: InstagramIcon
  }
]
</script>

<style>
.bg-grid-pattern {
  background-size: 40px 40px;
  background-image: linear-gradient(to right, rgb(255 255 255 / 0.05) 1px, transparent 1px),
    linear-gradient(to bottom, rgb(255 255 255 / 0.05) 1px, transparent 1px);
}
</style>