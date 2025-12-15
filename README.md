# ECOSISTEMA-
El Quiz del Ecosistema es un juego educativo digital diseñado para aprender de forma divertida, rápida e interactiva sobre los ecosistemas y su funcionamiento.  El juego consiste en una serie de 20 preguntas sencillas relacionadas con temas como el ecosistema, la sucesión ecológica, los ciclos naturales, la vulnerabilidad y la resiliencia. 
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <title>Quiz del Ecosistema</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #e8f5e9;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }
    .game {
      background: white;
      padding: 20px;
      border-radius: 12px;
      width: 90%;
      max-width: 500px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
    }
    h1 {
      text-align: center;
      color: #2e7d32;
    }
    .question {
      font-size: 18px;
      margin-bottom: 15px;
    }
    button {
      display: block;
      width: 100%;
      padding: 10px;
      margin: 8px 0;
      border: none;
      border-radius: 8px;
      background: #4caf50;
      color: white;
      font-size: 16px;
      cursor: pointer;
    }
    button:hover {
      background: #388e3c;
    }
    .score {
      margin-top: 15px;
      text-align: center;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <div class="game">
    <h1>🌍 Quiz del Ecosistema</h1>
    <div class="question" id="question"></div>
    <div id="answers"></div>
    <div class="score" id="score"></div>
  </div>

  <script>
    const questions = [
      { q: "¿Qué es un ecosistema?", a: ["Seres vivos y su ambiente", "Solo animales", "Solo plantas"], c: 0 },
      { q: "¿Qué es la sucesión ecológica?", a: ["Cambio del ecosistema con el tiempo", "Un animal", "Una enfermedad"], c: 0 },
      { q: "¿La sucesión ecológica ocurre rápido o lentamente?", a: ["Rápido", "Lentamente", "Nunca ocurre"], c: 1 },
      { q: "¿Qué proceso ocurre cuando unas plantas ayudan a otras a crecer?", a: ["Competencia", "Facilitación", "Depredación"], c: 1 },
      { q: "¿Cómo se llama cuando una especie impide que otra crezca?", a: ["Inhibición", "Facilitación", "Mutualismo"], c: 0 },

      { q: "¿Qué necesitan las plantas además del sol?", a: ["Ropa", "Agua y nutrientes", "Plástico"], c: 1 },
      { q: "¿Qué producen las plantas durante la fotosíntesis?", a: ["Oxígeno", "Humo", "Basura"], c: 0 },
      { q: "¿Qué ciclo natural produce el oxígeno que respiramos?", a: ["Ciclo del agua", "Ciclo del oxígeno", "Ciclo del suelo"], c: 1 },
      { q: "¿Los ciclos naturales se repiten o solo ocurren una vez?", a: ["Solo una vez", "Se repiten", "Nunca ocurren"], c: 1 },
      { q: "¿Qué ciclo incluye lluvia, ríos y nubes?", a: ["Ciclo del agua", "Ciclo del carbono", "Ciclo del oxígeno"], c: 0 },

      { q: "¿Qué ecosistema es más vulnerable?", a: ["Maduro", "Inmaduro", "Equilibrado"], c: 1 },
      { q: "¿Qué significa que un ecosistema sea resiliente?", a: ["Que no cambia", "Que se destruye", "Que se recupera fácilmente"], c: 2 },
      { q: "¿Un ecosistema con muchas especies es más…?", a: ["Débil", "Fuerte", "Peligroso"], c: 1 },
      { q: "¿La contaminación aumenta o disminuye la resiliencia?", a: ["La aumenta", "No afecta", "La disminuye"], c: 2 },
      { q: "¿Un ecosistema fuerte se recupera rápido o lento?", a: ["Rápido", "Lento", "Nunca"], c: 0 },

      { q: "¿Los seres humanos forman parte del ecosistema?", a: ["Sí", "No", "Solo algunos"], c: 0 },
      { q: "¿Los animales dependen de las plantas?", a: ["No", "Sí", "Solo algunos"], c: 1 },
      { q: "¿Los ecosistemas solo existen en bosques?", a: ["Sí", "No", "Solo en selvas"], c: 1 },
      { q: "¿Cuidar el ecosistema es importante?", a: ["No", "Sí", "Solo a veces"], c: 1 },
      { q: "¿Las plantas son importantes para la vida?", a: ["No", "Sí", "Solo para animales"], c: 1 }
    ];

    let index = 0;
    let score = 0;

    function loadQuestion() {
      const q = questions[index];
      document.getElementById("question").textContent = q.q;
      const answersDiv = document.getElementById("answers");
      answersDiv.innerHTML = "";
      q.a.forEach((text, i) => {
        const btn = document.createElement("button");
        btn.textContent = text;
        btn.onclick = () => checkAnswer(i);
        answersDiv.appendChild(btn);
      });
    }

    function checkAnswer(i) {
      if (i === questions[index].c) {
        score++;
        alert("¡Correcto! ✅");
      } else {
        alert("Incorrecto ❌");
      }
      index++;
      if (index < questions.length) {
        loadQuestion();
      } else {
        document.getElementById("question").textContent = "¡Juego terminado! 🎉";
        document.getElementById("answers").innerHTML = "";
        document.getElementById("score").textContent = "Puntaje final: " + score;
      }
    }

    loadQuestion();
  </script>
</body>
</html>
