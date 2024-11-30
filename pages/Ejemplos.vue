<template>
    <div class="ejemplos-container">
      <h2>Ejemplos de Números Racionales</h2>
      <p>Los números racionales pueden expresarse como una fracción de dos enteros. A continuación se muestran algunos ejemplos y ejercicios:</p>
  
      <div class="ejemplo-card" v-for="(ejemplo, index) in ejemplos" :key="index">
        <h3>Ejemplo {{ index + 1 }}</h3>
        <p>{{ ejemplo }}</p>
      </div>
  
      <h3>Ejercicios para Resolver</h3>
      <div class="ejercicio-card" v-for="(ejercicio, index) in ejercicios" :key="index">
        <p>{{ ejercicio.pregunta }}</p>
        <input 
          type="text" 
          v-model="respuestas[index]" 
          :placeholder="'Respuesta ' + (index + 1)"
        />
        <button @click="verificarRespuesta(index)">Verificar</button>
        <p v-if="mensajes[index]" :class="{'correcto': mensajes[index] === 'Correcto', 'incorrecto': mensajes[index] === 'Incorrecto'}">{{ mensajes[index] }}</p>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const ejemplos = [
    "1/2 (una fracción que representa la mitad)",
    "-3/4 (un número racional negativo)",
    "5 (el número entero 5 es un número racional, ya que puede expresarse como 5/1)",
    "0.75 (un decimal que puede expresarse como 3/4)",
    "-2 (un entero negativo que puede escribirse como -2/1)"
  ];
  
  const ejercicios = [
    {
      pregunta: "Escribe el número racional que representa tres cuartos.",
      respuestaCorrecta: "3/4"
    },
    {
      pregunta: "Escribe un número racional equivalente a 0.5.",
      respuestaCorrecta: "1/2"
    },
    {
      pregunta: "¿Cuál es la representación fraccionaria del número -1.25?",
      respuestaCorrecta: "-5/4"
    }
  ];
  
  const respuestas = ref(Array(ejercicios.length).fill(''));
  const mensajes = ref(Array(ejercicios.length).fill(''));
  
  const verificarRespuesta = (index) => {
    mensajes.value[index] = respuestas.value[index] === ejercicios[index].respuestaCorrecta ? "Correcto" : "Incorrecto";
  };
  </script>
  
  <style scoped>
  .ejemplos-container {
    max-width: 800px;
    margin: auto;
    padding: 20px;
    background-color: #f3f7fa;
    border-radius: 8px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
    text-align: center;
  }
  
  h2 {
    color: #1976d2;
    font-size: 24px;
    margin-bottom: 15px;
  }
  
  p {
    font-size: 16px;
    color: #555;
    line-height: 1.6;
  }
  
  .ejemplo-card, .ejercicio-card {
    background-color: #ffffff;
    padding: 15px;
    margin: 10px 0;
    border-radius: 8px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    text-align: left;
  }
  
  .ejemplo-card h3, .ejercicio-card p {
    color: #388e3c;
    font-size: 18px;
  }
  
  input[type="text"] {
    padding: 8px;
    width: 70%;
    margin-top: 5px;
    border: 1px solid #ddd;
    border-radius: 5px;
  }
  
  button {
    padding: 8px 12px;
    margin-top: 8px;
    background-color: #1976d2;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.2s ease;
    margin-left: 20px;
  }
  
  button:hover {
    background-color: #1565c0;
  }
  
  .correcto {
    color: green;
    font-weight: bold;
  }
  
  .incorrecto {
    color: red;
    font-weight: bold;
  }
  </style>
  