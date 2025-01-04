<script setup>
import {
  CheckIcon,
} from 'lucide-vue-next'

const experiences = [
  {
    role: 'Lead Product Engineer',
    company: 'Upwork',
    imagePath: 'upwork.png',
    period: '2024 - Present',
    achievements: [],
  },
  {
    role: 'Staff Software Engineer - Full Stack',
    imagePath: 'objective.png',
    company: 'Objective, Inc. (Acquired by Upwork)',
    period: '2024',
    achievements: [

    ],
  },
  {
    role: 'Software Engineer',
    company: 'Kovo Credit',
    imagePath: 'kovo-credit.png',
    period: '2021 - 2024',
    achievements: [
      'Led Kovo\'s admin dashboard development, resulting in a 70% reduction in customer support ticket resolution time.',
      'Implemented new customer acquisition channels and features, including referrals, partnerships, and rewards, leading to a 15% monthly growth in user acquisition.',
      'Orchestrated the API and OAuth integration process with third-party providers to expand Kovo\'s product offering.',
      'Built CI/CD pipelines with GitHub Actions and established dashboards, monitors, and metrics in DataDog, Rollbar, and Retool.',
      'Collaborated daily with cross-functional teams to swiftly address and resolve customer issues, resulting in improved customer satisfaction and retention rates.',
    ],
    skills: [
      'React', 'Javascript/Typescript', 'NodeJS Fastify', 'Serverless framework', 'AWS', 'Terraform', 'Github Actions', 'Material UI'

    ]
  },
  {
    role: 'Full Stack Engineer',
    company: 'Parexel',
    imagePath: 'parexel.png',
    period: '2020 - 2021',
    achievements: [
      'Developed React-based web applications to support Parexel\'s SDO organization with language data, integrating NLP/ML technologies.',
      'Designed and implemented RESTful API using Python Flask.',
      'Engineered microservices with NodeJS, deployed on Kubernetes for platform-wide application delivery.',
    ],
    skills: [
      'React', 'Node Express', 'Python Flask', 'Elasticsearch', 'PostgresDB', 'Docker', 'Kubernetes', 'AWS'
    ]
  },
  {
    role: 'Frontend Developer',
    company: 'Roam Analytics (Acquired by Parexel)',
    period: '2019 - 2020',
    imagePath: 'roam-analytics.png',
    achievements: [
      'Published the Roam UI components library to ensure a consistent user experience across platforms and expedite the development cycle.',
      'Developed Annotation Manager to optimize the clinical annotation process, converting unstructured medical documents into structured data for NLP.',
      'Implemented Reviewer to significantly enhance CRO\'s clinical trial monitoring report review speed by 500%.',
      'Established end-to-end testing with Cypress to improve code coverage and reduce regression errors.',
    ],
    skills: [
      'React', 'Redux', 'Redux-Saga', 'Node Express', 'Python Flask', 'Elasticsearch', 'PostgresDB', 'Docker', 'Kubernetes', 'AWS'
    ]
  },
  {
    role: 'Fullstack Developer',
    company: 'Liftians',
    period: '2017 - 2019',
    imagePath: 'liftians.png',
    achievements: [
      'Liftians\' First fullstack hire',
      'Developed Liftians\' station operation application, increasing warehouse pick capacity per worker by 400% and facilitating the acquisition of Liftian\'s first customer.',
      'Designed and constructed Liftians\' customer portal that provides full visibility to customers\' products and orders.',
      'Presented and demonstrated the product to investors and prospective customers.'
    ],
    skills: [
      'React', 'Redux', 'Electron', 'Node', 'Python Flask', 'MySQL'
    ]
  },
  {
    role: 'Front-end Developer Intern',
    company: 'SAP',
    period: '2016-2017',
    imagePath: 'SAP.png',
    achievements: [
      'Involved in the beta release of SAP Ana (Digital Assistant) in a small, fast paced team including designers and back-end developers.',
      'Built SAP Ana Admin Dashboard by using Angular.js, Knockout.js, Grunt, Bootstrap, LESS/SASS.',
      'Prototyped multiple proof-of-concept projects based on SAP HANA & SAP HANA Vora.'
    ],
    skills: [
    ]
  },
]
</script>
<template>
  <!-- Main content -->
  <main class="pt-24 pb-16 px-4 sm:px-6 lg:px-8 max-w-5xl mx-auto min-h-screen flex flex-col">
    <section class="mb-16">
      <h2 class="text-3xl font-bold mb-8 bg-gradient-to-r from-white to-gray-400 bg-clip-text text-transparent">
        Experience</h2>
      <div class="space-y-8">
        <div v-for="(experience, index) in experiences" :key="index"
          class="rounded-xl border border-border/50 bg-card/50 backdrop-blur-sm text-card-foreground p-6 hover:border-border/80 transition-all hover:shadow-lg">
          <div class="flex flex-col sm:flex-row sm:items-center gap-4 mb-4">
            <div class="w-16 h-16 rounded-[50%] border border-border/50 bg-card p-2 flex items-center justify-center">
              <NuxtImg :src="`images/${experience.imagePath}`" :alt="`${experience.company} logo`"
                class="w-full h-full object-contain" />
            </div>
            <div>
              <h3 class="text-xl font-semibold">{{ experience.role }}</h3>
              <p class="text-muted-foreground">{{ experience.company }}</p>
            </div>
            <div class="flex-grow" />
            <span
              class="inline-flex items-center rounded-lg bg-primary/10 px-3 py-1.5 text-sm font-medium text-primary">
              {{ experience.period }}
            </span>
          </div>
          <div v-if="experience.skills" class="mb-4 flex flex-wrap gap-2">
            <span v-for="(skill, i) in experience.skills" :key="i"
              class="inline-flex items-center rounded-lg bg-primary/5 px-2.5 py-1 text-xs font-medium text-primary">
              {{ skill }}
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
  </main>
</template>