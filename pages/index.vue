<template>
  <div class="home-page">
    <div class="header-section">
      <h1 class="title">Bienvenido a nuestro OVA</h1>
      <p class="subtitle">Explora el mundo fascinante de los números racionales y domina sus conceptos.</p>
    </div>
    
    <div class="content-section">
      <h2>aquí podrás encontrar:</h2>
      <ul class="topics-list">
        <li>Definición y conceptos básicos de números racionales</li>
        <li>Operaciones con fracciones</li>
        <li>Ejemplos prácticos</li>
        <li>Propiedades importantes</li>
        <li>Ejercicios de práctica</li>
      </ul>
      <div class="nav-buttons">
        <NuxtLink to="/teoria" class="btn">Comenzar con la Teoría</NuxtLink>
      </div>
    </div>
    
    <div class="video-section">
      <video class="video" controls autoplay muted src="/components/Numeros Racionales.mp4.mp4"></video>
    </div>
  </div>
</template>

  
<style scoped>
/* Estilo general */
.home-page {
  font-family: 'Roboto', sans-serif;
  background: linear-gradient(135deg, #f3f4f6, #d1e7ff);
  color: #333;
  text-align: center;
  padding: 2rem;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  gap: 3rem;
}

/* Encabezado */
.header {
  background: linear-gradient(135deg, #4caf50, #8bc34a);
  color: white;
  padding: 1.5rem;
  border-radius: 10px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
  animation: fadeIn 1.5s ease-in-out;
}

.title {
  font-size: 2.8rem;
  margin-bottom: 0.5rem;
  text-shadow: 0px 3px 6px rgba(0, 0, 0, 0.3);
}

.subtitle {
  font-size: 1.2rem;
  margin: 0;
}

/* Contenido */
.content {
  background: white;
  padding: 1.5rem;
  border-radius: 10px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
  animation: slideUp 1.5s ease-out;
}

.section-title {
  font-size: 1.8rem;
  color: #00796b;
  margin-bottom: 1rem;
}

.topics-list {
  list-style: none;
  padding: 0;
  margin: 1rem 0;
}

.topics-list li {
  background: #e3f2fd;
  padding: 10px 15px;
  border-radius: 5px;
  margin-bottom: 0.5rem;
  font-size: 1rem;
  transition: all 0.3s ease;
}

.topics-list li:hover {
  background: #bbdefb;
  transform: translateX(5px);
}

/* Botones */
.nav-buttons {
  margin-top: 1.5rem;
}

.btn {
  text-decoration: none;
  font-size: 1.2rem;
  background: #0288d1;
  color: white;
  padding: 10px 20px;
  border-radius: 30px;
  transition: transform 0.3s, box-shadow 0.3s;
  display: inline-block;
  box-shadow: 0px 5px 15px rgba(0, 0, 0, 0.2);
}

.btn:hover {
  transform: translateY(-3px);
  box-shadow: 0px 8px 20px rgba(0, 0, 0, 0.3);
}

/* Sección de video */
.video-section {
  padding: 1.5rem;
  background: white;
  border-radius: 10px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
  animation: fadeIn 2s ease;
}

.video {
  width: 90%;
  max-width: 800px;
  border: 3px solid #0288d1;
  border-radius: 10px;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.3);
}

/* Animaciones */
@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

@keyframes slideUp {
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

