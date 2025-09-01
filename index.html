<!DOCTYPE html>
<html lang="hi">
<head>
  <meta charset="UTF-8">
  <title>Quiz App</title>
  <style>
    #quiz, #question-container, #result-container { display:none; }
    .buttons { margin-top: 10px; }
  </style>
</head>
<body>
  <div id="topic-menu">
    <h2>Choose Section</h2>
    <button onclick="startQuiz('history')">History</button>
    <button onclick="startQuiz('economics')">Economics</button>
  </div>

  <div id="quiz">
    <div id="question-container"></div>
    <div class="buttons">
      <button onclick="prevQuestion()">⬅ Prev</button>
      <button onclick="nextQuestion()">Next ➡</button>
      <button onclick="showResult()">✅ Finish</button>
    </div>
  </div>

  <div id="result-container"></div>

  <!-- अब JS को <script> टैग के अंदर डालो -->
  <script>
    let sections = {
      history: {
        harappa: [
          {question:"हड़प्पा सभ्यता कहाँ स्थित थी?", options:["सिंधु घाटी","मेसोपोटामिया","मिस्र","चीन"], answer:"सिंधु घाटी"},
          {question:"मोहनजोदड़ो किस नदी के किनारे था?", options:["सिंधु","गंगा","यमुना","नर्मदा"], answer:"सिंधु"}
        ]
      },
      economics: {
        basics: [
          {question:"भारत की मुद्रा क्या है?", options:["डॉलर","रुपया","पौंड","यूरो"], answer:"रुपया"}
        ]
      }
    };

    let currentSection = "history";
    let currentTopic = "harappa";
    let currentQuestion = 0;
    let userAnswers = {};

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

    function loadQuestion(){
      let questions = sections[currentSection][currentTopic];
      let q = questions[currentQuestion];
      let html = `<h3>Q${currentQuestion+1}. ${q.question}</h3>`;
      q.options.forEach(opt=>{
        let checked = userAnswers[currentQuestion]===opt ? "checked" : "";
        html += `<label><input type="radio" name="q${currentQuestion}" value="${opt}" ${checked}> ${opt}</label><br>`;
      });
      document.getElementById("question-container").innerHTML = html;
    }

    function saveAnswer(){
      let selected = document.querySelector(`input[name="q${currentQuestion}"]:checked`);
      if(selected) userAnswers[currentQuestion] = selected.value;
    }

    function nextQuestion(){
      saveAnswer();
      let questions = sections[currentSection][currentTopic];
      if(currentQuestion < questions.length-1){
        currentQuestion++;
        loadQuestion();
      }
    }

    function prevQuestion(){
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
        let correct = (user === q.answer);
        if(correct) score++;
        resultHTML += `
          <div style="margin-bottom:10px; padding:8px; border:1px solid #ddd; border-radius:8px;">
            <p><b>Q${i+1}: ${q.question}</b></p>
            <p>आपका जवाब: <span style="color:${correct ? 'green' : 'red'}">${user}</span></p>
            <p>सही जवाब: <b style="color:green">${q.answer}</b></p>
          </div>
        `;
      });

      resultHTML += `<h3>आपका स्कोर: ${score} / ${questions.length}</h3>`;
      resultHTML += `<button onclick="restartQuiz()">🔄 Restart</button>`;

      document.getElementById("quiz").style.display="none";
      document.getElementById("result-container").style.display="block";
      document.getElementById("result-container").innerHTML = resultHTML;
    }

    function restartQuiz(){
      currentQuestion = 0;
      userAnswers = {};
      document.getElementById("quiz").style.display="none";
      document.getElementById("result-container").style.display="none";
      document.getElementById("topic-menu").style.display="block";
    }
  </script>
</body>
</html>
