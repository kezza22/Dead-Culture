<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Dead Culture — Poetry & Short Story Contest</title>
<link rel="icon" href="data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 100 100%22><text y=%22.9em%22 font-size=%2290%22>&#9760;</text></svg>">
<link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@500;600&family=Inter:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --void: #0B0B0C;
    --ink: #E7E4DD;
    --ink-soft: #8C8880;
    --rule: #29282A;
    --blood: #8A1216;
    --blood-dim: #631014;
    box-sizing: border-box;
    padding-top: env(safe-area-inset-top, 0px);
    padding-bottom: env(safe-area-inset-bottom, 0px);
  }
  html { scroll-padding-top: env(safe-area-inset-top, 0px); height: 100%; }
  :root[data-theme="light"] {
    --void: #F1EFEA; --ink: #17151A; --ink-soft: #5C5852; --rule: #D7D2C8; --blood: #7A1014; --blood-dim: #9C2C30;
  }
  * { box-sizing: border-box; }
  html, body { height: 100%; }
  body {
    margin: 0;
    background: var(--void);
    color: var(--ink);
    font-family: 'Inter', sans-serif;
    line-height: 1.55;
    -webkit-font-smoothing: antialiased;
  }
  .wrap { max-width: 600px; margin: 0 auto; padding: 60px 24px 80px; }
  .masthead { text-align: center; margin-bottom: 44px; }
  .masthead .kicker {
    font-size: 11px; letter-spacing: 0.22em; color: var(--blood);
    margin: 0 0 14px; text-transform: uppercase;
  }
  .masthead h1 {
    font-family: 'Cinzel', serif;
    font-size: clamp(32px, 8vw, 46px);
    font-weight: 600;
    margin: 0;
    letter-spacing: 0.02em;
    text-transform: uppercase;
  }
  .masthead .tagline {
    color: var(--ink-soft);
    margin: 14px 0 0;
    font-size: 14px;
    letter-spacing: 0.04em;
  }
  hr { border: none; border-top: 1px solid var(--rule); margin: 36px 0; }
  .facts { display: grid; grid-template-columns: 1fr 1fr; gap: 22px 28px; }
  .facts div { border-top: 1px solid var(--rule); padding-top: 10px; }
  .facts .label { font-size: 11px; letter-spacing: 0.1em; color: var(--ink-soft); margin-bottom: 4px; text-transform: uppercase; }
  .facts .value { font-size: 16px; font-weight: 500; }
  .card { background: transparent; border: 1px solid var(--rule); padding: 28px 26px; margin-top: 32px; }
  .card h2 {
    font-family: 'Cinzel', serif; font-size: 17px; font-weight: 600;
    margin: 0 0 10px; letter-spacing: 0.04em; text-transform: uppercase;
  }
  .card p { color: var(--ink-soft); margin: 0 0 20px; font-size: 14.5px; }
  .btn {
    display: inline-block; width: 100%; text-align: center;
    background: var(--blood); color: #F1EFEA;
    font-weight: 600; font-size: 13px; letter-spacing: 0.08em; text-transform: uppercase;
    text-decoration: none; padding: 16px 20px; border: none; cursor: pointer;
    transition: background 0.15s ease;
  }
  .btn:hover { background: var(--blood-dim); }
  .btn:focus-visible { outline: 1px solid var(--blood); outline-offset: 3px; }
  .status {
    display: inline-flex; align-items: center; gap: 8px;
    font-size: 12px; letter-spacing: 0.08em; text-transform: uppercase;
    color: var(--ink-soft); margin-bottom: 18px;
  }
  .status .dot { width: 6px; height: 6px; background: var(--blood); }
  label { display: block; font-size: 12px; letter-spacing: 0.05em; color: var(--ink-soft); margin: 18px 0 6px; text-transform: uppercase; }
  input[type="text"] {
    width: 100%; font-family: 'Inter', sans-serif; font-size: 15px;
    padding: 12px 14px; border: 1px solid var(--rule); background: var(--void); color: var(--ink);
  }
  input[type="text"]:focus-visible { outline: 1px solid var(--blood); }
  .hint { font-size: 12px; color: var(--ink-soft); margin-top: 6px; }
  .stage { display: none; }
  .stage.active { display: block; }
  footer { text-align: center; margin-top: 48px; font-size: 12px; color: var(--ink-soft); }
  .setup-note {
    font-size: 12px; color: var(--ink-soft); background: color-mix(in srgb, var(--blood) 8%, transparent);
    border: 1px dashed var(--rule); padding: 14px 16px; margin-top: 40px;
  }
  .setup-note code { color: var(--blood); }
  .rules-list { margin: 0; padding-left: 20px; font-size: 14.5px; color: var(--ink); }
  .rules-list li { margin-bottom: 10px; }
  .rules-list li:last-child { margin-bottom: 0; }
  #rulesCard p { color: var(--ink-soft); font-size: 13px; }
</style>
</head>
<body>
<div class="wrap">

  <div class="masthead">
    <p class="kicker">Annual Contest</p>
    <h1>Dead Culture</h1>
    <p class="tagline">Poetry & short story competition</p>
  </div>

  <div class="facts">
    <div><div class="label">Entry Fee</div><div class="value" id="feeDisplay">£5</div></div>
    <div><div class="label">Deadline</div><div class="value" id="deadlineDisplay">31 October 2026</div></div>
    <div><div class="label">Categories</div><div class="value">Poetry · Short Fiction · Opinion Pieces</div></div>
    <div><div class="label">First Prize</div><div class="value" id="prizeDisplay">£100 + publication</div></div>
  </div>

  <hr>

  <div class="card" id="rulesCard">
    <h2>Rules</h2>
    <ol class="rules-list">
      <li>All contestants must be over the age of 18.</li>
      <li>Only submissions in English will be accepted.</li>
      <li>No AI-generated submissions. Work will be checked, and any AI-generated entries will be disqualified.</li>
      <li>Submissions must be your own original, previously unpublished work.</li>
      <li>Entries must not exceed 500 words.</li>
      <li>One entry per person per fee paid.</li>
      <li>Entry fees are non-refundable, including for disqualified entries.</li>
      <li>Late entries received after the deadline will not be considered.</li>
      <li>You retain copyright of your work. By entering, you grant the organiser one-time rights to publish your work on Instagram if it is shortlisted or wins.</li>
      <li>The judges' decision is final.</li>
    </ol>
    <p style="margin-top:16px">By paying the entry fee below, you confirm you have read and agree to these rules.</p>
    <p style="margin-top:10px"><a id="rulesLink" href="#" target="_blank" rel="noopener" style="color:var(--blood)">For our full list of rules and terms, click here</a></p>
  </div>

  <div class="stage" id="stagePay">
    <div class="card">
      <h2>Step 1 — Pay Entry Fee</h2>
      <p>Entry opens once payment is confirmed. You'll be sent to PayPal, then brought straight back here.</p>
      <a class="btn" id="payButton" href="#" target="_top">Pay Entry Fee with PayPal</a>
    </div>
  </div>

  <div class="stage" id="stageSubmit">
    <div class="status"><span class="dot"></span>Payment Received</div>
    <div class="card">
      <h2>Step 2 — Submit Your Work</h2>
      <p>One last thing before the submission form: enter the transaction ID from your PayPal receipt email, so your entry can be matched to your payment.</p>
      <label for="txnId">PayPal Transaction ID</label>
      <input type="text" id="txnId" placeholder="e.g. 9AB123456C789012D" autocomplete="off">
      <div class="hint">Found in the confirmation email PayPal just sent you.</div>
      <div style="margin-top:22px">
        <a class="btn" id="formButton" href="#" target="_blank" rel="noopener">Continue to Submission Form</a>
      </div>
    </div>
  </div>

  <div class="setup-note">
    <strong>Setup — replace before sharing:</strong><br>
    1. In your PayPal account, create a <em>Payment Link</em> for your entry fee, turn on <em>Auto Return</em>, and set the return URL to this page's published link with <code>?paid=1</code> added at the end.<br>
    2. Edit <code>CONFIG.paypalLink</code> and <code>CONFIG.googleFormUrl</code> below in the page code.<br>
    3. Update the fee, deadline and prize text above.
  </div>

  <footer>Questions about your entry? Message us on Instagram — @Dead_Culture_Press</footer>
</div>

<script>
  const CONFIG = {
    paypalLink: "https://www.paypal.com/ncp/payment/YOUR-LINK-ID",
    googleFormUrl: "https://forms.gle/YOUR-FORM-ID",
    fee: "£5",
    deadline: "31 October 2026",
    prize: "£100 + publication on Instagram",
    rulesUrl: "https://claude.ai/artifact/SA4WJUMjBi8cuCyU7URf7w"
  };

  document.getElementById('feeDisplay').textContent = CONFIG.fee;
  document.getElementById('deadlineDisplay').textContent = CONFIG.deadline;
  document.getElementById('prizeDisplay').textContent = CONFIG.prize;
  document.getElementById('rulesLink').href = CONFIG.rulesUrl;

  const payButton = document.getElementById('payButton');
  const formButton = document.getElementById('formButton');
  payButton.href = CONFIG.paypalLink;

  const params = new URLSearchParams(window.location.search);
  const paid = params.get('paid') === '1' || params.get('tx') || params.get('st') === 'Completed';

  const stagePay = document.getElementById('stagePay');
  const stageSubmit = document.getElementById('stageSubmit');

  if (paid) { stageSubmit.classList.add('active'); } else { stagePay.classList.add('active'); }

  const txnInput = document.getElementById('txnId');
  formButton.addEventListener('click', function (e) {
    const id = txnInput.value.trim();
    if (!id) {
      e.preventDefault();
      txnInput.focus();
      txnInput.style.borderColor = 'var(--blood)';
      return;
    }
    formButton.href = CONFIG.googleFormUrl;
  });
</script>
</body>
</html>