<template>
  <div class="calculator-container">
    <h1 class="title">Calculadora de Fracciones</h1>
    <div class="calculator">
      <div class="fraction-input">
        <div class="fraction-box">
          <input 
            v-model.number="numerator1" 
            type="number" 
            placeholder="Num"
            class="fraction-input-field numerator"
          >
          <div class="fraction-line"></div>
          <input 
            v-model.number="denominator1" 
            type="number" 
            placeholder="Den"
            class="fraction-input-field denominator"
          >
        </div>

        <select v-model="operation" class="operation-select">
          <option value="+">+</option>
          <option value="-">−</option>
          <option value="*">×</option>
          <option value="/">÷</option>
        </select>

        <div class="fraction-box">
          <input 
            v-model.number="numerator2" 
            type="number" 
            placeholder="Num"
            class="fraction-input-field numerator"
          >
          <div class="fraction-line"></div>
          <input 
            v-model.number="denominator2" 
            type="number" 
            placeholder="Den"
            class="fraction-input-field denominator"
          >
        </div>

        <button @click="calculate" class="equals-btn" :class="{ 'pulse': isCalculating }">
          =
        </button>
      </div>

      <transition name="fade">
        <div v-if="result" class="result">
          <p class="result-text">Resultado:</p>
          <div class="fraction-result">{{ result }}</div>
        </div>
      </transition>

      <transition name="slide">
        <div v-if="error" class="error">
          <span class="error-icon">⚠️</span>
          {{ error }}
        </div>
      </transition>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const numerator1 = ref(null)
const denominator1 = ref(null)
const numerator2 = ref(null)
const denominator2 = ref(null)
const operation = ref('+')
const result = ref('')
const error = ref('')
const isCalculating = ref(false)

function calculateGCD(a, b) {
  return b === 0 ? a : calculateGCD(b, a % b)
}

function calculate() {
  error.value = ''
  result.value = ''
  isCalculating.value = true

  if (!numerator1.value || !denominator1.value || !numerator2.value || !denominator2.value) {
    error.value = 'Por favor, complete todos los campos'
    isCalculating.value = false
    return
  }

  if (denominator1.value === 0 || denominator2.value === 0) {
    error.value = 'El denominador no puede ser cero'
    isCalculating.value = false
    return
  }

  let resultNum, resultDen

  switch(operation.value) {
    case '+':
      resultNum = (numerator1.value * denominator2.value) + (numerator2.value * denominator1.value)
      resultDen = denominator1.value * denominator2.value
      break
    case '-':
      resultNum = (numerator1.value * denominator2.value) - (numerator2.value * denominator1.value)
      resultDen = denominator1.value * denominator2.value
      break
    case '*':
      resultNum = numerator1.value * numerator2.value
      resultDen = denominator1.value * denominator2.value
      break
    case '/':
      if (numerator2.value === 0) {
        error.value = 'No se puede dividir por cero'
        isCalculating.value = false
        return
      }
      resultNum = numerator1.value * denominator2.value
      resultDen = denominator1.value * numerator2.value
      break
  }

  const gcd = calculateGCD(Math.abs(resultNum), Math.abs(resultDen))
  resultNum = resultNum / gcd
  resultDen = resultDen / gcd

  setTimeout(() => {
    result.value = `${resultNum}/${resultDen}`
    isCalculating.value = false
  }, 300)
}
</script>

<style scoped>
.calculator-container {
  max-width: 800px;
  margin: 2rem auto;
  padding: 2rem;
  background: linear-gradient(145deg, #ffffff, #f0f0f0);
  border-radius: 20px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}

.title {
  text-align: center;
  color: #2d3748;
  font-size: 2rem;
  margin-bottom: 2rem;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
}

.calculator {
  background: white;
  padding: 2rem;
  border-radius: 15px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
}

.fraction-input {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 1.5rem;
  margin-bottom: 2rem;
}

.fraction-box {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
  animation: slideIn 0.5s ease-out;
}

.fraction-input-field {
  width: 80px;
  height: 40px;
  text-align: center;
  border: 2px solid #e2e8f0;
  border-radius: 8px;
  font-size: 1.2rem;
  transition: all 0.3s ease;
  background: #f8fafc;
}

.fraction-input-field:focus {
  outline: none;
  border-color: #3b82f6;
  box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.2);
}

.fraction-line {
  width: 100%;
  height: 2px;
  background-color: #3b82f6;
  margin: 4px 0;
  animation: scaleIn 0.5s ease-out;
}

.operation-select {
  width: 60px;
  height: 40px;
  font-size: 1.5rem;
  border: 2px solid #e2e8f0;
  border-radius: 8px;
  background: #f8fafc;
  cursor: pointer;
  transition: all 0.3s ease;
}

.operation-select:focus {
  outline: none;
  border-color: #3b82f6;
}

.equals-btn {
  width: 50px;
  height: 50px;
  font-size: 1.5rem;
  border: none;
  border-radius: 50%;
  background: #3b82f6;
  color: white;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 4px 6px rgba(59, 130, 246, 0.2);
}

.equals-btn:hover {
  transform: scale(1.1);
  background: #2563eb;
}

.equals-btn.pulse {
  animation: pulse 0.5s ease-out;
}

.result {
  text-align: center;
  margin-top: 2rem;
  padding: 1rem;
  background: #f0f9ff;
  border-radius: 10px;
  animation: fadeIn 0.5s ease-out;
}

.result-text {
  color: #3b82f6;
  font-size: 1.2rem;
  margin-bottom: 0.5rem;
}

.fraction-result {
  font-size: 1.5rem;
  font-weight: bold;
  color: #2d3748;
}

.error {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
  margin-top: 1rem;
  padding: 1rem;
  background: #fee2e2;
  color: #dc2626;
  border-radius: 10px;
  font-size: 0.9rem;
}

.error-icon {
  font-size: 1.2rem;
}

/* Animaciones */
@keyframes slideIn {
  from {
    opacity: 0;
    transform: translateY(-20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes scaleIn {
  from {
    transform: scaleX(0);
  }
  to {
    transform: scaleX(1);
  }
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes pulse {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.2);
  }
  100% {
    transform: scale(1);
  }
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.slide-enter-active,
.slide-leave-active {
  transition: all 0.3s ease;
}

.slide-enter-from,
.slide-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}

/* Responsive */
@media (max-width: 600px) {
  .calculator-container {
    margin: 1rem;
    padding: 1rem;
  }

  .fraction-input {
    flex-direction: column;
    gap: 1rem;
  }

  .fraction-box {
    width: 100%;
  }

  .fraction-input-field {
    width: 100%;
    max-width: 200px;
  }
}
</style>