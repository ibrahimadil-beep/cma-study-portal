# Section D Practice Exam

<div class="exam-container" id="examEngine">
  <div class="exam-header">
    <span class="exam-title" id="examStatus">Question 1 of 2</span>
    <span class="exam-timer" id="examTimer">⏱️ 00:00</span>
  </div>
  <div class="progress-bar-bg">
    <div class="progress-bar-fill" id="progressBar"></div>
  </div>

  <div id="quizBody">
    <div class="question-box" id="qText"></div>
    <div id="optionsContainer"></div>
    <div class="explanation-box" id="explanationBox"></div>
  </div>

  <div class="exam-nav">
    <button class="btn btn-secondary" id="prevBtn" onclick="prevQuestion()">← Previous</button>
    <div>
      <button class="btn btn-primary" id="checkBtn" onclick="checkAnswer()">Confirm Answer</button>
      <button class="btn btn-success" id="nextBtn" onclick="nextQuestion()" style="display:none;">Next Question →</button>
      <button class="btn btn-success" id="finishBtn" onclick="finishExam()" style="display:none;">Submit Exam</button>
    </div>
  </div>
</div>

<div id="scoreScreen" class="exam-container" style="display: none; text-align: center;">
  <h2>Exam Completed! 🎉</h2>
  <h1 id="scoreDisplay" style="color: #0969da; font-size: 2.5rem; margin: 15px 0;"></h1>
  <p id="scoreMessage" style="font-size: 1.15rem; color: #57606a;"></p>
  <div style="margin-top: 30px; display: flex; justify-content: center; gap: 15px;">
    <button class="btn btn-primary" onclick="restartExam()">🔄 Retake Exam</button>
    <a href="section-e-practice.html" class="btn btn-success">Next: Section E Exam →</a>
    <a href="../README.html" class="btn btn-secondary">🏠 Portal Home</a>
  </div>
</div>

<script>
  const questions = JSON.parse("[{&quot;q&quot;: &quot;According to the Object-Dependent Rule, a factory supervisor's salary is classified as:&quot;, &quot;options&quot;: [&quot;(A) Direct to a product unit, indirect to the department.&quot;, &quot;(B) Direct to the department, indirect to a single product unit.&quot;, &quot;(C) Period cost expensed immediately.&quot;, &quot;(D) Fixed selling expense.&quot;], &quot;ans&quot;: 1, &quot;exp&quot;: &quot;The salary can be directly traced to the production department, but must be allocated indirectly to individual product units.&quot;}, {&quot;q&quot;: &quot;How is normal spoilage accounted for in a manufacturing process?&quot;, &quot;options&quot;: [&quot;(A) Expensed immediately as a period loss.&quot;, &quot;(B) Capitalized as an inventoriable product cost.&quot;, &quot;(C) Deducted directly from equity.&quot;, &quot;(D) Charged to selling expenses.&quot;], &quot;ans&quot;: 1, &quot;exp&quot;: &quot;Normal spoilage is considered an inherent cost of production and is capitalized into inventory.&quot;}]");
  let curIndex = 0;
  let userAnswers = new Array(questions.length).fill(null);
  let timerSeconds = 0;
  let timerInterval = setInterval(() => {
    timerSeconds++;
    const m = String(Math.floor(timerSeconds / 60)).padStart(2, '0');
    const s = String(timerSeconds % 60).padStart(2, '0');
    const t = document.getElementById('examTimer');
    if (t) t.innerText = `⏱️ ${m}:${s}`;
  }, 1000);

  function loadQuestion() {
    const q = questions[curIndex];
    document.getElementById('examStatus').innerText = `Question ${curIndex + 1} of ${questions.length}`;
    document.getElementById('progressBar').style.width = `${((curIndex + 1) / questions.length) * 100}%`;
    document.getElementById('qText').innerText = q.q;

    const container = document.getElementById('optionsContainer');
    container.innerHTML = '';

    q.options.forEach((opt, idx) => {
      const label = document.createElement('label');
      label.className = 'option-label';
      label.id = `optLabel_${idx}`;

      const input = document.createElement('input');
      input.type = 'radio';
      input.name = 'examOption';
      input.value = idx;
      input.checked = (userAnswers[curIndex] === idx);

      label.appendChild(input);
      label.appendChild(document.createTextNode(opt));
      label.onclick = () => {
        if (label.getAttribute('data-locked') !== 'true') {
          input.checked = true;
          userAnswers[curIndex] = idx;
        }
      };
      container.appendChild(label);
    });

    document.getElementById('explanationBox').style.display = 'none';
    document.getElementById('prevBtn').disabled = (curIndex === 0);

    if (userAnswers[curIndex] !== null) {
      highlightResults();
    } else {
      document.getElementById('checkBtn').style.display = 'inline-block';
      document.getElementById('nextBtn').style.display = 'none';
      document.getElementById('finishBtn').style.display = 'none';
    }
  }

  function checkAnswer() {
    const selected = userAnswers[curIndex];
    if (selected === null) {
      alert('Please select an option before confirming.');
      return;
    }
    highlightResults();
  }

  function highlightResults() {
    const q = questions[curIndex];
    const selected = userAnswers[curIndex];

    q.options.forEach((_, idx) => {
      const lbl = document.getElementById(`optLabel_${idx}`);
      lbl.setAttribute('data-locked', 'true');
      if (idx === q.ans) {
        lbl.classList.add('correct');
      } else if (idx === selected) {
        lbl.classList.add('incorrect');
      }
    });

    const exp = document.getElementById('explanationBox');
    exp.innerHTML = `<strong>${selected === q.ans ? '✅ Correct!' : '❌ Incorrect.'}</strong><br>${q.exp}`;
    exp.style.display = 'block';

    document.getElementById('checkBtn').style.display = 'none';
    if (curIndex < questions.length - 1) {
      document.getElementById('nextBtn').style.display = 'inline-block';
      document.getElementById('finishBtn').style.display = 'none';
    } else {
      document.getElementById('nextBtn').style.display = 'none';
      document.getElementById('finishBtn').style.display = 'inline-block';
    }
  }

  function nextQuestion() {
    if (curIndex < questions.length - 1) {
      curIndex++;
      loadQuestion();
    }
  }

  function prevQuestion() {
    if (curIndex > 0) {
      curIndex--;
      loadQuestion();
    }
  }

  function finishExam() {
    clearInterval(timerInterval);
    document.getElementById('examEngine').style.display = 'none';
    const scoreScreen = document.getElementById('scoreScreen');
    scoreScreen.style.display = 'block';

    let correctCount = 0;
    questions.forEach((q, idx) => {
      if (userAnswers[idx] === q.ans) correctCount++;
    });

    const pct = Math.round((correctCount / questions.length) * 100);
    document.getElementById('scoreDisplay').innerText = `${correctCount} / ${questions.length} (${pct}%)`;
    document.getElementById('scoreMessage').innerText = pct >= 75 
      ? 'Congratulations! You met the passing standard (≥75%) for this CMA Part 1 drill.'
      : 'You scored below the 75% target benchmark. Review the explanations and retake the drill.';
  }

  function restartExam() {
    userAnswers.fill(null);
    curIndex = 0;
    timerSeconds = 0;
    document.getElementById('scoreScreen').style.display = 'none';
    document.getElementById('examEngine').style.display = 'block';
    loadQuestion();
  }

  document.addEventListener("DOMContentLoaded", loadQuestion);
</script>
