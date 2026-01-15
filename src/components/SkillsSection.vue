<script setup>
    const skillGroups = [
  {
    color: 'blue',
    items: ['Angular (up to v20)', 'TypeScript', 'JavaScript', 'RxJS', 'HTML5', 'CSS3']
  },
  {
    color: 'purple',
    items: ['Component Driven Design', 'SOLID Principles', 'AI & LLM Assisted Workflows']
  },
  {
    color: 'orange',
    items: ['Playwright E2E', 'Jasmine', 'Karma', 'Unit Testing']
  },
  {
    color: 'emerald',
    items: ['Jenkins', 'GitLab CI', 'Automated Builds', 'Quality Gates', 'SonarQube']
  },
  {
    color: 'rose',
    items: ['Node.js', 'REST APIs', 'GraphQL']
  },
  {
    color: 'gray',
    items: ['Git', 'Jira', 'Confluence', 'Strapi CMS']
  }
]

const tools = [
  'Visual Studio Code',
  'IntelliJ',
  'GitHub',
  'GitLab',
  'Jenkins',
  'SonarQube',
  'Figma'
]

const stats = [
  { value: '10+', label: 'Years Experience' },
  { value: '6', label: 'Companies' },
  { value: '3', label: 'Countries' },
  { value: '∞', label: 'Lines of Code' }
]

const colorMap = {
  blue: 'bg-blue-500/10 text-blue-400 border-blue-500/20',
  purple: 'bg-purple-500/10 text-purple-400 border-purple-500/20',
  orange: 'bg-orange-500/10 text-orange-400 border-orange-500/20',
  emerald: 'bg-emerald-500/10 text-emerald-400 border-emerald-500/20',
  rose: 'bg-rose-500/10 text-rose-400 border-rose-500/20',
  gray: 'bg-white/5 text-gray-400 border-white/10'
}
</script>

<template>
    <section id="skills" class="py-28 bg-[#2f2f31] text-white">
    <div class="max-w-6xl mx-auto px-6 text-center">

        <!-- Section Header -->
        <p class="text-sm tracking-widest text-gray-400 mb-3">02. SKILLS</p>
        <h2 class="text-4xl font-bold mb-4">Technical Expertise</h2>
        <div class="w-16 h-1 bg-white mx-auto mb-12"></div>

        <!-- Skills -->
        <div class="flex flex-wrap justify-center gap-3 mb-14">
        <template v-for="group in skillGroups" :key="group.color">
            <span
            v-for="skill in group.items"
            :key="skill"
            class="px-4 py-2 text-sm rounded-md border"
            :class="colorMap[group.color]"
    >
            {{ skill }}
            </span>
        </template>
        </div>

        <!-- Tools -->
        <h3 class="text-lg font-medium text-gray-300 mb-4">Tools & Environment</h3>
        <div class="flex flex-wrap justify-center gap-3 mb-16">
        <span
            v-for="tool in tools"
            :key="tool"
            class="px-4 py-2 text-sm rounded-md bg-white/5 border border-white/10 text-gray-400"
        >
            {{ tool }}
        </span>
        </div>

        <!-- Stats -->
        <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-4 gap-6">
        <div
            v-for="stat in stats"
            :key="stat.label"
            class="bg-white/5 border border-white/10 rounded-xl p-6"
        >
            <div class="text-4xl font-bold text-blue-400 mb-1">
            {{ stat.value }}
            </div>
            <div class="text-sm text-gray-400">
            {{ stat.label }}
            </div>
        </div>
        </div>

    </div>
    </section>
</template>