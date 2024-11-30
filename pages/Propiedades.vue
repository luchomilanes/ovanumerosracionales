<template>
    <div class="propiedades-container">
      <h2>Propiedades de los Números Racionales</h2>
      <p>Los números racionales cumplen con varias propiedades importantes que los caracterizan en las operaciones matemáticas. A continuación, se explican las principales propiedades:</p>
      
      <div class="propiedad-card" v-for="(propiedad, index) in propiedades" :key="index">
        <h3>{{ propiedad.titulo }}</h3>
        <p>{{ propiedad.descripcion }}</p>
      </div>
    </div>
  </template>
  
  <script setup>
  const propiedades = [
    {
      titulo: "Propiedad de Cerradura",
      descripcion: "La suma, resta, multiplicación y división (excepto por cero) de dos números racionales es siempre otro número racional."
    },
    {
      titulo: "Propiedad Conmutativa",
      descripcion: "El orden de los números no afecta el resultado en la suma y multiplicación de números racionales: a + b = b + a y a × b = b × a."
    },
    {
      titulo: "Propiedad Asociativa",
      descripcion: "La forma en que se agrupan los números no afecta el resultado en la suma y multiplicación: (a + b) + c = a + (b + c) y (a × b) × c = a × (b × c)."
    },
    {
      titulo: "Existencia del Elemento Neutro",
      descripcion: "En la suma, el número 0 es el elemento neutro, ya que a + 0 = a. En la multiplicación, el número 1 es el elemento neutro, ya que a × 1 = a."
    },
    {
      titulo: "Existencia del Elemento Inverso",
      descripcion: "Todo número racional tiene un inverso aditivo (su opuesto) y un inverso multiplicativo (su recíproco, excepto el 0)."
    }
  ];
  </script>
  
  <style scoped>
  .propiedades-container {
    max-width: 800px;
    margin: auto;
    padding: 20px;
    background-color: #f9f9f9;
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
  
  .propiedad-card {
    background-color: #ffffff;
    padding: 15px;
    margin: 10px 0;
    border-radius: 8px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    transition: transform 0.2s;
    text-align: left;
  }
  
  .propiedad-card h3 {
    color: #388e3c;
    font-size: 18px;
    margin-bottom: 8px;
  }
  
  .propiedad-card p {
    color: #333;
  }
  
  .propiedad-card:hover {
    transform: scale(1.02);
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.15);
  }
  </style>
  