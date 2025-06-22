<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Quel personnage de Mario es-tu ?</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      background-color: #f5f5f5;
      color: #333;
      margin: 0;
      padding: 20px;
      text-align: center;
    }

    h1 {
      color: #e60012;
      font-size: 36px;
      margin-bottom: 20px;
    }

    img.logo {
      max-width: 250px;
      margin-bottom: 20px;
    }

    .question {
      margin: 20px auto;
      background-color: #fff3d4;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
      max-width: 600px;
    }

    .options button {
      background-color: #ffcc00;
      color: #000;
      padding: 10px 20px;
      border: none;
      margin: 8px;
      font-size: 16px;
      cursor: pointer;
      border-radius: 5px;
      transition: 0.3s;
    }

    .options button:hover {
      background-color: #e6b800;
      transform: scale(1.05);
    }

    .result {
      background-color: #d1f7ff;
      padding: 20px;
      border-radius: 12px;
      margin-top: 30px;
      display: none;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
      max-width: 600px;
      margin-left: auto;
      margin-right: auto;
    }

    .score {
      font-size: 16px;
      margin-top: 10px;
      color: #555;
    }
  </style>
</head>
<body>
  <img class="logo" src="https://zupimages.net/up/25/25/uaza.jpg" alt="Logo Mario">
  <h1>Quel personnage de Mario es-tu ?</h1>

  <div id="quiz-container">
    <div class="question" id="question-container">
      <h2 id="question-text"></h2>
      <div class="options" id="options-container"></div>
    </div>
  </div>

  <div class="result" id="result-container">
    <h2>Tu es...</h2>
    <p id="result-text"></p>
    <p class="score">Basé sur tes réponses !</p>
    <button onclick="startQuiz()">Recommencer</button>
  </div>

  <script>
    const questions = [
      { question: "Quel est ton passe-temps préféré ?", options: ["Sauter partout", "Sauver les autres", "Faire la fête", "Rire méchamment"], scores: ["Mario", "Luigi", "Peach", "Bowser"] },
      { question: "Ton atout principal ?", options: ["Force", "Vitesse", "Charme", "Stratégie"], scores: ["Donkey Kong", "Toad", "Daisy", "Bowser"] },
      { question: "Ton plat préféré ?", options: ["Spaghetti", "Champignons", "Gâteaux", "Pizza"], scores: ["Mario", "Toad", "Peach", "Wario"] },
      { question: "Ta plus grande peur ?", options: ["Les fantômes", "Les hauteurs", "L’échec", "L’ennui"], scores: ["Luigi", "Peach", "Mario", "Wario"] },
      { question: "Ta qualité principale ?", options: ["Héroïsme", "Loyauté", "Gentillesse", "Courage"], scores: ["Mario", "Luigi", "Toad", "Yoshi"] }
    ];

    const characters = {
      "Mario": { name: "Mario", description: "Le héros intrépide toujours prêt à sauver le royaume Champignon." },
      "Luigi": { name: "Luigi", description: "Le frère loyal qui surmonte ses peurs pour aider les autres." },
      "Peach": { name: "Peach", description: "Gracieuse et forte, elle sait prendre les choses en main quand il le faut." },
      "Bowser": { name: "Bowser", description: "Le roi des Koopas, ambitieux et puissant, avec un fond parfois attendrissant." },
      "Toad": { name: "Toad", description: "Petit mais courageux, toujours prêt à aider dans l’ombre." },
      "Daisy": { name: "Daisy", description: "Énergique et audacieuse, elle apporte de la fraîcheur partout où elle passe." },
      "Wario": { name: "Wario", description: "Rusé, cupide mais diablement drôle et imprévisible." },
      "Yoshi": { name: "Yoshi", description: "Fidèle et agile, il transporte toujours ses amis avec enthousiasme." },
      "Donkey Kong": { name: "Donkey Kong", description: "Fort et bienveillant, il ne recule devant rien pour défendre ses amis." }
    };

    let currentQuestion = 0;
    const userScores = {};

    function startQuiz() {
      currentQuestion = 0;
      for (let char in characters) userScores[char] = 0;
      document.getElementById('result-container').style.display = 'none';
      document.getElementById('quiz-container').style.display = 'block';
      showQuestion();
    }

    function showQuestion() {
      const question = questions[currentQuestion];
      document.getElementById('question-text').innerText = question.question;

      const optionsContainer = document.getElementById('options-container');
      optionsContainer.innerHTML = '';

      question.options.forEach((option, index) => {
        const button = document.createElement('button');
        button.innerText = option;
        button.onclick = () => {
          const char = question.scores[index];
          userScores[char] += 1;
          currentQuestion++;
          if (currentQuestion < questions.length) {
            showQuestion();
          } else {
            showResult();
          }
        };
        optionsContainer.appendChild(button);
      });
    }

    function showResult() {
      let topCharacter = null;
      let maxScore = -1;
      for (let char in userScores) {
        if (userScores[char] > maxScore) {
          topCharacter = char;
          maxScore = userScores[char];
        }
      }

      const result = characters[topCharacter];
      document.getElementById('result-text').innerText = `${result.name} - ${result.description}`;
      document.getElementById('quiz-container').style.display = 'none';
      document.getElementById('result-container').style.display = 'block';
    }

    startQuiz();
  </script>
</body>
</html>
