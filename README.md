# Quizzes-game-
Quizzes game fantastic quizzes love it, 😁
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Brain Root Quiz Game</title>
  <style>
    body {
      font-family: 'Comic Sans MS', cursive, sans-serif;
      background: #ffeaa7;
      text-align: center;
      padding: 50px;
    }
    .container {
      max-width: 600px;
      margin: auto;
      background: #fff;
      padding: 30px;
      border-radius: 20px;
      box-shadow: 0 0 15px rgba(0,0,0,0.2);
    }
    h1 {
      color: #6c5ce7;
    }
    .question {
      font-size: 22px;
      margin: 20px 0;
    }
    .options button {
      display: block;
      margin: 10px auto;
      padding: 10px 20px;
      font-size: 18px;
      background: #74b9ff;
      border: none;
      border-radius: 10px;
      cursor: pointer;
    }
    .options button:hover {
      background: #0984e3;
      color: white;
    }
    .result {
      font-size: 20px;
      margin-top: 20px;
      color: green;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Brain Root Quiz</h1>
    <div class="question" id="question">Loading...</div>
    <div class="options" id="options"></div>
    <div class="result" id="result"></div>
  </div>

  <script>
    const questions = [
      {
        q: "How many months have 28 days?",
        options: ["1", "2", "All of them", "Only February"],
        answer: "All of them"
      },
      {
        q: "What is heavier: 1 kg of iron or 1 kg of cotton?",
        options: ["Iron", "Cotton", "Both are same", "None"],
        answer: "Both are same"
      },
      {
        q: "What breaks but never falls?",
        options: ["Glass", "Silence", "Daybreak", "Promise"],
        answer: "Daybreak"
      },
      {
        q: "If you have 3 apples and take away 2, how many do you have?",
        options: ["1", "2", "3", "0"],
        answer: "2"
      },
      {
        q: "Which word is spelled incorrectly in every dictionary?",
        options: ["Incorrectly", "Correctly", "Dictionary", "Spelled"],
        answer: "Incorrectly"
      }
    ];

    let current = 0;

    function loadQuestion() {
      const q = questions[current];
      document.getElementById('question').innerText = q.q;
      const optionsDiv = document.getElementById('options');
      optionsDiv.innerHTML = '';
      q.options.forEach(opt => {
        const btn = document.createElement('button');
        btn.innerText = opt;
        btn.onclick = () => checkAnswer(opt);
        optionsDiv.appendChild(btn);
      });
      document.getElementById('result').innerText = '';
    }

    function checkAnswer(selected) {
      const correct = questions[current].answer;
      if (selected === correct) {
        document.getElementById('result').innerText = "✅ Correct!";
        current++;
        if (current < questions.length) {
          setTimeout(loadQuestion, 1000);
        } else {
          document.getElementById('question').innerText = "🎉 You completed the quiz!";
          document.getElementById('options').innerHTML = '';
        }
      } else {
        document.getElementById('result').innerText = "❌ Try Again!";
      }
    }

    // Start the game
    loadQuestion();
  </script>
</body>
</html>
