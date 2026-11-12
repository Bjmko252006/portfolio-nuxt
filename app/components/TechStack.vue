
<template>
  <section
    id="tech-stack"
    class="bg-[#2a2a2a] px-6 py-16 text-white"
  >
    <div class="max-w-5xl mx-auto">
      <h2
        class="tech-font tech-fire text-3xl font-bold text-center mb-10"
        data-text="Tech Stack"
      >
        Tech Stack
      </h2>

      <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-5 gap-5">

        <!-- C -->
        <div class="card bg-[#3a3a3a] shadow-lg">
          <div class="card-body items-center text-center justify-center gap-3 py-6">
            <img
              src="/tech-stack/logo.c.png"
              alt="C Programming"
              class="tech-logo"
              loading="lazy"
            />
            <h3 class="tech-font card-title text-[#ff5555]">C</h3>
          </div>
        </div>

        <!-- HTML -->
        <div class="card bg-[#3a3a3a] shadow-lg">
          <div class="card-body items-center text-center justify-center gap-3 py-6">
            <img
              src="/tech-stack/logo.html.png"
              alt="HTML"
              class="tech-logo"
              loading="lazy"
            />
            <h3 class="tech-font card-title text-[#ff5555]">HTML</h3>
          </div>
        </div>

        <!-- Java -->
        <div class="card bg-[#3a3a3a] shadow-lg">
          <div class="card-body items-center text-center justify-center gap-3 py-6">
            <img
              src="/tech-stack/logo.java.png"
              alt="Java"
              class="tech-logo"
              loading="lazy"
            />
            <h3 class="tech-font card-title text-[#ff5555]">Java</h3>
          </div>
        </div>

        <!-- JavaScript -->
        <div class="card bg-[#3a3a3a] shadow-lg">
          <div class="card-body items-center text-center justify-center gap-3 py-6">
            <img
              src="/tech-stack/logo.javascript.png"
              alt="JavaScript"
              class="tech-logo"
              loading="lazy"
            />
            <h3 class="tech-font card-title text-[#ff5555]">JavaScript</h3>
          </div>
        </div>

        <!-- MongoDB -->
        <div class="card bg-[#3a3a3a] shadow-lg">
          <div class="card-body items-center text-center justify-center gap-3 py-6">
            <img
              src="/tech-stack/logo.mongodb.jpg"
              alt="MongoDB"
              class="tech-logo"
              loading="lazy"
            />
            <h3 class="tech-font card-title text-[#ff5555]">MongoDB</h3>
          </div>
        </div>

        <!-- Python -->
        <div class="card bg-[#3a3a3a] shadow-lg">
          <div class="card-body items-center text-center justify-center gap-3 py-6">
            <img
              src="/tech-stack/logo.python.png"
              alt="Python"
              class="tech-logo"
              loading="lazy"
            />
            <h3 class="tech-font card-title text-[#ff5555]">Python</h3>
          </div>
        </div>

        <!-- PostgreSQL -->
        <div class="card bg-[#3a3a3a] shadow-lg">
          <div class="card-body items-center text-center justify-center gap-3 py-6">
            <img
              src="/tech-stack/logo.postgres.png"
              alt="PostgreSQL"
              class="tech-logo"
              loading="lazy"
            />
            <h3 class="tech-font card-title text-[#ff5555]">PostgreSQL</h3>
          </div>
        </div>

        <!-- NetBeans -->
        <div class="card bg-[#3a3a3a] shadow-lg">
          <div class="card-body items-center text-center justify-center gap-3 py-6">
            <img
              src="/tech-stack/logo.netbeans.png"
              alt="NetBeans"
              class="tech-logo"
              loading="lazy"
            />
            <h3 class="tech-font card-title text-[#ff5555]">NetBeans</h3>
          </div>
        </div>

        <!-- VS Code -->
        <div class="card bg-[#3a3a3a] shadow-lg">
          <div class="card-body items-center text-center justify-center gap-3 py-6">
            <img
              src="/tech-stack/logo.vscode.png"
              alt="Visual Studio Code"
              class="tech-logo"
              loading="lazy"
            />
            <h3 class="tech-font card-title text-[#ff5555]">VS Code</h3>
          </div>
        </div>

        <!-- Git -->
        <div class="card bg-[#3a3a3a] shadow-lg">
          <div class="card-body items-center text-center justify-center gap-3 py-6">
            <img
              src="/tech-stack/logo.git.png"
              alt="Git"
              class="tech-logo"
              loading="lazy"
            />
            <h3 class="tech-font card-title text-[#ff5555]">Git</h3>
          </div>
        </div>

        <!-- GitHub -->
        <div class="card bg-[#3a3a3a] shadow-lg">
          <div class="card-body items-center text-center justify-center gap-3 py-6">
            <img
              src="/tech-stack/logo.github.webp"
              alt="GitHub"
              class="tech-logo"
              loading="lazy"
            />
            <h3 class="tech-font card-title text-[#ff5555]">GitHub</h3>
          </div>
        </div>

        <!-- CSS -->
        <div class="card bg-[#3a3a3a] shadow-lg">
          <div class="card-body items-center text-center justify-center gap-3 py-6">
            <img
              src="/tech-stack/logo.css.png"
              alt="CSS"
              class="tech-logo"
              loading="lazy"
            />
            <h3 class="tech-font card-title text-[#ff5555]">CSS</h3>
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

/* TECHNOLOGY LOGOS */
.tech-logo {
  width: 76px;
  height: 76px;
  object-fit: contain;
  transition: transform 0.3s ease;
}

.card:hover .tech-logo {
  transform: scale(1.1);
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
  .tech-fire::before,
  .tech-logo {
    animation: none;
    transition: none;
  }
}
</style>
