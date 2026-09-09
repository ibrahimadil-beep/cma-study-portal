# Case Study 3: Traditional vs. ABC Allocation

<div class="exam-container">
  <h3>📋 Exam Case Scenario</h3>
  <div style="background: #f6f8fa; padding: 18px; border-radius: 8px; border-left: 4px solid #0969da; line-height: 1.6;">
    A manufacturing plant produces 10,000 Standard Units and 1,000 Custom Units. Total setup overhead cost is $110,000. Under traditional volume costing, setup costs are allocated based on units produced. Production records show Standard Units require 2 machine setups, while Custom Units require 9 machine setups.
  </div>

  <h3 style="margin-top: 25px;">✍️ Required Tasks</h3>
  <ol style="line-height: 1.7; font-weight: 500;">
    <li>Calculate the setup cost per unit under the Traditional Volume Allocation method.</li><li>Calculate the setup cost per unit for both products under Activity-Based Costing (ABC).</li><li>Explain product cross-subsidization and why traditional costing distorts pricing decisions.</li>
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
    
<p><strong>1. Traditional Volume Allocation:</strong><br>
Rate = $\$110,000 / 11,000 	ext{ total units} = \mathbf{\$10.00 / 	ext{unit}}$ for both Standard and Custom.</p>
<p><strong>2. Activity-Based Costing (ABC):</strong><br>
Total setups = 11. Cost per setup = $\$110,000 / 11 = \mathbf{\$10,000 / 	ext{setup}}$.<br>
* Standard: $(2 	imes \$10,000) / 10,000 	ext{ units} = \mathbf{\$2.00 / 	ext{unit}}$.<br>
* Custom: $(9 	imes \$10,000) / 1,000 	ext{ units} = \mathbf{\$90.00 / 	ext{unit}}$.</p>
<p><strong>3. Cross-Subsidization Analysis:</strong><br>
Traditional costing drastically undercosts low-volume custom products ($10 vs $90) and overcosts high-volume standard products ($10 vs $2). This causes management to underprice complex custom goods and lose competitive bids on high-volume standard goods.</p>

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


<div class="nav-buttons"><a href="case-study-2-coso-internal-controls.html" class="nav-btn">← Case Study 2</a><a href="../README.html" class="nav-btn home">🏠 Home</a><a href="../diagrams/cost-classification-mindmap.html" class="nav-btn">Diagrams →</a></div>
