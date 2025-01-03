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

const socials = [
  {
    name: 'GitHub',
    url: 'https://github.com/kevinhongw',
    icon: GithubIcon
  },
  {
    name: 'LinkedIn',
    url: 'https://www.linkedin.com/in/kevinhongw',
    icon: LinkedinIcon
  },
  // {
  //   name: 'Twitter',
  //   url: 'https://twitter.com/yourusername',
  //   icon: TwitterIcon
  // },
  // {
  //   name: 'Instagram',
  //   url: 'https://instagram.com/yourusername',
  //   icon: InstagramIcon
  // }
]
</script>
<template>
  <footer class="py-6 border-t border-border/40">
    <div class="flex justify-center items-center gap-6">
      <a v-for="social in socials" :key="social.name" :href="social.url" target="_blank" rel="noopener noreferrer"
        class="text-muted-foreground hover:text-primary transition-colors" :aria-label="social.name">
        <component :is="social.icon" class="h-6 w-6" />
      </a>
    </div>
  </footer>
</template>
