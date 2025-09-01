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
    .quiz-container {
      max-width: 600px;
      margin: auto;
      background: white;
      padding: 20px;
      border-radius: 15px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
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
    .options input {
      margin-right: 10px;
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
  <div class="quiz-container" id="quiz">
    <h2 id="section-title">सेक्शन: HISTORY</h2>
    <div id="question-container"></div>
    <div class="buttons">
      <button class="prev" onclick="prevQuestion()">Previous</button>
      <button class="next" onclick="nextQuestion()">Next</button>
      <button class="finish" onclick="showResult()">Finish</button>
    </div>
    <div id="result-container" style="display:none;"></div>
  </div>

  <script>
    // दो sections के सवाल
    const sections = {
      "HISTORY": [
        {
          question: "ताजमहल किसने बनवाया था?",
          options: ["अकबर", "शाहजहाँ", "औरंगज़ेब", "बाबर"],
          answer: "शाहजहाँ"
        },
        {
          question: "1857 की क्रांति का प्रथम स्वतंत्रता संग्राम कहाँ शुरू हुआ?",
          options: ["मेरठ", "दिल्ली", "लखनऊ", "कानपुर"],
          answer: "मेरठ"
        }
      ],
      "ECONOMICS": [
        {
          question: "भारत में मुद्रा किस संस्था द्वारा जारी की जाती है?",
          options: ["SBI", "वित्त मंत्रालय", "RBI", "SEBI"],
          answer: "RBI"
        },
        {
          question: "GDP का पूरा रूप क्या है?",
          options: ["Gross Domestic Product", "Global Development Plan", "General Domestic Policy", "Gross Development Program"],
          answer: "Gross Domestic Product"
        }
      ]
    };

    let sectionNames = Object.keys(sections);
    let currentSectionIndex = 0;
    let currentQuestion = 0;
    let userAnswers = {};

    function loadQuestion() {
      let section = sectionNames[currentSectionIndex];
      let questions = sections[section];

      document.getElementById("section-title").innerText = "सेक्शन: " + section;

      if (questions.length === 0) {
        document.getElementById("question-container").innerHTML = "<p>⚠️ इस सेक्शन में कोई प्रश्न नहीं है।</p>";
        document.querySelector(".buttons").style.display="none";
        return;
      }

      const q = questions[currentQuestion];
      document.getElementById("question-container").innerHTML = `
        <div class="question">Q${currentQuestion+1}: ${q.question}</div>
        <div class="options">
          ${q.options.map((opt,i)=>`
            <label>
              <input type="radio" name="option" value="${opt}" ${(userAnswers[section] && userAnswers[section][currentQuestion]===opt) ? "checked":""}>
              ${String.fromCharCode(65+i)}. ${opt}
            </label>
          `).join('')}
        </div>
      `;
    }

    function saveAnswer(){
      let section = sectionNames[currentSectionIndex];
      let selected = document.querySelector('input[name="option"]:checked');
      if(!userAnswers[section]) userAnswers[section] = [];
      if(selected){
        userAnswers[section][currentQuestion] = selected.value;
      }
    }

    function nextQuestion() {
      saveAnswer();
      let section = sectionNames[currentSectionIndex];
      let questions = sections[section];
      if(currentQuestion < questions.length-1){
        currentQuestion++;
      } else if(currentSectionIndex < sectionNames.length-1){
        currentSectionIndex++;
        currentQuestion = 0;
      }
      loadQuestion();
    }

    function prevQuestion() {
      saveAnswer();
      if(currentQuestion > 0){
        currentQuestion--;
      } else if(currentSectionIndex > 0){
        currentSectionIndex--;
        let prevSection = sectionNames[currentSectionIndex];
        currentQuestion = sections[prevSection].length-1;
      }
      loadQuestion();
    }

    function showResult(){
      saveAnswer();
      let resultHTML = "<h2>परिणाम / Result</h2>";
      let totalScore = 0, totalQuestions = 0;

      sectionNames.forEach(section=>{
        let questions = sections[section];
        resultHTML += `<h3>सेक्शन: ${section}</h3>`;
        questions.forEach((q,i)=>{
          let correct = q.answer;
          let user = (userAnswers[section] && userAnswers[section][i]) || "कोई जवाब नहीं";
          if(user === correct) totalScore++;
          resultHTML += `
            <div>
              <b>Q${i+1}:</b> ${q.question}<br>
              आपका जवाब: <span class="${user===correct?'correct':'wrong'}">${user}</span><br>
              सही जवाब: <span class="correct">${correct}</span><br><br>
            </div>
          `;
        });
        totalQuestions += questions.length;
      });

      resultHTML += `<h3>आपका कुल स्कोर: ${totalScore} / ${totalQuestions}</h3>`;
      resultHTML += `<button class="restart" onclick="restartQuiz()">Restart Test</button>`;

      document.getElementById("question-container").style.display="none";
      document.querySelector(".buttons").style.display="none";
      const resultBox = document.getElementById("result-container");
      resultBox.style.display="block";
      resultBox.innerHTML = resultHTML;
    }

    function restartQuiz(){
      currentSectionIndex = 0;
      currentQuestion = 0;
      userAnswers = {};
      document.getElementById("question-container").style.display="block";
      document.querySelector(".buttons").style.display="block";
      document.getElementById("result-container").style.display="none";
      loadQuestion();
    }

    loadQuestion();
  </script>

</body>
</html>
