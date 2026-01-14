<script setup>
import { Download, Mail } from 'lucide-vue-next'
</script>

<template>
  <section
    id="home"
    class="relative min-h-screen flex items-center justify-center overflow-hidden bg-[#1f2937]"
  >
    <!-- Center radial glow -->
    <div
      class="absolute inset-0 bg-[radial-gradient(circle_at_center,_rgba(255,255,255,0.05),_transparent_60%)] pointer-events-none"
    ></div>

    <!-- Vignette / dark edges -->
    <div
      class="absolute inset-0 bg-[radial-gradient(circle_at_center,_transparent_30%,_rgba(0,0,0,0.6)_100%)] pointer-events-none"
    ></div>

    <!-- Content -->
    <div class="relative text-center max-w-2xl px-6">
      
      <!-- Status Tab -->
      <div class="inline-flex items-center justify-center gap-2 mb-4">
        <span class="w-3 h-3 rounded-full bg-green-500"></span>
        <span class="text-gray-300 text-sm font-medium">Available for opportunities</span>
      </div>

      <h1 class="text-5xl font-bold mb-3 text-white">
        Milind Ahuja
      </h1>

      <p class="text-blue-400 text-xl mb-3">
        Frontend Developer
      </p>

      <p class="text-gray-400 text-lg mb-8">
        Frontend Developer with 10+ years of experience building scalable, user-focused applications with Angular, TypeScript, and modern architecture.
      </p>

      <div class="flex flex-col sm:flex-row gap-4 justify-center">
        <a
          href="#contact"
          class="inline-flex items-center gap-2 bg-white text-black px-6 py-3 rounded-lg font-medium hover:bg-gray-200 transition"
        >
          <Mail class="w-4 h-4" />
          Contact Me
        </a>

        <a
          href="/Milind-Ahuja-CV.pdf"
          target="_blank"
          rel="noopener"
          class="inline-flex items-center gap-2 border border-white/40 text-white px-6 py-3 rounded-lg font-medium hover:bg-white hover:text-black transition"
        >
          <Download class="w-4 h-4" />
          Download CV
        </a>
      </div>

      <!-- Optional: Scroll down indicator -->
      <div class="mt-12 text-gray-400 text-sm animate-bounce">Scroll Down ↓</div>
    </div>
  </section>
</template>