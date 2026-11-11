
<template>
  <main class="min-h-screen bg-[#2a2a2a] text-white flex flex-col">
<AppNavbar />
<HeroSection />
<AboutSection />
<TechStack />
<Certifications />
<ContactSection />
<MapSection />
    <footer class="text-center py-5 text-sm text-gray-400">
      © {{ new Date().getFullYear() }} Bong Joseph Sigayan. All Rights Reserved.
    </footer>
  </main>
</template>

<script setup>
useHead({
  title: 'Bong Joseph Sigayan | Web Portfolio'
})

useSeoMeta({
  title: 'Bong Joseph Sigayan | Web Portfolio',
  description: 'Personal portfolio of Bong Joseph Sigayan, an aspiring IT Professional and future Software Developer.',
  author: 'Bong Joseph Sigayan',
  ogTitle: 'Bong Joseph Sigayan | Web Portfolio',
  ogDescription: 'Explore my personal portfolio, skills, certifications, and projects.'
})
</script>
