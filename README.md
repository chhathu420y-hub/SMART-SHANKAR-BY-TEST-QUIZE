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
