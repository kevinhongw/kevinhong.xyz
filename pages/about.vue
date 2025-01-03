<script setup>
import {
  CodeIcon,
  UsersIcon,
  MusicIcon,
  ArrowRightIcon,
} from 'lucide-vue-next'
</script>
<template>
  <main class="w-full px-4 sm:px-6 lg:px-8 py-12 relative min-h-screen flex flex-col items-center">
    <div class="flex-1 flex items-center">
      <div class="flex flex-col items-center">
        <div class="flex flex-col md:flex-row items-center gap-12 md:gap-16 mb-12">
          <div class="relative group">
            <div
              class="absolute -inset-0.5 bg-gradient-to-r from-primary/50 to-primary/30 rounded-full blur opacity-50 group-hover:opacity-75 transition duration-500">
            </div>
            <div class="relative w-48 h-48 md:w-56 md:h-56 rounded-full overflow-hidden border-2 border-border/50">
              <img src="/assets/portrait.jpg" alt="Kevin Hong"
                class="w-full h-full object-cover group-hover:scale-105 transition duration-500" />
            </div>
          </div>

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
              Based in the metro Seattle area.
              I'm passionate about delivering high-quality, user-centric web applications with a focus on balancing the
              development speed and scalability. Outside of coding, you'll find me trying out new stack, traveling, and
              spending quality time with my family.
            </p>
          </div>
        </div>

        <!-- About Me Button -->
        <button @click="navigateTo('/experiences')"
          class="group relative px-8 py-3 rounded-full bg-foreground hover:bg-foreground/80 transition-colors">
          <span class="relative z-10 text-primary-foreground font-medium inline-flex items-center gap-2">
            About Me
            <ArrowRightIcon class="h-4 w-4 group-hover:translate-x-1 transition-transform" />
          </span>
        </button>
      </div>
    </div>

    <Footer />
  </main>
</template>
