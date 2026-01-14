<template>
  <header class="fixed w-full top-0 left-0 backdrop-blur-md z-50 shadow-sm">
    <div class="max-w-6xl mx-auto flex justify-between items-center p-4">
      <!-- Logo / Name -->
      <div class="text-xl font-bold text-gray-200">
        Milind Ahuja
      </div>

      <!-- Navigation links -->
      <nav class="hidden md:flex space-x-6 text-gray-400 font-small">
        <a href="#home" class="hover:text-blue-500 transition">Home</a>
        <a href="#about" class="hover:text-blue-500 transition">About</a>
        <a href="#projects" class="hover:text-blue-500 transition">Projects</a>
        <a href="#contact" class="hover:text-blue-500 transition">Contact</a>
      </nav>

      <!-- Mobile hamburger menu -->
      <div class="md:hidden">
        <button @click="isOpen = !isOpen">
          <svg v-if="!isOpen" xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none"
               viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                  d="M4 6h16M4 12h16M4 18h16"/>
          </svg>
          <svg v-else xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none"
               viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                  d="M6 18L18 6M6 6l12 12"/>
          </svg>
        </button>
      </div>
    </div>

    <!-- Mobile menu dropdown -->
    <div v-if="isOpen" class="md:hidden bg-white/95 backdrop-blur-md shadow-md">
      <nav class="flex flex-col p-4 space-y-4">
        <a href="#home" class="hover:text-blue-500 transition">Home</a>
        <a href="#projects" class="hover:text-blue-500 transition">Projects</a>
        <a href="#about" class="hover:text-blue-500 transition">About</a>
        <a href="#contact" class="hover:text-blue-500 transition">Contact</a>
      </nav>
    </div>
  </header>
</template>

<script setup>
import { ref } from 'vue'
const isOpen = ref(false)
</script>

<style scoped>
header {
  backdrop-filter: blur(10px);
}
</style>