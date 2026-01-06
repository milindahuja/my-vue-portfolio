<template>
  <section id="projects" class="bg-gray-950 py-24">
    <div class="max-w-6xl mx-auto px-6">
      <h2 class="text-3xl font-semibold mb-12 text-white">
        Projects
      </h2>

      <div class="grid gap-8 sm:grid-cols-2 lg:grid-cols-3">
        <ProjectCard
            v-for="project in projects"
            :key="project.title"
            :title="project.title"
            :description="project.description"
            :link="project.link"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
import ProjectCard from './ProjectCard.vue'

const projects = [
  {
    title: 'Portfolio Website',
    description: 'Personal portfolio built with Vue and Tailwind.',
    link: '#'
  },
  {
    title: 'Dashboard App',
    description: 'Admin dashboard with charts and authentication.',
    link: '#'
  },
  {
    title: 'E-commerce UI',
    description: 'Modern shopping UI with responsive layout.',
    link: '#'
  }
]
</script>