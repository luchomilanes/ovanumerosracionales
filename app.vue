<template>
  <div>
    <NuxtLayout>
      <NuxtPage />
    </NuxtLayout>
    <link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" >
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" >
<link href="https://fonts.googleapis.com/css2?family=Bitter:ital,wght@0,100..900;1,100..900&family=Faculty+Glyphic&family=Funnel+Display:wght@300..800&family=Libre+Bodoni:ital,wght@0,400..700;1,400..700&family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&family=Titillium+Web:ital,wght@0,200;0,300;0,400;0,600;0,700;0,900;1,200;1,300;1,400;1,600;1,700&display=swap" rel="stylesheet">

<footer class="footer">
    <div class="footer-waves">
      <svg class="waves" xmlns="http://www.w3.org/2000/svg" viewBox="0 24 150 28" preserveAspectRatio="none">
        <defs>
          <path id="wave" d="M-160 44c30 0 58-18 88-18s 58 18 88 18 58-18 88-18 58 18 88 18 v44h-352z" />
        </defs>
        <g class="wave-parallax">
          <use xlink:href="#wave" x="48" y="0" fill="rgba(52, 152, 219, 0.7)" />
          <use xlink:href="#wave" x="48" y="3" fill="rgba(41, 128, 185, 0.5)" />
          <use xlink:href="#wave" x="48" y="5" fill="rgba(52, 152, 219, 0.3)" />
          <use xlink:href="#wave" x="48" y="7" fill="rgba(41, 128, 185, 0.2)" />
        </g>
      </svg>
    </div>

    <div class="footer-content">
      <div class="footer-section brand-section">
        <img 
          src="https://th.bing.com/th/id/R.4e4b55f050cc74e25209ad45c4326c78?rik=oetujsW9cGulvg&pid=ImgRaw&r=0" 
          alt="Logo de Córdoba" 
          class="footer-image"
        >
        <div class="math-symbols">
          <span class="symbol">÷</span>
          <span class="symbol">±</span>
          <span class="symbol">∞</span>
        </div>
      </div>

      <div class="footer-section main-content">
        <h3 class="footer-title">OVA Números Racionales</h3>
        <p class="footer-description">
          Explora el fascinante mundo de los números racionales a través de nuestra plataforma educativa interactiva.
        </p>
        <div class="creators">
          <h4>Desarrollado por:</h4>
          <ul class="creators-list">
            <li>Luis Arrieta</li>
            <li>Valentina Luna</li>
            <li>Juan Miranda</li>
          </ul>
        </div>
      </div>

      <div class="footer-section links-section">
        <h4>Secciones</h4>
        <nav class="footer-nav">
          <NuxtLink to="/teoria" class="footer-link">Teoría</NuxtLink>
          <NuxtLink to="/calculadora" class="footer-link">Calculadora</NuxtLink>
          <NuxtLink to="/ejemplos" class="footer-link">Ejemplos</NuxtLink>
          <NuxtLink to="/propiedades" class="footer-link">Propiedades</NuxtLink>
          <NuxtLink to="/quiz" class="footer-link">Quiz</NuxtLink>
        </nav>
      </div>
    </div>

    <div class="footer-bottom">
      <p>&copy; 2024 OVA sobre los números racionales. Todos los derechos reservados.</p>
    </div>
  </footer>
  </div>
</template>

<style>
*{
  font-family: "Funnel Display";
}
@import url('https://fonts.googleapis.com/css2?family=Titillium+Web:wght@300;400;600;700&display=swap');


.footer {
  position: relative;
  background: linear-gradient(135deg, #2c3e50, #3498db);
  color: #ffffff;
  font-family: 'Titillium Web', sans-serif;
  overflow: hidden;
}

.footer-waves {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  overflow: hidden;
  line-height: 0;
  transform: rotate(180deg);
}

.waves {
  position: relative;
  width: 100%;
  height: 60px;
}

.wave-parallax use {
  animation: wave 25s cubic-bezier(.55,.5,.45,.5) infinite;
}

.wave-parallax use:nth-child(1) { animation-delay: -2s; }
.wave-parallax use:nth-child(2) { animation-delay: -3s; }
.wave-parallax use:nth-child(3) { animation-delay: -4s; }
.wave-parallax use:nth-child(4) { animation-delay: -5s; }

@keyframes wave {
  0% { transform: translate3d(-90px,0,0); }
  100% { transform: translate3d(85px,0,0); }
}

.footer-content {
  display: grid;
  grid-template-columns: 1fr 2fr 1fr;
  gap: 2rem;
  max-width: 1200px;
  margin: 0 auto;
  padding: 4rem 2rem 2rem;
  position: relative;
  z-index: 1;
}

.footer-section {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}

.brand-section {
  justify-content: center;
}

.footer-image {
  width: 120px;
  height: auto;
  border-radius: 12px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
  transition: transform 0.3s ease;
}

.footer-image:hover {
  transform: scale(1.05);
}

.math-symbols {
  margin-top: 1rem;
  display: flex;
  gap: 1rem;
}

.symbol {
  font-size: 1.5rem;
  opacity: 0.8;
  animation: float 3s ease-in-out infinite;
}

.symbol:nth-child(2) { animation-delay: -1s; }
.symbol:nth-child(3) { animation-delay: -2s; }

@keyframes float {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-10px); }
}

.footer-title {
  font-size: 1.5rem;
  font-weight: 700;
  margin-bottom: 1rem;
  
  -webkit-text-fill-color: transparent;
}

.footer-description {
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.creators {
  margin-top: 1rem;
}

.creators-list {
  list-style: none;
  padding: 0;
  margin: 0.5rem 0;
}

.creators-list li {
  margin: 0.3rem 0;
  opacity: 0.9;
}

.footer-nav {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.footer-link {
  color: #ffffff;
  text-decoration: none;
  padding: 0.3rem 0;
  transition: all 0.3s ease;
  position: relative;
}

.footer-link::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0;
  height: 2px;
  background-color: #e74c3c;
  transition: width 0.3s ease;
}

.footer-link:hover::after {
  width: 100%;
}

.footer-bottom {
  text-align: center;
  padding: 1rem;
  background-color: rgba(0, 0, 0, 0.1);
  font-size: 0.9rem;
}

/* Responsive Design */
@media (max-width: 968px) {
  .footer-content {
    grid-template-columns: 1fr 1fr;
  }
  
  .brand-section {
    grid-column: span 2;
  }
}

@media (max-width: 768px) {
  .footer-content {
    grid-template-columns: 1fr;
    gap: 3rem;
  }

  .brand-section {
    grid-column: span 1;
  }

  .footer-image {
    width: 100px;
  }
}

/* Animación de entrada */
.footer-section {
  opacity: 0;
  animation: fadeInUp 0.8s ease forwards;
}

.footer-section:nth-child(2) { animation-delay: 0.2s; }
.footer-section:nth-child(3) { animation-delay: 0.4s; }

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

</style>