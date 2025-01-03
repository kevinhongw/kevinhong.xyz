<script setup>

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
</script>
<template>
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
</template>