<template>
  <div class="min-h-screen bg-background text-foreground bg-grid-pattern">
    <!-- Halo cursor -->
    <div
      class="fixed w-32 h-32 pointer-events-none -translate-x-1/2 -translate-y-1/2 opacity-30 bg-gradient-to-r from-primary/50 to-primary/30 blur-3xl rounded-full transition-transform duration-200 ease-out z-0"
      :style="{ left: cursorPosition.x + 'px', top: cursorPosition.y + 'px' }" />

    <Header />
    <slot />
    <Footer />
  </div>
</template>
<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const cursorPosition = ref({ x: 0, y: 0 })

const updateCursorPosition = (event) => {
  cursorPosition.value = { x: event.clientX, y: event.clientY }
}

onMounted(() => {
  window.addEventListener('mousemove', updateCursorPosition)

  if (window.matchMedia('(prefers-color-scheme: light)').matches) {
    // TODO: set theme
  }
})

onUnmounted(() => {
  window.removeEventListener('mousemove', updateCursorPosition)
})
</script>
<style>
html {
  scroll-behavior: smooth;
}

.bg-grid-pattern {
  background-size: 80px 80px;
  background-image: linear-gradient(to right, rgb(255 255 255 / 0.05) 1px, transparent 1px),
    linear-gradient(to bottom, rgb(255 255 255 / 0.05) 1px, transparent 1px);
}
</style>
