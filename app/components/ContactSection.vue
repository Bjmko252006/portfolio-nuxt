
<template>
  <section
    id="contact"
    class="bg-[#2a2a2a] px-6 py-16 text-white"
  >
    <div class="max-w-4xl mx-auto">
      <h2 class="text-3xl font-bold text-[#ff3333] text-center mb-8">
        Contact Me
      </h2>

      <div class="bg-[#3a3a3a] rounded-xl p-8 text-center shadow-lg">
        <p class="text-gray-300 mb-6">
          Feel free to connect with me through my social accounts.
        </p>

        <div class="flex flex-wrap justify-center gap-4">
          <a
            href="https://github.com/Bjmko252006"
            target="_blank"
            rel="noopener noreferrer"
            class="btn bg-[#ff3333] border-none text-white hover:bg-red-700"
          >
            <Github :size="20" />
            GitHub
          </a>

          <a
            href="https://www.linkedin.com/in/bong-joseph-sigayan-5b22a2406/"
            target="_blank"
            rel="noopener noreferrer"
            class="btn bg-[#ff3333] border-none text-white hover:bg-red-700"
          >
            <Linkedin :size="20" />
            LinkedIn
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { Github, Linkedin } from 'lucide-vue-next'
</script>
