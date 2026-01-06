<template>
  <div class="bg-gray-800 rounded-xl p-6 hover:bg-gray-700 transition">
    <h3 class="text-xl font-semibold mb-2">
      {{ title }}
    </h3>

    <p class="text-gray-400 mb-4">
      {{ description }}
    </p>

    <a
        :href="link"
        target="_blank"
        class="text-white underline underline-offset-4 hover:text-gray-300"
    >
      View Project
    </a>
  </div>
</template>

<script setup>
defineProps({
  title: String,
  description: String,
  link: String
})
</script>