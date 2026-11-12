
<template>
  <section
    id="tech-stack"
    class="bg-[#2a2a2a] px-6 py-16 text-white"
  >
    <div class="max-w-4xl mx-auto">
      <h2
        class="tech-font tech-fire text-3xl font-bold text-center mb-8"
        data-text="Tech Stack"
      >
        Tech Stack
      </h2>

      <div class="grid grid-cols-2 md:grid-cols-3 gap-5">
        <div class="card bg-[#3a3a3a] shadow-lg">
          <div class="card-body items-center text-center">
            <h3 class="tech-font card-title text-[#ff5555]">HTML</h3>
            <p class="tech-font text-gray-300">Web Structure</p>
          </div>
        </div>

        <div class="card bg-[#3a3a3a] shadow-lg">
          <div class="card-body items-center text-center">
            <h3 class="tech-font card-title text-[#ff5555]">CSS</h3>
            <p class="tech-font text-gray-300">Web Styling</p>
          </div>
        </div>

        <div class="card bg-[#3a3a3a] shadow-lg">
          <div class="card-body items-center text-center">
            <h3 class="tech-font card-title text-[#ff5555]">JavaScript</h3>
            <p class="tech-font text-gray-300">Programming</p>
          </div>
        </div>

        <div class="card bg-[#3a3a3a] shadow-lg">
          <div class="card-body items-center text-center">
            <h3 class="tech-font card-title text-[#ff5555]">Java</h3>
            <p class="tech-font text-gray-300">Programming</p>
          </div>
        </div>

        <div class="card bg-[#3a3a3a] shadow-lg">
          <div class="card-body items-center text-center">
            <h3 class="tech-font card-title text-[#ff5555]">MySQL</h3>
            <p class="tech-font text-gray-300">Database</p>
          </div>
        </div>

        <div class="card bg-[#3a3a3a] shadow-lg">
          <div class="card-body items-center text-center">
            <h3 class="tech-font card-title text-[#ff5555]">Git & GitHub</h3>
            <p class="tech-font text-gray-300">Version Control</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;600;700;800&display=swap');

.tech-font {
  font-family: 'Orbitron', sans-serif;
  letter-spacing: 0.3px;
}

/* VIOLET FLAME HEADING */
.tech-fire {
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

  animation: tech-glow 2s ease-in-out infinite alternate;
}

/* VIOLET FLAME HIGHLIGHTS */
.tech-fire::before {
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

  animation: tech-flame 1.5s ease-in-out infinite alternate;
}

/* GLOW ANIMATION */
@keyframes tech-glow {
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
@keyframes tech-flame {
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
  .tech-fire,
  .tech-fire::before {
    animation: none;
  }
}
</style>
