
<script setup>
import { ref } from 'vue'

const certificates = [
  {
    title: 'C Essentials 1',
    image: '/certificates/certificate-c-essentials-1-sigayan.jpg',
    link: 'https://www.credly.com/users/bong-b-n-sdca-edu-ph'
  },
  {
    title: 'Fundamentals of Programming 1',
    image: '/certificates/certificate-fundamentals-of-programming-1-sigayan.jpg',
    link: 'https://www.credly.com/badges/0a6befea-602f-4b56-87ef-d07c541251e4/public_url'
  },
  {
    title: 'Introduction to Modern Database Systems',
    image: '/certificates/certificate-introduction-to-modern-database-systems-sigayan.jpg',
    link: 'https://www.credly.com/users/bong-b-n-sdca-edu-ph'
  },
  {
    title: 'Network Basics',
    image: '/certificates/certificate-networking-basics-sigayan.jpg',
    link: 'https://www.credly.com/users/bong-b-n-sdca-edu-ph'
  },
  {
    title: 'Python Essentials 1',
    image: '/certificates/certificate-python-essentials-1-sigayan.jpg',
    link: 'https://www.credly.com/users/bong-b-n-sdca-edu-ph'
  }
]

const selectedCertificate = ref(null)

function openCertificate(certificate) {
  selectedCertificate.value = certificate
}

function closeCertificate() {
  selectedCertificate.value = null
}
</script>

<template>
  <section id="certifications" class="bg-[#303030] px-6 py-16 text-white">
    <div class="max-w-5xl mx-auto">

      <h2
        class="cert-font cert-fire text-3xl font-bold text-center mb-8"
        data-text="Certifications"
      >
        Certifications
      </h2>

      <div class="bg-[#3a3a3a] rounded-xl p-8 text-center shadow-lg mb-10">
        <h3 class="cert-font text-xl font-semibold text-[#ff5555] mb-3">
          Certifications & Training
        </h3>

        <p class="cert-font text-gray-300 font-bold leading-relaxed">
          I am continuously learning and improving my skills in
          Information Technology. Here are some of my certifications
          and training achievements.
        </p>
      </div>

      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
        <div
          v-for="certificate in certificates"
          :key="certificate.title"
          class="bg-[#3a3a3a] rounded-xl p-4 shadow-lg border border-white/5
                 hover:border-purple-400/50 hover:shadow-purple-500/10
                 transition-all duration-300"
        >
          <button
            type="button"
            class="w-full cursor-pointer overflow-hidden rounded-lg
                   bg-[#25252b] focus:outline-none focus:ring-2
                   focus:ring-purple-400"
            :aria-label="`View ${certificate.title} certificate`"
            @click="openCertificate(certificate)"
          >
            <img
              :src="certificate.image"
              :alt="`${certificate.title} Certificate`"
              class="w-full h-52 object-contain hover:scale-105
                     transition-transform duration-300"
              loading="lazy"
            />
          </button>

          <div class="text-center pt-5">
            <h3 class="cert-font text-sm font-semibold text-white mb-4">
              {{ certificate.title }}
            </h3>

            <a
              :href="certificate.link"
              target="_blank"
              rel="noopener noreferrer"
              class="cert-font inline-flex items-center gap-2
                     bg-[#ff3333] hover:bg-[#ff5555]
                     text-white text-xs font-semibold
                     px-5 py-3 rounded-lg transition-all duration-300"
            >
              <span>Verify on Credly</span>
              <span aria-hidden="true">↗</span>
            </a>
          </div>
        </div>
      </div>

      <p class="cert-font text-center text-gray-400 text-xs mt-8">
        {{ certificates.length }} Certifications & Training Achievements
      </p>
    </div>

    <Teleport to="body">
      <Transition name="certificate-lightbox">
        <div
          v-if="selectedCertificate"
          class="fixed inset-0 z-[100] bg-black/90
                 flex items-center justify-center p-4"
          role="dialog"
          aria-modal="true"
          :aria-label="selectedCertificate.title"
          @click.self="closeCertificate"
        >
          <button
            type="button"
            class="absolute top-5 right-6 text-white text-4xl
                   hover:text-purple-400 transition-colors"
            aria-label="Close certificate preview"
            @click="closeCertificate"
          >
            &times;
          </button>

          <div class="certificate-preview max-w-5xl w-full flex flex-col items-center gap-4">
            <img
              :src="selectedCertificate.image"
              :alt="`${selectedCertificate.title} Certificate`"
              class="max-w-full max-h-[80vh] object-contain rounded-lg shadow-2xl"
            />

            <p class="cert-font text-white text-center text-sm">
              {{ selectedCertificate.title }}
            </p>
          </div>
        </div>
      </Transition>
    </Teleport>
  </section>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;600;700;800&display=swap');

.cert-font {
  font-family: 'Orbitron', sans-serif;
  letter-spacing: 0.3px;
}

.cert-fire {
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
  animation: cert-glow 2s ease-in-out infinite alternate;
}

.cert-fire::before {
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
  animation: cert-flame 1.5s ease-in-out infinite alternate;
}

@keyframes cert-glow {
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

@keyframes cert-flame {
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

/* SMOOTH CERTIFICATE PREVIEW */
.certificate-lightbox-enter-active,
.certificate-lightbox-leave-active {
  transition: opacity 0.35s ease;
}

.certificate-lightbox-enter-from,
.certificate-lightbox-leave-to {
  opacity: 0;
}

.certificate-preview {
  transition:
    transform 0.45s cubic-bezier(0.16, 1, 0.3, 1),
    opacity 0.35s ease;
}

.certificate-lightbox-enter-from .certificate-preview {
  transform: scale(0.75);
  opacity: 0;
}

.certificate-lightbox-enter-to .certificate-preview {
  transform: scale(1);
  opacity: 1;
}

.certificate-lightbox-leave-to .certificate-preview {
  transform: scale(0.75);
  opacity: 0;
}

@media (prefers-reduced-motion: reduce) {
  .cert-fire,
  .cert-fire::before {
    animation: none;
  }

  .certificate-lightbox-enter-active,
  .certificate-lightbox-leave-active,
  .certificate-preview {
    transition-duration: 0.01ms;
  }
}
</style>
