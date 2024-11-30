<template>
  <nav class="nav-container">
    <div class="nav-wrapper">
      <div class="nav-links">
        <NuxtLink 
          v-for="(link, index) in links" 
          :key="index"
          :to="link.path"
          class="nav-link"
          active-class="active"
        >
          <span class="nav-text">{{ link.name }}</span>
          <span class="nav-indicator"></span>
        </NuxtLink>
      </div>
    </div>
  </nav>
</template>

<script setup>
const links = [
  { name: 'Teoría', path: '/teoria' },
  { name: 'Calculadora', path: '/calculadora' },
  { name: 'Ejemplos', path: '/ejemplos' },
  { name: 'Propiedades', path: '/propiedades' },
  { name: 'Quiz', path: '/quiz' }
]
</script>

<style scoped>
.nav-container {
  background: linear-gradient(135deg, #2c3e50, #3498db);
  padding: 1rem;
  border-radius: 12px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
  margin: 1rem;
}

.nav-wrapper {
  max-width: 1200px;
  margin: 0 auto;
}

.nav-links {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 1rem;
}

.nav-link {
  position: relative;
  color: #ecf0f1;
  text-decoration: none;
  padding: 0.8rem 1.5rem;
  border-radius: 8px;
  font-weight: 500;
  transition: all 0.3s ease;
  overflow: hidden;
}

.nav-link::before {
  content: '';
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 0;
  height: 3px;
  background-color: #e74c3c;
  transition: width 0.3s ease;
}

.nav-link:hover {
  color: #ffffff;
  transform: translateY(-2px);
}

.nav-link:hover::before {
  width: 80%;
}

.nav-link.active {
  background-color: rgba(255, 255, 255, 0.1);
  color: #ffffff;
}

.nav-link.active::before {
  width: 80%;
  background-color: #e74c3c;
}

/* Animación al cargar */
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(-10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.nav-link {
  animation: fadeIn 0.5s ease forwards;
  animation-delay: calc(var(--index) * 0.1s);
}

/* Responsive */
@media (max-width: 768px) {
  .nav-links {
    flex-direction: column;
    align-items: center;
  }

  .nav-link {
    width: 100%;
    text-align: center;
  }
}

/* Efecto de hover más suave */
.nav-link:hover {
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(5px);
}

/* Efecto de click */
.nav-link:active {
  transform: scale(0.98);
}
</style>