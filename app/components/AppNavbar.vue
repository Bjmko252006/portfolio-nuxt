
<template>
  <header class="navbar-header">
    <nav class="max-w-6xl mx-auto flex flex-wrap justify-center gap-3 px-4 py-4">

      <a href="#home" class="nav-fire-btn">
        Home
      </a>

      <a href="#about-details" class="nav-fire-btn">
        About
      </a>

      <a href="#tech-stack" class="nav-fire-btn">
        Tech Stack
      </a>

      <a href="#certifications" class="nav-fire-btn">
        Certifications
      </a>

      <a href="#contact" class="nav-fire-btn">
        Contact
      </a>

    </nav>
  </header>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;600;700;800&display=swap');

.navbar-header {
  background: #444444;
  border-bottom: 1px solid rgba(255, 51, 51, 0.4);
}

/* RED FIRE NAVIGATION BUTTONS */
.nav-fire-btn {
  position: relative;
  display: inline-flex;
  align-items: center;
  justify-content: center;

  padding: 9px 18px;
  border-radius: 8px;
  border: 1px solid rgba(255, 80, 50, 0.8);

  background: linear-gradient(
    135deg,
    #ff3333,
    #b30000
  );

  color: #ffffff;
  text-decoration: none;

  font-family: 'Orbitron', sans-serif;
  font-size: 12px;
  font-weight: 700;
  letter-spacing: 0.5px;

  box-shadow:
    0 0 5px rgba(255, 51, 51, 0.7),
    0 0 12px rgba(255, 30, 0, 0.4);

  transition:
    transform 0.3s ease,
    box-shadow 0.3s ease,
    background 0.3s ease;

  animation: red-fire-glow 2s ease-in-out infinite alternate;
}

/* HOVER FIRE EFFECT */
.nav-fire-btn:hover {
  background: linear-gradient(
    135deg,
    #ff7043,
    #ff0000,
    #990000
  );

  color: #ffffff;
  transform: translateY(-3px) scale(1.05);

  box-shadow:
    0 0 8px #ff3333,
    0 0 18px #ff2200,
    0 0 30px rgba(255, 0, 0, 0.8);
}

/* RED FIRE ANIMATION */
@keyframes red-fire-glow {
  0% {
    box-shadow:
      0 0 4px rgba(255, 51, 51, 0.5),
      0 0 9px rgba(255, 30, 0, 0.3);
  }

  100% {
    box-shadow:
      0 0 8px rgba(255, 80, 50, 0.9),
      0 0 18px rgba(255, 0, 0, 0.7),
      0 0 25px rgba(255, 30, 0, 0.4);
  }
}

/* ACCESSIBILITY */
@media (prefers-reduced-motion: reduce) {
  .nav-fire-btn {
    animation: none;
    transition: none;
  }
}
</style>
