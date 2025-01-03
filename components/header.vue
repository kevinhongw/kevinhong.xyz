<script setup>
const mobileMenuOpen = ref(false)

const navItems = ['Home', 'About', 'Experience', 'Blog']

const navigateMobile = (page) => {
  // currentPage.value = page
  mobileMenuOpen.value = false
}

const toggleTheme = () => { }


</script>
<template>
  <!-- Navigation -->
  <nav class="fixed top-0 left-0 right-0 bg-transparent backdrop-blur-sm border-b border-border/40 z-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16">
        <!-- Logo -->
        <div class="flex items-center">
          <span
            class="text-xl font-bold bg-gradient-to-r from-white to-gray-400 bg-clip-text text-transparent">KH</span>
        </div>

        <!-- Desktop Navigation -->
        <div class="hidden sm:flex sm:items-center sm:space-x-4">
          <button v-for="item in navItems" :key="item" @click="currentPage = item.toLowerCase()" :class="[
            'px-3 py-2 rounded-md text-sm font-medium transition-colors',
            currentPage === item.toLowerCase()
              ? 'bg-primary/10 text-primary'
              : 'text-muted-foreground hover:text-primary hover:bg-primary/5'
          ]">
            {{ item }}
          </button>
          <button @click="toggleTheme"
            class="p-2 rounded-md text-muted-foreground hover:text-primary hover:bg-primary/5 transition-colors"
            aria-label="Toggle theme">
            <SunIcon v-if="theme === 'dark'" class="h-5 w-5" />
            <MoonIcon v-else class="h-5 w-5" />
          </button>
        </div>

        <!-- Mobile menu button -->
        <div class="sm:hidden flex items-center gap-2">
          <button @click="toggleTheme"
            class="p-2 rounded-md text-muted-foreground hover:text-primary hover:bg-primary/5 transition-colors"
            aria-label="Toggle theme">
            <SunIcon v-if="theme === 'dark'" class="h-5 w-5" />
            <MoonIcon v-else class="h-5 w-5" />
          </button>
          <button @click="mobileMenuOpen = !mobileMenuOpen"
            class="p-2 rounded-md text-muted-foreground hover:text-primary hover:bg-primary/5 transition-colors">
            <MenuIcon v-if="!mobileMenuOpen" class="h-6 w-6" />
            <XIcon v-else class="h-6 w-6" />
          </button>
        </div>
      </div>
    </div>

    <!-- Mobile menu -->
    <div v-if="mobileMenuOpen" class="sm:hidden border-b border-border/40">
      <div class="px-2 pt-2 pb-3 space-y-1">
        <button v-for="item in navItems" :key="item" @click="navigateMobile(item.toLowerCase())" :class="[
          'w-full px-3 py-2 rounded-md text-sm font-medium text-left transition-colors',
          currentPage === item.toLowerCase()
            ? 'bg-primary/10 text-primary'
            : 'text-muted-foreground hover:text-primary hover:bg-primary/5'
        ]">
          {{ item }}
        </button>
      </div>
    </div>
  </nav>

</template>