
<template>
  <section
    id="about"
    class="flex-1 flex items-center justify-center px-5 py-12"
  >
    <div class="w-full max-w-2xl bg-[#303030] border border-[#ff3333]/30 rounded-xl shadow-xl px-6 py-10 md:px-12 text-center">

      <h1 class="text-3xl md:text-4xl font-bold text-[#ff3333] mb-6">
        Bong Joseph Sigayan
      </h1>

      <!-- Profile Picture -->
      <div class="flex justify-center mb-7">
        <img
          src="/images/profilepicture.jpg"
          alt="Profile picture of Bong Joseph Sigayan"
          class="w-56 h-56 md:w-80 md:h-80 object-cover rounded-full border-4 border-[#ff3333] shadow-lg"
        />
      </div>

      <h2 class="text-xl font-semibold mb-4">
        Aspiring IT Professional
      </h2>

      <p class="text-gray-200 leading-relaxed max-w-lg mx-auto mb-8">
        Hello! I'm Bong Joseph Sigayan, an aspiring IT Professional
        and future Software Developer. I am eager to improve my skills,
        gain more knowledge, and explore different areas within the IT
        field to prepare myself for future opportunities.
      </p>

      <!-- Social Media Icons -->
      <div class="flex justify-center gap-5">
        <a
          href="https://www.linkedin.com/in/bong-joseph-sigayan-5b22a2406/"
          target="_blank"
          rel="noopener noreferrer"
          aria-label="Visit my LinkedIn profile"
          class="btn btn-circle bg-[#ff3333] border-none text-white hover:bg-red-700"
        >
          <Linkedin :size="22" />
        </a>

        <a
          href="https://github.com/Bjmko252006"
          target="_blank"
          rel="noopener noreferrer"
          aria-label="Visit my GitHub profile"
          class="btn btn-circle bg-[#ff3333] border-none text-white hover:bg-red-700"
        >
          <Github :size="22" />
        </a>
      </div>

    </div>
  </section>
</template>

<script setup>
import { Linkedin, Github } from 'lucide-vue-next'
</script>
