<template>
  <section
    id="about"
    class="flex-1 flex items-center justify-center px-5 py-12"
  >
    <div
      class="w-full max-w-2xl bg-[#303030] border border-[#ff3333]/30 rounded-xl shadow-xl px-6 py-10 md:px-12 text-center"
    >
      <!-- Animated Name -->
      <h1
        class="name-fire text-3xl md:text-4xl font-bold mb-6"
        data-text="Bong Joseph Sigayan"
      >
        Bong Joseph Sigayan
      </h1>

      <!-- Profile Picture with Violet Flames -->
      <div class="flex justify-center mb-7">
        <div class="flame-frame">
          <div class="flame-glow"></div>
          <div class="flame-particle particle-one"></div>
          <div class="flame-particle particle-two"></div>
          <div class="flame-particle particle-three"></div>

          <img
            src="/images/profilepicture.jpg"
            alt="Profile picture of Bong Joseph Sigayan"
            class="profile-image"
          />
        </div>
      </div>

      <!-- Subtitle -->
      <h2 class="text-xl font-semibold mb-4 description-font">
        Aspiring IT Professional
      </h2>

      <!-- Description -->
      <p
        class="text-gray-200 leading-relaxed max-w-lg mx-auto mb-8 description-font"
      >
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

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;600;700;800&display=swap');

/* =================================
   NAME - WHITE VIOLET FLAME
================================= */

.name-fire {
  position: relative;
  display: inline-block;
  font-family: 'Orbitron', sans-serif;
  font-weight: 800;
  letter-spacing: 1px;
  line-height: 1.4;
  color: #ffffff;

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

  animation: name-glow 2s ease-in-out infinite alternate;
}

/* Soft flame highlights behind the letters */
.name-fire::before {
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

  animation: text-flame 1.5s ease-in-out infinite alternate;
}

/* Smooth neon glow */
@keyframes name-glow {
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

/* Upward flickering flame on text */
@keyframes text-flame {
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

/* =================================
   SUBTITLE AND DESCRIPTION FONT
================================= */

.description-font {
  font-family: 'Orbitron', sans-serif;
  font-weight: 500;
  letter-spacing: 0.3px;
}

/* =================================
   PROFILE PICTURE - VIOLET FLAMES
================================= */

.flame-frame {
  position: relative;
  width: 14rem;
  height: 14rem;
  border-radius: 50%;
  isolation: isolate;
  z-index: 1;

  filter:
    drop-shadow(0 0 8px rgba(168, 85, 247, 0.65))
    drop-shadow(0 0 14px rgba(126, 34, 206, 0.4));
}

/* Upward violet flames */
.flame-frame::before {
  content: "";
  position: absolute;
  inset: -15px;
  border-radius: 50%;

  background:
    radial-gradient(ellipse 8px 28px at 15% 30%, #f5d0fe, #a855f7 45%, transparent 75%),
    radial-gradient(ellipse 9px 32px at 35% 5%, #ffffff, #c084fc 40%, transparent 75%),
    radial-gradient(ellipse 8px 30px at 60% 8%, #f5d0fe, #9333ea 45%, transparent 75%),
    radial-gradient(ellipse 9px 34px at 85% 28%, #ffffff, #a855f7 40%, transparent 75%),
    radial-gradient(ellipse 8px 28px at 95% 65%, #e9d5ff, #7e22ce 45%, transparent 75%),
    radial-gradient(ellipse 9px 30px at 75% 92%, #f5d0fe, #9333ea 45%, transparent 75%),
    radial-gradient(ellipse 8px 32px at 40% 95%, #ffffff, #a855f7 45%, transparent 75%),
    radial-gradient(ellipse 9px 30px at 8% 70%, #e9d5ff, #9333ea 45%, transparent 75%);

  -webkit-mask: radial-gradient(
    farthest-side,
    transparent calc(100% - 22px),
    #000 calc(100% - 8px)
  );

  mask: radial-gradient(
    farthest-side,
    transparent calc(100% - 22px),
    #000 calc(100% - 8px)
  );

  filter: blur(3px);
  animation: flame-flicker 0.55s ease-in-out infinite alternate;
  z-index: -2;
}

/* Inner fire glow */
.flame-frame::after {
  content: "";
  position: absolute;
  inset: -7px;
  border-radius: 50%;

  background: conic-gradient(
    #9333ea,
    #f5d0fe,
    #a855f7,
    #ffffff,
    #c084fc,
    #7e22ce,
    #9333ea
  );

  -webkit-mask: radial-gradient(
    farthest-side,
    transparent calc(100% - 10px),
    #000 calc(100% - 5px)
  );

  mask: radial-gradient(
    farthest-side,
    transparent calc(100% - 10px),
    #000 calc(100% - 5px)
  );

  filter: blur(2px);
  animation: fire-pulse 0.7s ease-in-out infinite alternate;
  z-index: -1;
}

/* Purple fire aura */
.flame-glow {
  position: absolute;
  inset: -19px;
  border-radius: 50%;

  background:
    radial-gradient(ellipse at 50% 0%, rgba(216, 180, 254, 0.55), transparent 45%),
    radial-gradient(ellipse at 100% 50%, rgba(147, 51, 234, 0.5), transparent 45%),
    radial-gradient(ellipse at 50% 100%, rgba(192, 132, 252, 0.5), transparent 45%),
    radial-gradient(ellipse at 0% 50%, rgba(126, 34, 206, 0.5), transparent 45%);

  filter: blur(13px);
  opacity: 0.7;
  animation: glow-flicker 0.6s ease-in-out infinite alternate;
  z-index: -3;
}

/* Rising fire particles */
.flame-particle {
  position: absolute;
  bottom: 50%;
  width: 7px;
  height: 19px;
  border-radius: 50% 50% 35% 35%;

  background: linear-gradient(
    to top,
    #7e22ce,
    #c084fc,
    #ffffff
  );

  filter: blur(2px);
  opacity: 0;
  z-index: 3;
  pointer-events: none;
}

.particle-one {
  left: 15%;
  animation: particle-rise 1.5s ease-out infinite;
}

.particle-two {
  left: 48%;
  animation: particle-rise 1.8s ease-out infinite 0.5s;
}

.particle-three {
  right: 15%;
  animation: particle-rise 1.4s ease-out infinite 0.9s;
}

/* Profile image */
.profile-image {
  position: relative;
  z-index: 2;
  display: block;
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 50%;
  border: 3px solid #e9d5ff;

  box-shadow:
    0 0 10px rgba(216, 180, 254, 0.8),
    0 0 18px rgba(168, 85, 247, 0.6);
}

/* Flame movement */
@keyframes flame-flicker {
  0% {
    transform: translateY(3px) scaleY(0.92);
    opacity: 0.65;
    filter: blur(4px);
  }

  50% {
    transform: translateY(-5px) scaleY(1.08);
    opacity: 1;
    filter: blur(2px);
  }

  100% {
    transform: translateY(-9px) scaleY(1.15);
    opacity: 0.8;
    filter: blur(3px);
  }
}

@keyframes fire-pulse {
  from {
    opacity: 0.65;
    filter: blur(2px);
  }

  to {
    opacity: 1;
    filter: blur(4px);
  }
}

@keyframes glow-flicker {
  from {
    opacity: 0.45;
    transform: scale(0.96);
  }

  to {
    opacity: 0.8;
    transform: scale(1.03);
  }
}

@keyframes particle-rise {
  0% {
    transform: translateY(0) scale(0.6);
    opacity: 0;
  }

  20% {
    opacity: 0.9;
  }

  100% {
    transform: translateY(-65px) translateX(8px) scale(0.2);
    opacity: 0;
  }
}

/* Desktop profile size */
@media (min-width: 768px) {
  .flame-frame {
    width: 20rem;
    height: 20rem;
  }
}

/* Accessibility */
@media (prefers-reduced-motion: reduce) {
  .name-fire,
  .name-fire::before,
  .flame-frame::before,
  .flame-frame::after,
  .flame-glow,
  .flame-particle {
    animation: none;
  }
}
</style>