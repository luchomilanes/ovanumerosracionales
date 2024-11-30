<template>
<div class="rational-numbers">
        <!-- Sección Hero -->
        <div class="hero-section">
            <h1 class="main-title">Teoría de Números Racionales</h1>
            <div class="animated-fraction">
                <span class="numerator">a</span>
                <div class="fraction-line"></div>
                <span class="denominator">b</span>
            </div>
        </div>

        <!-- Sección Definición -->
        <section class="content-section definition">
            <h2>¿Qué son los números racionales?</h2>
            <p>Los números racionales son aquellos que pueden expresarse como el cociente de dos números enteros, 
               donde el denominador debe ser distinto de cero. Estos números son fundamentales en matemáticas y 
               tienen aplicaciones prácticas en la vida cotidiana.</p>
            <div class="formula">
                Q = { a/b | a, b ∈ Z, b ≠ 0 }
            </div>
            <p class="note">Donde Z representa el conjunto de números enteros y Q el conjunto de números racionales.</p>
        </section>

        <!-- Sección Características -->
        <section class="content-section characteristics">
            <h2>Características fundamentales</h2>
            <div class="cards-container">
                <div class="feature-card">
                    <h3>Representación</h3>
                    <ul>
                        <li>Fraccionaria (a/b)</li>
                        <li>Decimal exacta (0.5)</li>
                        <li>Decimal periódica (0.333...)</li>
                        <li>Notación científica</li>
                        <li>Porcentual (50%)</li>
                    </ul>
                </div>
                <div class="feature-card">
                    <h3>Propiedades algebraicas</h3>
                    <ul>
                        <li>Clausura en operaciones básicas</li>
                        <li>Conmutatividad</li>
                        <li>Asociatividad</li>
                        <li>Elemento neutro</li>
                        <li>Elemento inverso</li>
                    </ul>
                </div>
                <div class="feature-card">
                    <h3>Aplicaciones prácticas</h3>
                    <ul>
                        <li>Mediciones y proporciones</li>
                        <li>Análisis financiero</li>
                        <li>Probabilidad y estadística</li>
                        <li>Física y química</li>
                        <li>Vida cotidiana</li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- Sección Línea Numérica -->
        <div class="interactive-section">
            <h2>Línea numérica interactiva</h2>
            <div class="number-line">
                <div class="number-point" style="left: 0%;" title="-2"></div>
                <div class="number-point" style="left: 25%;" title="-1"></div>
                <div class="number-point" style="left: 50%;" title="0"></div>
                <div class="number-point" style="left: 75%;" title="1"></div>
                <div class="number-point" style="left: 100%;" title="2"></div>
            </div>
        </div>

        <!-- Sección Ejemplos -->
        <section class="content-section examples">
            <h2>Ejemplos y aplicaciones</h2>
            <div class="examples-grid">
                <div class="example-box">
                    <span class="example-title">Fracciones comunes</span>
                    <div class="example-content">
                        <p>1/2 = 0.5 = 50%</p>
                        <p>3/4 = 0.75 = 75%</p>
                        <p>2/5 = 0.4 = 40%</p>
                    </div>
                </div>
                <div class="example-box">
                    <span class="example-title">Decimales periódicos</span>
                    <div class="example-content">
                        <p>1/3 = 0.333...</p>
                        <p>2/3 = 0.666...</p>
                        <p>1/6 = 0.166...</p>
                    </div>
                </div>
                <div class="example-box">
                    <span class="example-title">Números mixtos</span>
                    <div class="example-content">
                        <p>1 1/2 = 3/2 = 1.5</p>
                        <p>2 3/4 = 11/4 = 2.75</p>
                        <p>3 1/3 = 10/3 = 3.333...</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Sección Problemas de Práctica -->
        <section class="content-section practice-problems">
            <h2>Problemas de práctica</h2>
            <div class="problem-card">
                <h3>Problema 1</h3>
                <p>Si tenemos una pizza dividida en 8 partes iguales y comemos 3 porciones, 
                   ¿qué fracción de la pizza queda?</p>
            </div>
            <div class="problem-card">
                <h3>Problema 2</h3>
                <p>Expresa 0.75 como una fracción en su mínima expresión.</p>
            </div>
            <div class="problem-card">
                <h3>Problema 3</h3>
                <p>¿Cuál es el resultado de sumar 2/3 + 3/4?</p>
            </div>
        </section>
    </div>
</template><!-- HTML -->
    

    <!-- Estilos CSS -->
    <style>
        /* Variables CSS */
        :root {
            --primary: #4f46e5;
            --secondary: #3b82f6;
            --accent: #f59e0b;
            --text: #334155;
            --bg-light: #f8fafc;
            --card-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }

        /* Estilos Generales */
        .rational-numbers {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
            font-family: 'Arial', sans-serif;
            color: var(--text);
            background-color: #fff;
        }

        /* Sección Hero */
        .hero-section {
            text-align: center;
            padding: 4rem 0;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            border-radius: 1.5rem;
            color: white;
            margin-bottom: 3rem;
            position: relative;
            overflow: hidden;
        }

        .hero-section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('/api/placeholder/1200/400') center/cover;
            opacity: 0.1;
            animation: pulse 4s infinite;
        }

        .main-title {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
            animation: slideDown 1s ease-out;
            position: relative;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
        }

        /* Fracción Animada */
        .animated-fraction {
            display: inline-flex;
            flex-direction: column;
            align-items: center;
            font-size: 3rem;
            margin: 2rem;
            animation: scaleIn 0.8s ease-out;
            background: rgba(255, 255, 255, 0.1);
            padding: 2rem;
            border-radius: 1rem;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
        }

        .fraction-line {
            width: 4rem;
            height: 3px;
            background-color: var(--accent);
            margin: 0.8rem 0;
            animation: expandWidth 1s ease-out;
        }

        /* Secciones de Contenido */
        .content-section {
            background: white;
            border-radius: 1.5rem;
            padding: 3rem;
            margin-bottom: 3rem;
            box-shadow: var(--card-shadow);
            transition: transform 0.3s ease;
        }

        .content-section:hover {
            transform: translateY(-5px);
        }

        .definition {
            background: linear-gradient(to right, #fff, var(--bg-light));
        }

        /* Fórmula */
        .formula {
            background: linear-gradient(135deg, var(--bg-light), #fff);
            padding: 2rem;
            border-radius: 1rem;
            text-align: center;
            font-size: 1.5rem;
            margin: 2rem 0;
            color: var(--primary);
            border: 2px solid rgba(79, 70, 229, 0.1);
            position: relative;
            overflow: hidden;
        }

        .formula::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, transparent, rgba(79, 70, 229, 0.1), transparent);
            animation: shine 3s infinite;
        }

        /* Tarjetas de Características */
        .cards-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .feature-card {
            background: var(--bg-light);
            padding: 2rem;
            border-radius: 1rem;
            transition: all 0.3s ease;
            border: 1px solid rgba(0, 0, 0, 0.1);
        }

        .feature-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
        }

        /* Ejemplos */
        .examples-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .example-box {
            background: var(--bg-light);
            padding: 2rem;
            border-radius: 1rem;
            text-align: center;
            transition: all 0.3s ease;
            border: 1px solid rgba(0, 0, 0, 0.1);
        }

        .example-box:hover {
            transform: scale(1.05);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
        }

        /* Línea Numérica */
        .number-line {
            height: 4px;
            background: var(--primary);
            margin: 2rem 0;
            position: relative;
        }

        .number-point {
            width: 12px;
            height: 12px;
            background: var(--accent);
            border-radius: 50%;
            position: absolute;
            top: 50%;
            transform: translate(-50%, -50%);
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .number-point:hover {
            transform: translate(-50%, -50%) scale(1.5);
        }

        /* Problemas de Práctica */
        .practice-problems {
            background: linear-gradient(135deg, var(--bg-light), #fff);
            padding: 2rem;
            border-radius: 1rem;
            margin-top: 2rem;
        }

        .problem-card {
            background: white;
            padding: 1.5rem;
            border-radius: 0.8rem;
            margin-bottom: 1rem;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
            transition: all 0.3s ease;
        }

        .problem-card:hover {
            transform: translateX(10px);
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }

        /* Animaciones */
        @keyframes slideDown {
            from {
                opacity: 0;
                transform: translateY(-50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes scaleIn {
            from {
                transform: scale(0);
            }
            to {
                transform: scale(1);
            }
        }

        @keyframes expandWidth {
            from {
                width: 0;
            }
            to {
                width: 4rem;
            }
        }

        @keyframes pulse {
            0% { opacity: 0.1; }
            50% { opacity: 0.2; }
            100% { opacity: 0.1; }
        }

        @keyframes shine {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }

        /* Media Queries */
        @media (max-width: 768px) {
            .rational-numbers {
                padding: 1rem;
            }
            
            .main-title {
                font-size: 2.5rem;
            }
            
            .content-section {
                padding: 1.5rem;
            }
            
            .cards-container {
                grid-template-columns: 1fr;
            }
        }
    </style>