<!DOCTYPE html>
<html lang="hi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Smart Shankar Quiz</title>
  <style>
    body { font-family: Arial, sans-serif; text-align: center; background: #f2f2f2; }
    .menu, .quiz, .topics { margin-top: 20px; }
    button {
      padding: 10px 20px;
      margin: 10px;
      background: #00cc66;
      color: white;
      border: none;
      border-radius: 25px;
      cursor: pointer;
      font-size: 16px;
    }
    button:hover { background: #00994d; }
    .options button { display: block; margin: 5px auto; width: 60%; }
    .correct { color: green; font-weight: bold; }
    .wrong { color: red; font-weight: bold; }
    #result-container { background: #fff; margin: 20px auto; padding: 20px; border-radius: 10px; width: 80%; }
  </style>
</head>
<body>
  <h1>📘 Smart Shankar Quiz</h1>

  <!-- Section Menu -->
  <div id="section-menu" class="menu">
    <button onclick="openSection('history')">📖 History</button>
    <button onclick="openSection('economics')">💰 Economics</button>
  </div>

  <!-- Topic Menu -->
  <div id="topic-menu" class="topics" style="display:none"></div>

  <!-- Quiz Box -->
  <div id="quiz" class="quiz" style="display:none">
    <div id="question-container"></div>
    <div class="buttons">
      <button onclick="prevQuestion()">⬅ Prev</button>
      <button onclick="nextQuestion()">Next ➡</button>
      <button onclick="showResult()">✅ Submit</button>
    </div>
    <div id="result-container" style="display:none"></div>
  </div>

<script>
  let currentSection = "";
  let currentTopic = "";
  let currentQuestion = 0;
  let userAnswers = {};

  // All Questions Data
  const sections = {
    "history": {
      "Harappa": [
        {
          question: "हड़प्पा सभ्यता किस नदी के किनारे विकसित हुई?",
          options: ["गंगा", "सिंधु", "यमुना", "गोदावरी"],
          answer: "सिंधु"
        },
        {
          question: "मोहनजोदड़ो किस देश में स्थित है?",
          options: ["भारत", "पाकिस्तान", "नेपाल", "अफगानिस्तान"],
          answer: "पाकिस्तान"
        }
      ]
    },
    "economics": {
      "Basic Economics": [
        {
          question: "भारत में रुपया किस संस्था द्वारा जारी किया जाता है?",
          options: ["वित्त मंत्रालय", "आरबीआई", "सुप्रीम कोर्ट", "लोकसभा"],
          answer: "आरबीआई"
        },
        {
          question: "GDP का पूरा नाम क्या है?",
          options: ["Gross Domestic Product", "Global Domestic Product", "Gross Development Project", "General Domestic Plan"],
          answer: "Gross Domestic Product"
        }
      ]
    }
  };

  // Section Open
  function openSection(section){
    currentSection = section;
    document.getElementById("section-menu").style.display="none";
    let topicMenu = document.getElementById("topic-menu");
    topicMenu.style.display="block";
    topicMenu.innerHTML = `<h2>${section.toUpperCase()} Topics</h2>`;
    for(let topic in sections[section]){
      topicMenu.innerHTML += `<button onclick="startQuiz('${topic}')">${topic}</button>`;
    }
    topicMenu.innerHTML += `<br><button onclick="backToSections()">⬅ Back to Sections</button>`;
  }

  // Back to Section Menu
  function backToSections(){
    document.getElementById("topic-menu").style.display="none";
    document.getElementById("section-menu").style.display="block";
  }

  // Start Quiz
  function startQuiz(topic){
    currentTopic = topic;
    currentQuestion = 0;
    userAnswers = {};
    document.getElementById("topic-menu").style.display="none";
    document.getElementById("quiz").style.display="block";
    document.getElementById("question-container").style.display="block";
    document.querySelector(".buttons").style.display="block";
    document.getElementById("result-container").style.display="none";
    loadQuestion();
  }

  // Load Question
  function loadQuestion(){
    let questions = sections[currentSection][currentTopic];
    if(currentQuestion < 0) currentQuestion = 0;
    if(currentQuestion >= questions.length) currentQuestion = questions.length-1;

    let q = questions[currentQuestion];
    let container = document.getElementById("question-container");
    container.innerHTML = `<h2>Q${currentQuestion+1}: ${q.question}</h2><div class='options'></div>`;

    let optionsDiv = container.querySelector(".options");
    q.options.forEach(opt=>{
      let btn = document.createElement("button");
      btn.innerText = opt;
      btn.onclick = ()=>{ userAnswers[currentQuestion] = opt; highlightAnswers(); };
      optionsDiv.appendChild(btn);
    });
    highlightAnswers();
  }

  // Highlight Selected Answer
  function highlightAnswers(){
    let buttons = document.querySelectorAll(".options button");
    buttons.forEach(b=>{
      if(userAnswers[currentQuestion] === b.innerText){
        b.style.background="orange";
      } else {
        b.style.background="#00cc66";
      }
    });
  }

  // Navigation
  function nextQuestion(){ saveAnswer(); currentQuestion++; loadQuestion(); }
  function prevQuestion(){ saveAnswer(); currentQuestion--; loadQuestion(); }
  function saveAnswer(){}

  // Show Result
  function showResult(){
    saveAnswer();
    let questions = sections[currentSection][currentTopic];
    let resultHTML = "<h2>Result</h2>";
    let score = 0;

    questions.forEach((q,i)=>{
      let user = userAnswers[i] || "कोई जवाब नहीं";
      if(user === q.answer) score++;
      resultHTML += `
        <div>
          <b>Q${i+1}:</b> ${q.question}<br>
          आपका जवाब: <span class="${user===q.answer?'correct':'wrong'}">${user}</span><br>
          सही जवाब: <span class="correct">${q.answer}</span><br><br>
        </div>
      `;
    });

    resultHTML += `<h3>आपका स्कोर: ${score} / ${questions.length}</h3>`;
    resultHTML += `<button onclick="startQuiz('${currentTopic}')">🔄 Restart</button>`;
    resultHTML += `<button onclick="openSection('${currentSection}')">⬅ Back to Topics</button>`;

    document.getElementById("question-container").style.display="none";
    document.querySelector(".buttons").style.display="none";
    const resultBox = document.getElementById("result-container");
    resultBox.style.display="block";
    resultBox.innerHTML = resultHTML;
  }
</script>
</body>
</html>
