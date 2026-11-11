
<template>
  <section
    id="certifications"
    class="bg-[#303030] px-6 py-16 text-white"
  >
    <div class="max-w-4xl mx-auto">

      <!-- Animated Certifications Heading -->
      <h2
        class="cert-font cert-fire text-3xl font-bold text-center mb-8"
        data-text="Certifications"
      >
        Certifications
      </h2>

      <div class="bg-[#3a3a3a] rounded-xl p-8 text-center shadow-lg">
        <h3 class="cert-font text-xl font-semibold text-[#ff5555] mb-3">
          Certifications & Training
        </h3>

        <p class="cert-font text-gray-300 leading-relaxed">
          I am continuously learning and improving my skills in
          Information Technology. More certifications and training
          achievements will be added as I complete them.
        </p>
      </div>

    </div>
  </section>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;600;700;800&display=swap');

/* CERTIFICATIONS FONT */
.cert-font {
  font-family: 'Orbitron', sans-serif;
  letter-spacing: 0.3px;
}

/* CENTERED VIOLET FLAME HEADING */
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

/* VIOLET FLAME HIGHLIGHTS */
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

/* GLOW ANIMATION */
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

/* UPWARD FLAME MOVEMENT */
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

/* ACCESSIBILITY */
@media (prefers-reduced-motion: reduce) {
  .cert-fire,
  .cert-fire::before {
    animation: none;
  }
}
</style>
