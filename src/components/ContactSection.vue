<template>
  <section id="contact" class="bg-gray-900 py-24">
    <div class="max-w-xl mx-auto px-6">
      <h2 class="text-3xl font-semibold mb-8 text-white">
        Contact
      </h2>

      <form @submit.prevent="submitForm" class="space-y-6">
        <input v-model="name" type="text" placeholder="Your name"
          class="w-full bg-gray-800 text-white px-4 py-3 rounded-lg focus:outline-none focus:ring-2 focus:ring-white" />

        <input v-model="email" type="email" placeholder="Your email"
          class="w-full bg-gray-800 text-white px-4 py-3 rounded-lg focus:outline-none focus:ring-2 focus:ring-white" />

        <textarea v-model="message" placeholder="Your message" rows="4"
          class="w-full bg-gray-800 text-white px-4 py-3 rounded-lg focus:outline-none focus:ring-2 focus:ring-white"></textarea>

        <button type="submit" :disabled="loading || !name.trim() || !email.trim() || !message.trim()"
          class="flex items-center bg-white text-black px-6 py-3 rounded-lg font-medium hover:bg-gray-200 transition disabled:opacity-50">
         <Mail class="w-4 h-4 mr-2" /> {{ loading ? 'Sending...' : 'Send message' }}
        </button>

        <p v-if="success" class="text-green-400 mt-4">
          Message sent successfully.
        </p>

        <p v-if="error" class="text-red-400 mt-4">
          Something went wrong. Please try again.
        </p>
      </form>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import { Mail } from 'lucide-vue-next'
import { collection, addDoc, serverTimestamp } from 'firebase/firestore'
import { db } from '../firebase'

const name = ref('')
const email = ref('')
const message = ref('')
const loading = ref(false)
const success = ref(false)
const error = ref(false)

async function submitForm() {
  loading.value = true
  console.log('db:', db)


  try {
    await addDoc(collection(db, 'messages'), {
      name: name.value,
      email: email.value,
      message: message.value,
      createdAt: serverTimestamp()
    })

    name.value = ''
    email.value = ''
    message.value = ''
    success.value = true
  } catch (error) {
    error.value = true
  } finally {
    loading.value = false
  }
}
</script>