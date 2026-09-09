# Case Study 2: COSO Controls & Fraud Scenario

<div class="exam-container">
  <h3>📋 Exam Case Scenario</h3>
  <div style="background: #f6f8fa; padding: 18px; border-radius: 8px; border-left: 4px solid #0969da; line-height: 1.6;">
    At Apex Retail Inc., the Chief Executive Officer appointed her personal brother as chairman of the Audit Committee. Furthermore, a single senior cashier receives all cash and check payments, logs receipts into the customer subledger, and prepares the monthly bank reconciliation.
  </div>

  <h3 style="margin-top: 25px;">✍️ Required Tasks</h3>
  <ol style="line-height: 1.7; font-weight: 500;">
    <li>Identify corporate governance and internal control deficiencies under the COSO Framework and SOX.</li><li>Explain how the fundamental ARCR segregation of duties model is violated.</li><li>Draft three mandatory corrective actions the Board of Directors must take immediately.</li>
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
    
<p><strong>1. COSO & SOX Deficiencies:</strong><br>
* <strong>Tone at the Top / Control Environment:</strong> Compromised by familial nepotism.<br>
* <strong>SOX Section 407:</strong> Audit Committee members must be strictly independent. Having the CEO's brother as chair directly violates federal independence rules.</p>
<p><strong>2. ARCR Violations:</strong><br>
The cashier combines <strong>Custody</strong> (holding checks), <strong>Recordkeeping</strong> (posting ledger entries), and <strong>Reconciliation</strong> (preparing the bank reconciliation). This allows lapping and skimming frauds to go completely undetected.</p>
<p><strong>3. Mandatory Corrective Actions:</strong><br>
1. Remove the CEO's brother and appoint an independent financial expert to lead the Audit Committee.<br>
2. Reassign custody to a separate cashier and recordkeeping to the accounting department.<br>
3. Assign independent accounting staff or external auditors to perform monthly bank reconciliations.</p>

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


<div class="nav-buttons"><a href="case-study-1-variance-analysis.html" class="nav-btn">← Case Study 1</a><a href="../README.html" class="nav-btn home">🏠 Home</a><a href="case-study-3-cost-allocation-abc.html" class="nav-btn">Case Study 3 →</a></div>
