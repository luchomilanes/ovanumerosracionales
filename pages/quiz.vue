<template>
    <div class="quiz-container">
      <h2>Quiz sobre Números Racionales</h2>
      <p>Responde las preguntas sobre los números racionales. ¡Buena suerte!</p>
  
      <div class="question-card" v-for="(question, index) in questions" :key="index">
        <p>{{ question.text }}</p>
        <div class="options">
          <label v-for="(option, optIndex) in question.options" :key="optIndex" class="option-label">
            <input type="radio" :name="'question' + index" :value="option" v-model="selectedAnswers[index]" />
            {{ option }}
          </label>
        </div>
      </div>
  
      <button @click="checkAnswers" :disabled="quizCompleted">Enviar respuestas</button>
      <button v-if="quizCompleted" @click="resetQuiz" class="reset-button">Reiniciar Quiz</button>
  
      <div v-if="quizCompleted" class="result">
        <h3>Tu Puntaje: {{ score }} / {{ questions.length }}</h3>
        <p v-if="score === questions.length">¡Perfecto! Todas tus respuestas son correctas.</p>
        <p v-else>Inténtalo de nuevo para mejorar tu puntuación.</p>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const questions = [
    {
      text: "¿Cuál de estos es un número racional?",
      options: ["√2", "3/4", "π", "-5"],
      correctAnswer: "3/4"
    },
    {
      text: "El valor de −17 + 49 = es:",
      options: ["32", "3/4", "-35", "-5"],
      correctAnswer: "32"
    },





    {
      text: "¿Qué propiedad de los números racionales se cumple en la suma?",
      options: ["Cerradura", "Conmutatividad", "Ambas", "Ninguna"],
      correctAnswer: "Ambas"
    },
    {
      text: "¿Cuál de estos números NO es un número racional?",
      options: ["0.25", "√3", "1/2", "5"],
      correctAnswer: "√3"
    },
    {
      text: "¿Cuál es el inverso multiplicativo de 3/4?",
      options: ["4/3", "-3/4", "3", "1/4"],
      correctAnswer: "4/3"
    }
  ];
  
  const selectedAnswers = ref(Array(questions.length).fill(null));
  const score = ref(0);
  const quizCompleted = ref(false);
  
  const checkAnswers = () => {
    score.value = 0;
    selectedAnswers.value.forEach((answer, index) => {
      if (answer === questions[index].correctAnswer) {
        score.value++;
      }
    });
    quizCompleted.value = true;
  };
  
  const resetQuiz = () => {
    selectedAnswers.value = Array(questions.length).fill(null);
    score.value = 0;
    quizCompleted.value = false;
  };
  </script>
  
  <style scoped>
  .quiz-container {
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
  }
  
  .question-card {
    background-color: #ffffff;
    padding: 15px;
    margin: 10px 0;
    border-radius: 8px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    text-align: left;
  }
  
  .options {
    margin-top: 10px;
  }
  
  .option-label {
    display: block;
    margin-bottom: 5px;
    font-size: 15px;
    color: #333;
  }
  
  button {
    padding: 10px 15px;
    margin-top: 20px;
    font-size: 16px;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  
  button:disabled {
    background-color: #bbb;
    cursor: not-allowed;
  }
  
  button:not(:disabled) {
    background-color: #1976d2;
  }
  
  button:not(:disabled):hover {
    background-color: #1565c0;
  }
  
  .reset-button {
    background-color: #d32f2f;
    margin-top: 10px;
    margin-left: 20px;
  }
  
  .reset-button:hover {
    background-color: #c62828;
  }
  
  .result {
    margin-top: 20px;
    font-size: 18px;
  }
  </style>
  