// src/components/Skills.vue
<template>
  <section class="py-12 px-6 bg-gray-100">
    <h2 class="text-3xl font-bold mb-6 text-center">Competencias</h2>

    <div class="max-w-4xl mx-auto grid grid-cols-1 sm:grid-cols-2 gap-6 text-gray-700">
      <div>
        <h3 class="font-semibold mb-2">Programación</h3>
        <ul class="list-disc list-inside">
          <li>PHP (Laravel, Symfony)</li>
        </ul>
      </div>
      <div>
        <h3 class="font-semibold mb-2">Bases de datos</h3>
        <ul class="list-disc list-inside">
          <li>MongoDB, PostgreSQL, Redis</li>
        </ul>
      </div>
      <div>
        <h3 class="font-semibold mb-2">Sistemas</h3>
        <ul class="list-disc list-inside">
          <li>Docker, Linux, GitFlow, Kubernetes, Jenkins</li>
        </ul>
      </div>
      <div>
        <h3 class="font-semibold mb-2">Idiomas</h3>
        <ul class="list-disc list-inside">
          <li>Español (nativo)</li>
          <li>Inglés (nivel profesional)</li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script setup>
</script>

<style scoped>
</style>