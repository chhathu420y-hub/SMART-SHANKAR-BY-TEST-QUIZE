<!DOCTYPE html>
<html lang="hi">
<head>
  <meta charset="UTF-8">
  <title>SMART SHANKAR QUIZE TEST</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f9;
      text-align: center;
      padding: 20px;
    }
    h1 {
      color: #333;
    }
    .btn {
      display: inline-block;
      background: #00c853;
      color: white;
      padding: 12px 20px;
      margin: 10px;
      border-radius: 25px;
      font-size: 18px;
      text-decoration: none;
      cursor: pointer;
      transition: 0.3s;
    }
    .btn:hover {
      background: #009624;
    }
    .quiz-container {
      max-width: 600px;
      margin: auto;
      background: white;
      padding: 20px;
      border-radius: 15px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      display:none;
    }
    .question {
      font-size: 20px;
      margin-bottom: 15px;
      text-align: left;
    }
    .options label {
      display: block;
      background: #eee;
      margin: 8px 0;
      padding: 10px;
      border-radius: 8px;
      cursor: pointer;
      text-align: left;
    }
    .buttons {
      margin-top: 20px;
    }
    button {
      padding: 10px 20px;
      margin: 5px;
      font-size: 16px;
      border: none;
      border-radius: 8px;
      cursor: pointer;
    }
    .next { background: #4CAF50; color: white; }
    .prev { background: #2196F3; color: white; }
    .finish { background: #f44336; color: white; }
    .restart { background: #ff9800; color: white; margin-top:20px; }
    .result {
      text-align: left;
      margin-top: 20px;
    }
    .correct { color: green; font-weight: bold; }
    .wrong { color: red; font-weight: bold; }
  </style>
</head>
<body>

  <h1>SMART SHANKAR QUIZE TEST</h1>

  <!-- Main Section Buttons -->
  <div id="main-menu">
    <div class="btn" onclick="openSection('HISTORY')">📘 HISTORY</div>
    <div class="btn" onclick="openSection('ECONOMICS')">📗 ECONOMICS</div>
  </div>

  <!-- Topics Menu -->
  <div id="topic-menu" style="display:none;">
    <h2 id="topic-title"></h2>
    <div id="topics"></div>
    <br>
    <button class="restart" onclick="backToMain()">⬅ Back</button>
  </div>

  <!-- Quiz Container -->
  <div class="quiz-container" id="quiz">
    <h2 id="section-title"></h2>
    <div id="question-container"></div>
    <div class="buttons">
      <button class="prev" onclick="prevQuestion()">Previous</button>
      <button class="next" onclick="nextQuestion()">Next</button>
      <button class="finish" onclick="showResult()">Finish</button>
    </div>
    <div id="result-container" style="display:none;"></div>
  </div>

  <script>
    // Data Structure
    const sections = {
      "HISTORY": {
        "HARAPPA": [
          {
            question: "हड़प्पा सभ्यता किस नदी के किनारे विकसित हुई थी?",
            options: ["गंगा", "सिंधु", "यमुना", "सरस्वती"],
            answer: "सिंधु"
          },
          {
            question: "हड़प्पा सभ्यता का मुख्य व्यवसाय क्या था?",
            options: ["कृषि", "व्यापार", "लोहा निर्माण", "पशुपालन"],
            answer: "कृषि"
          }
        ],
        "MAURYA": [
          {
            question: "मौर्य वंश का संस्थापक कौन था?",
            options: ["अशोक", "चंद्रगुप्त मौर्य", "बिंदुसार", "हर्षवर्धन"],
            answer: "चंद्रगुप्त मौर्य"
          }
        ]
      },
      "ECONOMICS": {
        "BANKING": [
          {
            question: "RBI की स्थापना कब हुई थी?",
            options: ["1930", "1935", "1947", "1950"],
            answer: "1935"
          }
        ]
      }
    };

    let currentSection = "";
    let currentTopic = "";
    let currentQuestion = 0;
    let userAnswers = {};

    // Show Topics
    function openSection(section) {
      currentSection = section;
      document.getElementById("main-menu").style.display="none";
      document.getElementById("topic-menu").style.display="block";
      document.getElementById("topic-title").innerText = "Choose Topic in " + section;

      let topicsHTML = "";
      Object.keys(sections[section]).forEach(topic=>{
        topicsHTML += `<div class="btn" onclick="startQuiz('${topic}')">📖 ${topic}</div>`;
      });
      document.getElementById("topics").innerHTML = topicsHTML;
    }

    // Back to Main
    function backToMain(){
      document.getElementById("topic-menu").style.display="none";
      document.getElementById("quiz").style.display="none";
      document.getElementById("main-menu").style.display="block";
      userAnswers = {};
    }

    // Start Quiz
    function startQuiz(topic){
      currentTopic = topic;
      currentQuestion = 0;
      document.getElementById("topic-menu").style.display="none";
      document.getElementById("quiz").style.display="block";
      loadQuestion();
    }

    // Load Question
    function loadQuestion() {
      let questions = sections[currentSection][currentTopic];
      const q = questions[currentQuestion];
      document.getElementById("section-title").innerText = currentSection + " → " + currentTopic;
      document.getElementById("question-container").innerHTML = `
        <div class="question">Q${currentQuestion+1}: ${q.question}</div>
        <div class="options">
          ${q.options.map((opt,i)=>`
            <label>
              <input type="radio" name="option" value="${opt}" ${(userAnswers[currentQuestion]===opt)?"checked":""}>
              ${String.fromCharCode(65+i)}. ${opt}
            </label>
          `).join('')}
        </div>
      `;
    }

    function saveAnswer(){
      let selected = document.querySelector('input[name="option"]:checked');
      if(selected){
        userAnswers[currentQuestion] = selected.value;
      }
    }

    function nextQuestion() {
      saveAnswer();
      let questions = sections[currentSection][currentTopic];
      if(currentQuestion < questions.length-1){
        currentQuestion++;
        loadQuestion();
      }
    }

    function prevQuestion() {
      saveAnswer();
      if(currentQuestion > 0){
        currentQuestion--;
        loadQuestion();
      }
    }

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
      resultHTML += `<button class="restart" onclick="startQuiz('${currentTopic}')">🔄 Restart</button>`;
      resultHTML += `<button class="restart" onclick="openSection('${currentSection}')">⬅ Back to Topics</button>`;

      document.getElementById("question-container").style.display="none";
      document.querySelector(".buttons").style.display="none";
      const resultBox = document.getElementById("result-container");
      resultBox.style.display="block";
      resultBox.innerHTML = resultHTML;
    }
  </script>

</body>
</html>
