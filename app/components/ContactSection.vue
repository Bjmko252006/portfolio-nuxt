
<template>
  <section
    id="contact"
    class="bg-[#2a2a2a] px-6 py-16 text-white"
  >
    <div class="max-w-4xl mx-auto">

      <!-- Animated Contact Heading -->
      <h2
        class="contact-font contact-fire text-3xl font-bold text-center mb-8"
        data-text="Contact Me"
      >
        Contact Me
      </h2>

      <div class="bg-[#3a3a3a] rounded-xl p-8 text-center shadow-lg">
        <p class="contact-font text-gray-300 mb-6">
          Feel free to connect with me through my social accounts.
        </p>

        <div class="flex flex-wrap justify-center gap-4">
          <a
            href="https://github.com/Bjmko252006"
            target="_blank"
            rel="noopener noreferrer"
            class="contact-font btn bg-[#ff3333] border-none text-white hover:bg-red-700"
          >
            <Github :size="20" />
            GitHub
          </a>

          <a
            href="https://www.linkedin.com/in/bong-joseph-sigayan-5b22a2406/"
            target="_blank"
            rel="noopener noreferrer"
            class="contact-font btn bg-[#ff3333] border-none text-white hover:bg-red-700"
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

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;600;700;800&display=swap');

/* CONTACT FONT */
.contact-font {
  font-family: 'Orbitron', sans-serif;
  letter-spacing: 0.3px;
}

/* CENTERED VIOLET FLAME HEADING */
.contact-fire {
  position: relative;
  display: table;
  width: fit-content;
  margin-left: auto;
  margin-right: auto;

  font-family: 'Orbitron', sans-serif;
  font-weight: 800;
  letter-spacing: 1px;
  line-height: 1.4;

  background: linear-gradient(
    180deg,
    #ffffff 0%,
    #faf5ff 35%,
    #e9d5ff 70%,
    #c084fc 100%
  );

  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;

  filter:
    drop-shadow(0 0 5px rgba(233, 213, 255, 0.9))
    drop-shadow(0 0 12px rgba(147, 51, 234, 0.6));

  animation: contact-glow 2s ease-in-out infinite alternate;
}

/* VIOLET FLAME HIGHLIGHTS */
.contact-fire::before {
  content: attr(data-text);
  position: absolute;
  inset: 0;

  background: linear-gradient(
    to top,
    transparent 10%,
    #a855f7 35%,
    #ffffff 55%,
    transparent 85%
  );

  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;

  filter: blur(5px);
  opacity: 0.65;
  pointer-events: none;

  animation: contact-flame 1.5s ease-in-out infinite alternate;
}

/* GLOW ANIMATION */
@keyframes contact-glow {
  from {
    filter:
      drop-shadow(0 0 4px rgba(233, 213, 255, 0.65))
      drop-shadow(0 0 9px rgba(147, 51, 234, 0.4));
  }

  to {
    filter:
      drop-shadow(0 0 8px rgba(255, 255, 255, 0.95))
      drop-shadow(0 0 18px rgba(147, 51, 234, 0.75));
  }
}

/* UPWARD FLAME MOVEMENT */
@keyframes contact-flame {
  0% {
    transform: translateY(2px);
    opacity: 0.35;
    filter: blur(6px);
  }

  50% {
    transform: translateY(-2px);
    opacity: 0.8;
    filter: blur(4px);
  }

  100% {
    transform: translateY(-4px);
    opacity: 0.55;
    filter: blur(5px);
  }
}

/* ACCESSIBILITY */
@media (prefers-reduced-motion: reduce) {
  .contact-fire,
  .contact-fire::before {
    animation: none;
  }
}
</style>
