// src/App.vue
<template>
  <div class="font-sans text-gray-900">
    <!-- Menú de navegación -->
    <nav class="bg-white shadow-md sticky top-0 z-50">
      <div class="max-w-7xl mx-auto px-4 py-3 flex justify-center gap-6 text-sm font-medium">
        <a
            v-for="link in navLinks"
            :key="link.id"
            :href="`#${link.id}`"
            :class="[
            'hover:text-blue-600 transition-colors',
            activeSection === link.id ? 'text-blue-600 font-semibold' : 'text-gray-700'
          ]"
        >
          {{ link.label }}
        </a>
      </div>
    </nav>

    <!-- Secciones -->
    <section id="about" ref="aboutRef"><About /></section>
    <section id="experience" ref="experienceRef"><Experience /></section>
    <section class="py-24" id="education" ref="educationRef"><Education /></section>
    <section class="py-24" id="skills" ref="skillsRef"><Skills /></section>
    <section class="mb-40" id="contact" ref="contactRef"><Contact /></section>
  </div>
</template>

<script setup>
import { onMounted, onUnmounted, ref } from 'vue'
import About from './components/About.vue'
import Experience from './components/Experience.vue'
import Education from './components/Education.vue'
import Skills from './components/Skills.vue'
import Contact from './components/Contact.vue'

const navLinks = [
  { id: 'about', label: 'Sobre mí' },
  { id: 'experience', label: 'Experiencia' },
  { id: 'education', label: 'Educación' },
  { id: 'skills', label: 'Competencias' },
  { id: 'contact', label: 'Contacto' }
]

const activeSection = ref('about')

const aboutRef = ref(null)
const experienceRef = ref(null)
const educationRef = ref(null)
const skillsRef = ref(null)
const contactRef = ref(null)

const sectionRefs = [
  { id: 'about', ref: aboutRef },
  { id: 'experience', ref: experienceRef },
  { id: 'education', ref: educationRef },
  { id: 'skills', ref: skillsRef },
  { id: 'contact', ref: contactRef },
]

function handleScroll() {
  const scrollY = window.scrollY + 150

  for (const section of sectionRefs) {
    const el = section.ref.value
    if (el) {
      const top = el.offsetTop
      const height = el.offsetHeight
      if (scrollY >= top && scrollY < top + height) {
        activeSection.value = section.id
        break
      }
    }
  }
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
  handleScroll()
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style>
body {
  margin: 0;
  scroll-behavior: smooth;
}
</style>
