# Case Study 1: Variance Analysis Essay

<div class="exam-container">
  <h3>📋 Exam Case Scenario</h3>
  <div style="background: #f6f8fa; padding: 18px; border-radius: 8px; border-left: 4px solid #0969da; line-height: 1.6;">
    A manufacturing company uses a standard costing system. For 1,000 units produced, standard requirements are 4 lbs of Material X at $5.00/lb ($20,000 standard cost). Actual purchases and consumption were 4,200 lbs of Material X at $5.20/lb ($21,840 actual cost).
  </div>

  <h3 style="margin-top: 25px;">✍️ Required Tasks</h3>
  <ol style="line-height: 1.7; font-weight: 500;">
    <li>Calculate the Direct Material Price Variance and indicate whether it is Favorable (F) or Unfavorable (U).</li><li>Calculate the Direct Material Usage (Quantity) Variance and indicate F or U.</li><li>Evaluate possible operational causes for both variances occurring simultaneously.</li>
  </ol>

  <h3 style="margin-top: 25px;">💻 Candidate Essay Scratchpad</h3>
  <p style="color: #57606a; font-size: 0.95rem;">Type your complete responses below under real exam conditions. Track your word count before revealing the grading solution.</p>
  <textarea class="essay-textarea" id="essayInput" placeholder="Type your structured solution and essay here..." oninput="updateWordCount()"></textarea>
  <div style="display: flex; justify-content: space-between; align-items: center;">
    <span style="font-weight: bold; color: #57606a;" id="wordCount">Words: 0</span>
    <button class="btn btn-primary" onclick="toggleRubric()">Reveal Solution & Grading Rubric</button>
  </div>

  <div class="rubric-box" id="rubricBox">
    <h3 style="color: #1a7f37;">🎯 Official Model Solution & Grading Rubric</h3>
    
<p><strong>1. Direct Material Price Variance:</strong><br>
Formula: $AQ 	imes (AP - SP) = 4,200 	ext{ lbs} 	imes (\$5.20 - \$5.00) = \mathbf{\$840 	ext{ Unfavorable (U)}}$.<br>
<em>(Grading: 3 points for correct formula, substitution, and 'U' designation)</em></p>

<p><strong>2. Direct Material Usage Variance:</strong><br>
Formula: $SP 	imes (AQ - SQ) = \$5.00 	imes (4,200 	ext{ lbs} - 4,000 	ext{ lbs}) = \mathbf{\$1,000 	ext{ Unfavorable (U)}}$.<br>
<em>(Grading: 3 points for computing SQ = 4,000 lbs, correct variance, and 'U' designation)</em></p>

<p><strong>3. Operational Analysis:</strong><br>
Normally, purchasing higher-priced material ($5.20 vs $5.00) is justified if it leads to less scrap and waste. Here, both price and usage were unfavorable, indicating severe operational inefficiency, poorly calibrated machinery, or untrained laborers ruining premium raw material.<br>
<em>(Grading: 4 points for linking price and quality to efficiency)</em></p>

  </div>
</div>

<script>
  function updateWordCount() {
    const text = document.getElementById('essayInput').value.trim();
    const words = text ? text.split(/\s+/).length : 0;
    document.getElementById('wordCount').innerText = `Words: ${words}`;
  }
  function toggleRubric() {
    const box = document.getElementById('rubricBox');
    box.style.display = (box.style.display === 'block') ? 'none' : 'block';
  }
</script>


<div class="nav-buttons"><a href="../mcqs/section-e-practice.html" class="nav-btn">← Section E MCQs</a><a href="../README.html" class="nav-btn home">🏠 Home</a><a href="case-study-2-coso-internal-controls.html" class="nav-btn">Case Study 2 →</a></div>
