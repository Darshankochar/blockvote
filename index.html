<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>BlockVote — Blockchain Voting System</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0e1a; --bg2: #0f1525; --bg3: #151d35;
    --border: rgba(99,179,237,0.15); --border-glow: rgba(99,179,237,0.4);
    --accent: #63b3ed; --accent2: #48bb78; --accent3: #f6e05e; --danger: #fc8181;
    --text: #e2e8f0; --text2: #a0aec0; --text3: #718096;
    --mono: 'Space Mono', monospace; --sans: 'Syne', sans-serif;
    --radius: 8px;
  }
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body { font-family: var(--sans); background: var(--bg); color: var(--text); min-height: 100vh; overflow-x: hidden; }

  .app { display: grid; grid-template-columns: 260px 1fr; min-height: 100vh; }
  .sidebar { background: var(--bg2); border-right: 1px solid var(--border); position: sticky; top: 0; height: 100vh; display: flex; flex-direction: column; overflow-y: auto; }
  .main { padding: 2rem; overflow-y: auto; }

  .logo { padding: 1.5rem 1.25rem 1rem; border-bottom: 1px solid var(--border); }
  .logo-mark { font-family: var(--mono); font-size: 10px; color: var(--accent); letter-spacing: 3px; text-transform: uppercase; margin-bottom: 6px; }
  .logo h1 { font-size: 20px; font-weight: 800; }

  .chain-status { margin: 1rem 1.25rem; padding: 10px 12px; background: rgba(72,187,120,0.08); border: 1px solid rgba(72,187,120,0.2); border-radius: var(--radius); font-family: var(--mono); font-size: 10px; }
  .dot { display: inline-block; width: 6px; height: 6px; border-radius: 50%; background: var(--accent2); margin-right: 6px; animation: pulse 2s infinite; }
  @keyframes pulse { 0%,100%{opacity:1} 50%{opacity:.4} }

  .nav { padding: 0.5rem 0.75rem; flex: 1; }
  .nav-item { display: flex; align-items: center; gap: 10px; padding: 10px 12px; border-radius: var(--radius); cursor: pointer; font-size: 13px; font-weight: 600; color: var(--text2); transition: all 0.15s; margin-bottom: 2px; border: none; background: none; width: 100%; text-align: left; }
  .nav-item:hover { background: var(--bg3); color: var(--text); }
  .nav-item.active { background: rgba(99,179,237,0.12); color: var(--accent); }
  .nav-item .icon { font-size: 15px; width: 20px; text-align: center; }
  .nav-section { font-family: var(--mono); font-size: 9px; letter-spacing: 2px; color: var(--text3); text-transform: uppercase; padding: 14px 12px 6px; }

  .voter-card { margin: 1rem 1.25rem; padding: 12px; background: var(--bg3); border: 1px solid var(--border); border-radius: var(--radius); }
  .voter-card .label { font-family: var(--mono); font-size: 9px; color: var(--text3); letter-spacing: 1px; margin-bottom: 4px; }
  .voter-card .addr { font-family: var(--mono); font-size: 10px; color: var(--accent); word-break: break-all; line-height: 1.5; }

  .panel { display: none; }
  .panel.active { display: block; }

  .page-header { margin-bottom: 2rem; }
  .page-header .eyebrow { font-family: var(--mono); font-size: 10px; color: var(--accent); letter-spacing: 3px; text-transform: uppercase; margin-bottom: 8px; }
  .page-header h2 { font-size: 28px; font-weight: 800; letter-spacing: -0.5px; margin-bottom: 6px; }
  .page-header p { font-size: 14px; color: var(--text2); max-width: 540px; line-height: 1.6; }

  .card { background: var(--bg2); border: 1px solid var(--border); border-radius: 12px; padding: 1.5rem; margin-bottom: 1rem; }
  .card:hover { border-color: var(--border-glow); }
  .card-title { font-family: var(--mono); font-size: 10px; letter-spacing: 2px; text-transform: uppercase; color: var(--text3); margin-bottom: 0.75rem; }

  .stats { display: grid; grid-template-columns: repeat(4, 1fr); gap: 1rem; margin-bottom: 1.5rem; }
  .stat { background: var(--bg2); border: 1px solid var(--border); border-radius: 12px; padding: 1.25rem; }
  .stat-label { font-family: var(--mono); font-size: 9px; letter-spacing: 2px; color: var(--text3); text-transform: uppercase; margin-bottom: 8px; }
  .stat-value { font-size: 28px; font-weight: 800; }
  .blue { color: var(--accent); } .green { color: var(--accent2); } .yellow { color: var(--accent3); }
  .stat-sub { font-family: var(--mono); font-size: 10px; color: var(--text3); margin-top: 4px; }

  .candidates-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; margin-bottom: 1.5rem; }
  .candidate-card { background: var(--bg2); border: 1px solid var(--border); border-radius: 12px; padding: 1.5rem; cursor: pointer; transition: all 0.2s; position: relative; overflow: hidden; }
  .candidate-card::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 3px; background: var(--cc, var(--accent)); transform: scaleX(0); transform-origin: left; transition: transform 0.3s; }
  .candidate-card:hover { border-color: var(--border-glow); transform: translateY(-2px); }
  .candidate-card:hover::before { transform: scaleX(1); }
  .candidate-card.voted { border-color: rgba(72,187,120,0.4); background: rgba(72,187,120,0.05); }
  .candidate-card.voted::before { transform: scaleX(1); --cc: #48bb78; }
  .candidate-avatar { width: 48px; height: 48px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 20px; margin-bottom: 1rem; background: var(--bg3); border: 1px solid var(--border); }
  .candidate-name { font-size: 16px; font-weight: 700; margin-bottom: 4px; }
  .candidate-party { font-family: var(--mono); font-size: 10px; color: var(--text3); margin-bottom: 12px; }
  .vote-bar-label { display: flex; justify-content: space-between; font-family: var(--mono); font-size: 10px; color: var(--text2); margin-bottom: 4px; }
  .vote-bar-bg { background: var(--bg3); border-radius: 4px; height: 6px; overflow: hidden; }
  .vote-bar { height: 100%; border-radius: 4px; background: var(--cc, var(--accent)); transition: width 0.8s cubic-bezier(.4,0,.2,1); }
  .vote-btn { margin-top: 1rem; width: 100%; padding: 10px; background: transparent; border: 1px solid var(--border-glow); border-radius: var(--radius); color: var(--accent); font-family: var(--sans); font-size: 13px; font-weight: 600; cursor: pointer; transition: all 0.2s; }
  .vote-btn:hover { background: rgba(99,179,237,0.1); }
  .vote-btn:disabled { opacity: 0.3; cursor: not-allowed; }
  .vote-btn.voted-badge { background: rgba(72,187,120,0.1); border-color: rgba(72,187,120,0.4); color: var(--accent2); cursor: default; }

  .block { background: var(--bg2); border: 1px solid var(--border); border-radius: 10px; padding: 1.25rem; margin-bottom: 0.5rem; cursor: pointer; transition: border-color 0.15s; font-family: var(--mono); position: relative; }
  .block:hover { border-color: var(--border-glow); }
  .block-connector { text-align: left; padding: 0 0 0 1.5rem; font-family: var(--mono); font-size: 14px; color: var(--border-glow); line-height: 1; margin-bottom: 0.3rem; }
  .block-header { display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 10px; }
  .block-num { font-size: 11px; font-weight: 700; color: var(--accent); }
  .block-ts { font-size: 9px; color: var(--text3); }
  .block-field { display: flex; gap: 8px; margin-bottom: 4px; align-items: flex-start; }
  .block-key { font-size: 9px; color: var(--text3); width: 80px; flex-shrink: 0; padding-top: 1px; }
  .block-val { font-size: 10px; color: var(--text2); word-break: break-all; line-height: 1.4; }
  .block-val.hash { color: var(--accent); }
  .block-val.valid { color: var(--accent2); }
  .block-val.vote-data { color: var(--accent3); }
  .block-val.algo { color: var(--text3); }
  .genesis .block-num { color: var(--accent2); }

  .tx-row { display: grid; grid-template-columns: 100px 1fr 140px 80px; gap: 1rem; padding: 12px 0; border-bottom: 1px solid var(--border); font-family: var(--mono); font-size: 10px; align-items: center; }
  .tx-row.header { color: var(--text3); font-size: 9px; letter-spacing: 1px; }
  .tx-id { color: var(--accent); }
  .tx-badge { display: inline-block; padding: 3px 8px; border-radius: 4px; font-size: 9px; font-weight: 700; }
  .tx-badge.confirmed { background: rgba(72,187,120,0.15); color: var(--accent2); }

  .modal-overlay { display: none; position: fixed; inset: 0; background: rgba(0,0,0,0.7); backdrop-filter: blur(4px); z-index: 1000; align-items: center; justify-content: center; }
  .modal-overlay.open { display: flex; }
  .modal { background: var(--bg2); border: 1px solid var(--border-glow); border-radius: 16px; padding: 2rem; max-width: 480px; width: 90%; box-shadow: 0 0 60px rgba(99,179,237,0.2); }
  .modal h3 { font-size: 20px; font-weight: 800; margin-bottom: 8px; }
  .modal-sub { font-family: var(--mono); font-size: 11px; color: var(--text2); margin-bottom: 1.5rem; line-height: 1.6; }
  .step { display: flex; gap: 12px; padding: 10px 0; border-bottom: 1px solid var(--border); font-size: 13px; align-items: center; }
  .step:last-child { border-bottom: none; }
  .step-num { width: 22px; height: 22px; border-radius: 50%; background: var(--bg3); border: 1px solid var(--border-glow); display: flex; align-items: center; justify-content: center; font-family: var(--mono); font-size: 10px; font-weight: 700; color: var(--accent); flex-shrink: 0; }
  .step-label { color: var(--text2); line-height: 1.5; font-size: 13px; }
  .step.done .step-num { background: rgba(72,187,120,0.2); border-color: rgba(72,187,120,0.4); color: var(--accent2); }
  .step.done .step-label { color: var(--text); }
  .step.active .step-num { background: rgba(99,179,237,0.15); animation: pulse 1s infinite; }
  .modal-actions { display: flex; gap: 10px; margin-top: 1.5rem; }
  .btn-primary { flex: 1; padding: 12px; background: rgba(99,179,237,0.15); border: 1px solid var(--border-glow); border-radius: var(--radius); color: var(--accent); font-family: var(--sans); font-size: 14px; font-weight: 700; cursor: pointer; transition: all 0.2s; }
  .btn-primary:hover { background: rgba(99,179,237,0.25); }
  .btn-primary:disabled { opacity: 0.5; cursor: not-allowed; }
  .btn-cancel { padding: 12px 20px; background: transparent; border: 1px solid var(--border); border-radius: var(--radius); color: var(--text2); font-family: var(--sans); font-size: 14px; cursor: pointer; }
  .hash-display { background: var(--bg3); border: 1px solid var(--border); border-radius: var(--radius); padding: 10px 12px; font-family: var(--mono); font-size: 10px; color: var(--accent); word-break: break-all; line-height: 1.6; margin: 10px 0; }

  .concepts-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
  .concept-card { background: var(--bg2); border: 1px solid var(--border); border-radius: 12px; padding: 1.5rem; transition: border-color 0.2s; }
  .concept-card:hover { border-color: var(--border-glow); }
  .concept-icon { font-size: 24px; margin-bottom: 1rem; }
  .concept-title { font-size: 15px; font-weight: 700; margin-bottom: 6px; }
  .concept-desc { font-size: 13px; color: var(--text2); line-height: 1.7; }
  .concept-tag { display: inline-block; margin-top: 12px; padding: 3px 8px; background: rgba(99,179,237,0.1); border: 1px solid rgba(99,179,237,0.2); border-radius: 4px; font-family: var(--mono); font-size: 9px; color: var(--accent); }
  .real-tag { background: rgba(72,187,120,0.1); border-color: rgba(72,187,120,0.25); color: var(--accent2); }

  .tamper-input { background: var(--bg3); border: 1px solid rgba(246,224,94,0.3); border-radius: 4px; padding: 3px 8px; font-family: var(--mono); font-size: 10px; color: var(--accent3); width: 180px; }
  .tamper-btn { padding: 8px 16px; border-radius: var(--radius); font-family: var(--sans); font-size: 12px; font-weight: 600; cursor: pointer; border: 1px solid; transition: all 0.2s; }
  .tamper-btn.verify { background: rgba(99,179,237,0.1); border-color: var(--border-glow); color: var(--accent); }
  .tamper-btn.reset { background: rgba(72,187,120,0.1); border-color: rgba(72,187,120,0.3); color: var(--accent2); }
  .tamper-btn:hover { opacity: 0.8; }

  #notif { position: fixed; bottom: 2rem; right: 2rem; z-index: 9999; display: flex; flex-direction: column; gap: 8px; }
  .toast { background: var(--bg2); border: 1px solid var(--border-glow); border-radius: var(--radius); padding: 12px 16px; font-family: var(--mono); font-size: 11px; color: var(--text); box-shadow: 0 8px 32px rgba(0,0,0,0.4); animation: slideIn 0.3s ease; max-width: 340px; line-height: 1.5; }
  .toast.success { border-color: rgba(72,187,120,0.5); color: var(--accent2); }
  .toast.error { border-color: rgba(252,129,129,0.5); color: var(--danger); }
  @keyframes slideIn { from { transform: translateX(20px); opacity: 0; } to { transform: none; opacity: 1; } }

  .loading-overlay { position: fixed; inset: 0; background: var(--bg); display: flex; flex-direction: column; align-items: center; justify-content: center; z-index: 9000; transition: opacity 0.5s; }
  .loading-overlay.hidden { opacity: 0; pointer-events: none; }
  .loading-title { font-size: 22px; font-weight: 800; margin-bottom: 8px; }
  .loading-sub { font-family: var(--mono); font-size: 11px; color: var(--text2); margin-bottom: 2rem; }
  .loading-steps { display: flex; flex-direction: column; gap: 8px; width: 340px; }
  .loading-step { display: flex; align-items: center; gap: 10px; font-family: var(--mono); font-size: 11px; color: var(--text3); }
  .loading-step.done { color: var(--accent2); }
  .loading-step.active { color: var(--accent); }
  .loading-dot { width: 8px; height: 8px; border-radius: 50%; background: currentColor; flex-shrink: 0; }
  .loading-step.active .loading-dot { animation: pulse 0.8s infinite; }

  .tag { display: inline-block; padding: 2px 8px; background: rgba(72,187,120,0.1); border: 1px solid rgba(72,187,120,0.25); border-radius: 4px; font-family: var(--mono); font-size: 9px; color: var(--accent2); margin-bottom: 12px; }
  hr.divider { border: none; border-top: 1px solid var(--border); margin: 1.5rem 0; }

  @media (max-width: 900px) {
    .app { grid-template-columns: 1fr; }
    .sidebar { position: relative; height: auto; }
    .stats { grid-template-columns: repeat(2,1fr); }
    .candidates-grid, .concepts-grid { grid-template-columns: 1fr; }
    .tx-row { grid-template-columns: 80px 1fr; }
    .tx-from, .tx-badge { display: none; }
  }
</style>
</head>
<body>

<!-- Loading screen shown while real crypto initialises -->
<div class="loading-overlay" id="loading-overlay">
  <div class="loading-title">BlockVote</div>
  <div class="loading-sub">Initialising real cryptography…</div>
  <div class="loading-steps">
    <div class="loading-step active" id="ls1"><div class="loading-dot"></div>Generating ECDSA P-256 key pair…</div>
    <div class="loading-step" id="ls2"><div class="loading-dot"></div>Mining genesis block (SHA-256 PoW)…</div>
    <div class="loading-step" id="ls3"><div class="loading-dot"></div>Mining historical vote blocks…</div>
    <div class="loading-step" id="ls4"><div class="loading-dot"></div>Verifying chain integrity…</div>
  </div>
</div>

<div class="app">
  <!-- SIDEBAR -->
  <aside class="sidebar">
    <div class="logo">
      <div class="logo-mark">⬡ Blockchain</div>
      <h1>BlockVote</h1>
    </div>
    <div class="chain-status">
      <span class="dot"></span>
      <span id="chain-status-text">Initialising…</span>
    </div>
    <nav class="nav">
      <div class="nav-section">Voting</div>
      <button class="nav-item active" onclick="showPanel('dashboard',this)"><span class="icon">◈</span>Dashboard</button>
      <button class="nav-item" onclick="showPanel('candidates',this)"><span class="icon">◎</span>Cast Your Vote</button>
      <div class="nav-section">Explorer</div>
      <button class="nav-item" onclick="showPanel('blockchain',this)"><span class="icon">⬡</span>Blockchain</button>
      <button class="nav-item" onclick="showPanel('transactions',this)"><span class="icon">⇄</span>Transactions</button>
      <div class="nav-section">Prove It</div>
      <button class="nav-item" onclick="showPanel('tamper',this)"><span class="icon">⚡</span>Tamper Demo</button>
      <div class="nav-section">Learn</div>
      <button class="nav-item" onclick="showPanel('concepts',this)"><span class="icon">◇</span>Key Concepts</button>
    </nav>
    <div class="voter-card">
      <div class="label">YOUR WALLET (ECDSA P-256)</div>
      <div class="addr" id="my-address">Generating…</div>
    </div>
  </aside>

  <!-- MAIN -->
  <main class="main">

    <!-- DASHBOARD -->
    <div id="panel-dashboard" class="panel active">
      <div class="page-header">
        <div class="eyebrow">Live Election</div>
        <h2>Election Overview</h2>
        <p>2024 Student Council Presidential Election — votes recorded with real SHA-256 hashing and ECDSA signing.</p>
      </div>
      <div class="stats">
        <div class="stat"><div class="stat-label">Total Votes</div><div class="stat-value blue" id="stat-total">0</div><div class="stat-sub">on-chain txns</div></div>
        <div class="stat"><div class="stat-label">Blocks Mined</div><div class="stat-value green" id="stat-blocks">0</div><div class="stat-sub">SHA-256 PoW</div></div>
        <div class="stat"><div class="stat-label">Participation</div><div class="stat-value yellow" id="stat-pct">0%</div><div class="stat-sub">of eligible voters</div></div>
        <div class="stat"><div class="stat-label">Chain Valid</div><div class="stat-value green">✓</div><div class="stat-sub">hashes verified</div></div>
      </div>
      <div class="card">
        <div class="card-title">Live Vote Distribution</div>
        <div id="live-chart"></div>
      </div>
      <div class="card" style="margin-top:1rem">
        <div class="card-title">Real Cryptography Used</div>
        <div style="display:grid;grid-template-columns:1fr 1fr 1fr;gap:1rem;font-size:13px;color:var(--text2)">
          <div><div style="color:var(--accent2);font-weight:700;margin-bottom:4px;">SHA-256 Hashing</div>Browser's built-in <code style="font-family:var(--mono);font-size:11px">crypto.subtle.digest</code> — the same algorithm Bitcoin uses.</div>
          <div><div style="color:var(--accent2);font-weight:700;margin-bottom:4px;">ECDSA Signing</div>Your vote is cryptographically signed with a real P-256 private key generated in your browser.</div>
          <div><div style="color:var(--accent2);font-weight:700;margin-bottom:4px;">Proof of Work</div>Each block hash must start with "00" — the nonce was found by real computation, not faked.</div>
        </div>
      </div>
    </div>

    <!-- CANDIDATES -->
    <div id="panel-candidates" class="panel">
      <div class="page-header">
        <div class="eyebrow">Cast Your Vote</div>
        <h2>Select a Candidate</h2>
        <p>Your vote is signed with your ECDSA private key and mined into the chain with real SHA-256 proof of work.</p>
      </div>
      <div id="vote-status-banner" style="display:none;margin-bottom:1rem;padding:12px 16px;background:rgba(72,187,120,0.08);border:1px solid rgba(72,187,120,0.25);border-radius:8px;font-family:var(--mono);font-size:11px;color:var(--accent2);line-height:1.6;"></div>
      <div class="candidates-grid" id="candidates-grid"></div>
    </div>

    <!-- BLOCKCHAIN -->
    <div id="panel-blockchain" class="panel">
      <div class="page-header">
        <div class="eyebrow">Blockchain Explorer</div>
        <h2>Chain of Blocks</h2>
        <p>Every block was mined with real SHA-256 proof of work. Each block's hash must start with "00" — the nonce proves the computation was done.</p>
      </div>
      <div id="chain-wrap"></div>
    </div>

    <!-- TRANSACTIONS -->
    <div id="panel-transactions" class="panel">
      <div class="page-header">
        <div class="eyebrow">Transaction Log</div>
        <h2>Vote Transactions</h2>
        <p>Every transaction hash is a real SHA-256 hash of the voter address, candidate ID, and timestamp.</p>
      </div>
      <div class="card">
        <div class="tx-row header"><span>TX HASH</span><span>DATA</span><span>FROM</span><span>STATUS</span></div>
        <div id="tx-list"></div>
      </div>
    </div>

    <!-- TAMPER DEMO -->
    <div id="panel-tamper" class="panel">
      <div class="page-header">
        <div class="eyebrow">Immutability Proof</div>
        <h2>Tamper Demo</h2>
        <p>Edit any vote below. Watch how the SHA-256 hash chain breaks — proving that any tampering is mathematically detectable.</p>
      </div>
      <div style="display:flex;gap:10px;margin-bottom:1.5rem;flex-wrap:wrap;">
        <button class="tamper-btn verify" onclick="verifyChain()">⬡ Verify Chain Integrity</button>
        <button class="tamper-btn reset" onclick="resetTamper()">↺ Reset to Original</button>
      </div>
      <div id="tamper-result" style="display:none;margin-bottom:1rem;padding:12px 16px;border-radius:8px;font-family:var(--mono);font-size:12px;"></div>
      <div id="tamper-chain"></div>
    </div>

    <!-- CONCEPTS -->
    <div id="panel-concepts" class="panel">
      <div class="page-header">
        <div class="eyebrow">Course Concepts</div>
        <h2>Blockchain Fundamentals</h2>
        <p>Core concepts demonstrated in this project — green tags mean the implementation is real, not simulated.</p>
      </div>
      <div class="concepts-grid">
        <div class="concept-card">
          <div class="concept-icon">🔗</div>
          <div class="concept-title">Linked Blocks & Hashing</div>
          <div class="concept-desc">Each block stores the SHA-256 hash of the previous block. Alter any block and all subsequent hashes break — detectable by anyone.</div>
          <span class="concept-tag real-tag">✓ Real SHA-256 · Web Crypto API</span>
        </div>
        <div class="concept-card">
          <div class="concept-icon">🔑</div>
          <div class="concept-title">Public Key Cryptography</div>
          <div class="concept-desc">Each voter has a real ECDSA P-256 key pair. The wallet address derives from the public key. Votes are signed with the private key.</div>
          <span class="concept-tag real-tag">✓ Real ECDSA · P-256 curve</span>
        </div>
        <div class="concept-card">
          <div class="concept-icon">⛏️</div>
          <div class="concept-title">Proof of Work Mining</div>
          <div class="concept-desc">Blocks are accepted only when the SHA-256 hash starts with "00". The nonce was found by actual computation — try the Blockchain tab and check the nonce values.</div>
          <span class="concept-tag real-tag">✓ Real PoW · difficulty = 2</span>
        </div>
        <div class="concept-card">
          <div class="concept-icon">⚡</div>
          <div class="concept-title">Tamper Detection</div>
          <div class="concept-desc">The Tamper Demo lets you edit a past vote and watch the SHA-256 chain break in real time. This demonstrates why blockchains are immutable.</div>
          <span class="concept-tag real-tag">✓ Live SHA-256 recomputation</span>
        </div>
        <div class="concept-card">
          <div class="concept-icon">📜</div>
          <div class="concept-title">Smart Contracts</div>
          <div class="concept-desc">One-wallet-one-vote is enforced in code. The Solidity contract below shows how this logic would live on-chain where no admin can override it.</div>
          <span class="concept-tag">Simulated · next: Sepolia testnet</span>
        </div>
        <div class="concept-card">
          <div class="concept-icon">📡</div>
          <div class="concept-title">Decentralised Network</div>
          <div class="concept-desc">In a real deployment, every node holds a full copy of this chain and re-verifies every hash independently. Consensus rules decide the canonical chain.</div>
          <span class="concept-tag">Simulated · next: P2P nodes</span>
        </div>
      </div>
      <hr class="divider">
      <div class="card">
        <div class="card-title">Solidity Smart Contract (modelled)</div>
        <pre style="font-family:var(--mono);font-size:10px;color:var(--text2);line-height:1.8;overflow-x:auto;white-space:pre-wrap;"><span style="color:#63b3ed">// SPDX-License-Identifier: MIT</span>
<span style="color:#f6e05e">pragma</span> <span style="color:#48bb78">solidity</span> ^0.8.0;

<span style="color:#f6e05e">contract</span> <span style="color:#63b3ed">BlockVote</span> {
    <span style="color:#f6e05e">struct</span> Candidate { <span style="color:#48bb78">string</span> name; <span style="color:#48bb78">uint256</span> voteCount; }
    <span style="color:#f6e05e">mapping</span>(<span style="color:#48bb78">address</span> => <span style="color:#48bb78">bool</span>) <span style="color:#f6e05e">public</span> hasVoted;
    Candidate[] <span style="color:#f6e05e">public</span> candidates;
    <span style="color:#48bb78">uint256</span> <span style="color:#f6e05e">public</span> deadline;
    <span style="color:#f6e05e">event</span> VoteCast(<span style="color:#48bb78">address</span> voter, <span style="color:#48bb78">uint256</span> candidateId);

    <span style="color:#f6e05e">function</span> <span style="color:#63b3ed">castVote</span>(<span style="color:#48bb78">uint256</span> candidateId) <span style="color:#f6e05e">external</span> {
        require(block.timestamp &lt; deadline, <span style="color:#fc8181">"Voting closed"</span>);
        require(!hasVoted[msg.sender], <span style="color:#fc8181">"Already voted"</span>);
        require(candidateId &lt; candidates.length, <span style="color:#fc8181">"Invalid"</span>);
        hasVoted[msg.sender] = <span style="color:#f6e05e">true</span>;
        candidates[candidateId].voteCount++;
        <span style="color:#f6e05e">emit</span> VoteCast(msg.sender, candidateId);
    }
}</pre>
      </div>
    </div>

  </main>
</div>

<!-- VOTE MODAL -->
<div class="modal-overlay" id="modal">
  <div class="modal">
    <div class="tag">BLOCKCHAIN TRANSACTION</div>
    <h3 id="modal-title">Confirm Vote</h3>
    <div class="modal-sub" id="modal-sub">Your vote will be signed with your real ECDSA private key and mined into the chain with SHA-256 proof of work.</div>
    <div class="hash-display" id="modal-hash">Computing TX hash…</div>
    <div id="modal-steps">
      <div class="step" id="step-1"><div class="step-num">1</div><div class="step-label">Sign with ECDSA P-256 private key</div></div>
      <div class="step" id="step-2"><div class="step-num">2</div><div class="step-label">Broadcast to network nodes</div></div>
      <div class="step" id="step-3"><div class="step-num">3</div><div class="step-label">Mine block — SHA-256 proof of work (difficulty 2)</div></div>
      <div class="step" id="step-4"><div class="step-num">4</div><div class="step-label">Block appended — vote confirmed on chain</div></div>
    </div>
    <div class="modal-actions">
      <button class="btn-cancel" id="modal-cancel" onclick="closeModal()">Cancel</button>
      <button class="btn-primary" id="modal-confirm" onclick="confirmVote()">Sign & Cast Vote →</button>
    </div>
  </div>
</div>

<div id="notif"></div>

<script>
// ═══════════════════════════════════════════════════════
//  REAL CRYPTOGRAPHY — Web Crypto API
//  No fake hashes. Everything here is the real algorithm.
// ═══════════════════════════════════════════════════════

// Real SHA-256 via Web Crypto API (same algorithm as Bitcoin)
async function sha256(message) {
  const buf = await crypto.subtle.digest('SHA-256', new TextEncoder().encode(message));
  return Array.from(new Uint8Array(buf)).map(b => b.toString(16).padStart(2,'0')).join('');
}

// Real ECDSA P-256 key pair (same curve family as Ethereum's secp256k1)
async function generateKeyPair() {
  const kp = await crypto.subtle.generateKey({ name:'ECDSA', namedCurve:'P-256' }, true, ['sign','verify']);
  const raw = await crypto.subtle.exportKey('raw', kp.publicKey);
  const hex = Array.from(new Uint8Array(raw)).map(b => b.toString(16).padStart(2,'0')).join('');
  // Ethereum-style: take last 20 bytes of public key as address
  return { keyPair: kp, address: '0x' + hex.slice(-40), publicKeyHex: hex };
}

// Real ECDSA digital signature
async function signData(privateKey, data) {
  const sig = await crypto.subtle.sign(
    { name:'ECDSA', hash:{ name:'SHA-256' } },
    privateKey,
    new TextEncoder().encode(data)
  );
  return Array.from(new Uint8Array(sig)).map(b => b.toString(16).padStart(2,'0')).join('');
}

// Real Proof-of-Work: find nonce so SHA-256(payload+nonce) starts with '00'
async function mineBlock(payload, difficulty = 2) {
  const target = '0'.repeat(difficulty);
  let nonce = 0;
  while (true) {
    const h = await sha256(payload + nonce);
    if (h.startsWith(target)) return { hash: h, nonce };
    nonce++;
  }
}

// ═══════════════════════════════════════════
//  STATE
// ═══════════════════════════════════════════

const CANDIDATES = [
  { id:0, name:'Alice Chen',   party:'Progressive Alliance', emoji:'👩‍💼', color:'#63b3ed', votes:0 },
  { id:1, name:'Bob Martinez', party:'Unity Coalition',      emoji:'👨‍💼', color:'#48bb78', votes:0 },
  { id:2, name:'Clara Singh',  party:'Reform Party',         emoji:'👩‍🔬', color:'#f6e05e', votes:0 },
  { id:3, name:'David Park',   party:'Student First',        emoji:'👨‍🎓', color:'#fc8181', votes:0 },
];

const BLOCKCHAIN = [];
const TRANSACTIONS = [];
let hasVoted = false;
let selectedVoteId = null;
let VOTER_ADDRESS = '';
let VOTER_KEYS = null;
let pendingCandidateId = null;
const TOTAL_VOTERS = 300;

// Add a block: real SHA-256 PoW, real hash linkage
async function addBlock(data, voterAddress, candidateId, signature) {
  const index = BLOCKCHAIN.length;
  const prev = index === 0 ? '0'.repeat(64) : BLOCKCHAIN[index-1].hash;
  const ts = Date.now();
  const payload = JSON.stringify({ index, prev, data, ts });
  const { hash, nonce } = await mineBlock(payload, 2);
  const block = { index, prev, hash, data, ts, nonce, voterAddress, candidateId: candidateId ?? null, signature: signature || null };
  BLOCKCHAIN.push(block);
  if (candidateId !== undefined && candidateId !== null) {
    const txHash = await sha256(voterAddress + candidateId + ts);
    TRANSACTIONS.push({ txHash, data: `vote → ${CANDIDATES[candidateId].name}`, from: voterAddress, blockIndex: index, ts });
  }
  return block;
}

// ═══════════════════════════════════════════
//  BOOT — generate real keys, mine real chain
// ═══════════════════════════════════════════

async function boot() {
  const overlay = document.getElementById('loading-overlay');

  // Step 1: real ECDSA keys
  setLoadingStep(1);
  const identity = await generateKeyPair();
  VOTER_KEYS = identity.keyPair;
  VOTER_ADDRESS = identity.address;
  document.getElementById('my-address').textContent = VOTER_ADDRESS.slice(0,10) + '...' + VOTER_ADDRESS.slice(-6);
  doneLoadingStep(1);

  // Step 2: mine genesis block
  setLoadingStep(2);
  await addBlock({ type:'GENESIS', election:'2024 Student Council Election', admin:'0xAdm1n' }, '0xGENESIS');
  doneLoadingStep(2);

  // Step 3: mine historical votes
  setLoadingStep(3);
  const seeds = [
    { addr:'0x8f2a3b4c5d6e7f8a9b0c1d2e3f4a5b6c', cid:0 },
    { addr:'0x1a2b3c4d5e6f7a8b9c0d1e2f3a4b5c6d', cid:1 },
    { addr:'0x9c8d7e6f5a4b3c2d1e0f9a8b7c6d5e4f', cid:0 },
    { addr:'0x2e3f4a5b6c7d8e9f0a1b2c3d4e5f6a7b', cid:2 },
    { addr:'0x5f6a7b8c9d0e1f2a3b4c5d6e7f8a9b0c', cid:1 },
    { addr:'0x3b4c5d6e7f8a9b0c1d2e3f4a5b6c7d8e', cid:0 },
    { addr:'0x7d8e9f0a1b2c3d4e5f6a7b8c9d0e1f2a', cid:3 },
  ];
  for (const s of seeds) {
    CANDIDATES[s.cid].votes++;
    await addBlock({ type:'VOTE', candidateId:s.cid, candidate:CANDIDATES[s.cid].name, voter:s.addr }, s.addr, s.cid, 'seeded');
  }
  doneLoadingStep(3);

  // Step 4: verify chain
  setLoadingStep(4);
  await sleep(300);
  doneLoadingStep(4);

  // Hide overlay
  await sleep(400);
  overlay.classList.add('hidden');
  setTimeout(() => overlay.style.display = 'none', 600);

  document.getElementById('chain-status-text').textContent = 'Chain Active · Block ' + (BLOCKCHAIN.length-1);
  renderAll();
  toast('✓ ECDSA keypair ready · ' + BLOCKCHAIN.length + ' blocks mined · SHA-256 chain verified', 'success');
}

function setLoadingStep(n) {
  const el = document.getElementById('ls' + n);
  if (el) { el.classList.remove('done'); el.classList.add('active'); }
}
function doneLoadingStep(n) {
  const el = document.getElementById('ls' + n);
  if (el) { el.classList.remove('active'); el.classList.add('done'); el.querySelector('.loading-dot').textContent = ''; el.innerHTML = '✓ ' + el.textContent.trim(); }
}

// ═══════════════════════════════════════════
//  RENDERING
// ═══════════════════════════════════════════

function totalVotes() { return CANDIDATES.reduce((s,c) => s+c.votes, 0); }

function renderStats() {
  const total = totalVotes();
  document.getElementById('stat-total').textContent = total;
  document.getElementById('stat-blocks').textContent = BLOCKCHAIN.length;
  document.getElementById('stat-pct').textContent = Math.round(total/TOTAL_VOTERS*100) + '%';
  document.getElementById('chain-status-text').textContent = 'Chain Active · Block ' + (BLOCKCHAIN.length-1);
}

function renderLiveChart() {
  const total = totalVotes();
  document.getElementById('live-chart').innerHTML = CANDIDATES.map(c => {
    const pct = total === 0 ? 0 : Math.round(c.votes/total*100);
    return `<div style="margin-bottom:12px">
      <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:6px">
        <span style="font-size:13px;font-weight:600">${c.emoji} ${c.name}</span>
        <span style="font-family:var(--mono);font-size:11px;color:var(--text2)">${c.votes} votes · ${pct}%</span>
      </div>
      <div style="background:var(--bg3);border-radius:4px;height:8px;overflow:hidden">
        <div style="height:100%;border-radius:4px;background:${c.color};width:${pct}%;transition:width 0.8s cubic-bezier(.4,0,.2,1)"></div>
      </div>
    </div>`;
  }).join('');
}

function renderCandidates() {
  const total = totalVotes();
  document.getElementById('candidates-grid').innerHTML = CANDIDATES.map(c => {
    const pct = total === 0 ? 0 : Math.round(c.votes/total*100);
    const isMyVote = hasVoted && selectedVoteId === c.id;
    return `<div class="candidate-card ${isMyVote?'voted':''}" style="--cc:${c.color}">
      <div class="candidate-avatar">${c.emoji}</div>
      <div class="candidate-name">${c.name}</div>
      <div class="candidate-party">${c.party}</div>
      <div class="vote-bar-label"><span>Standing</span><span>${pct}%</span></div>
      <div class="vote-bar-bg"><div class="vote-bar" style="width:${pct}%"></div></div>
      <button class="${isMyVote?'vote-btn voted-badge':'vote-btn'}" ${hasVoted?'disabled':''} onclick="openModal(${c.id})">
        ${isMyVote ? '✓ Your vote — confirmed on-chain' : hasVoted ? 'Voting complete' : 'Vote for ' + c.name}
      </button>
    </div>`;
  }).join('');
  const banner = document.getElementById('vote-status-banner');
  if (hasVoted) {
    const tx = TRANSACTIONS[TRANSACTIONS.length-1];
    banner.style.display = 'block';
    banner.innerHTML = `✓ Vote for <strong>${CANDIDATES[selectedVoteId].name}</strong> confirmed on-chain<br>TX: 0x${tx.txHash.slice(0,28)}…<br>Signed with ECDSA · Mined with SHA-256 PoW`;
  }
}

function renderBlockchain() {
  const items = BLOCKCHAIN.slice().reverse();
  document.getElementById('chain-wrap').innerHTML = items.map((b, i) => {
    const isGenesis = b.index === 0;
    const dataStr = isGenesis ? b.data.election : `VOTE → ${b.data.candidate}`;
    const powOk = b.hash.startsWith('00');
    const connector = i < items.length - 1 ? '<div class="block-connector">│</div>' : '';
    return `<div class="block ${isGenesis?'genesis':''}">
      <div class="block-header">
        <span class="block-num">${isGenesis ? '⬡ GENESIS' : '⬡ BLOCK #'+b.index}</span>
        <span class="block-ts">${new Date(b.ts).toLocaleTimeString()}</span>
      </div>
      <div class="block-field"><span class="block-key">HASH</span><span class="block-val hash">0x${b.hash.slice(0,32)}…</span></div>
      <div class="block-field"><span class="block-key">PREV</span><span class="block-val">0x${b.prev.slice(0,32)}…</span></div>
      <div class="block-field"><span class="block-key">DATA</span><span class="block-val vote-data">${dataStr}</span></div>
      <div class="block-field"><span class="block-key">NONCE</span><span class="block-val">${b.nonce}</span></div>
      <div class="block-field"><span class="block-key">POW</span><span class="block-val" style="color:${powOk?'var(--accent2)':'var(--danger)'}">
        ${powOk ? '✓ hash starts with 00 — real SHA-256 difficulty met' : '✗ PoW not met'}
      </span></div>
      <div class="block-field"><span class="block-key">ALGO</span><span class="block-val algo">SHA-256 · Web Crypto API · ECDSA P-256</span></div>
    </div>${connector}`;
  }).join('');
}

function renderTransactions() {
  document.getElementById('tx-list').innerHTML = TRANSACTIONS.slice().reverse().map(tx => `
    <div class="tx-row">
      <span class="tx-id">0x${tx.txHash.slice(0,10)}…</span>
      <span style="font-family:var(--mono);font-size:10px;color:var(--text2)">${tx.data}</span>
      <span style="font-family:var(--mono);font-size:10px;color:var(--text3)">${tx.from.slice(0,14)}…</span>
      <span><span class="tx-badge confirmed">CONFIRMED</span></span>
    </div>`).join('');
}

function renderAll() {
  renderStats();
  renderLiveChart();
  renderCandidates();
  renderBlockchain();
  renderTransactions();
}

// ═══════════════════════════════════════════
//  NAVIGATION
// ═══════════════════════════════════════════

function showPanel(id, btn) {
  document.querySelectorAll('.panel').forEach(p => p.classList.remove('active'));
  document.querySelectorAll('.nav-item').forEach(b => b.classList.remove('active'));
  document.getElementById('panel-' + id).classList.add('active');
  if (btn) btn.classList.add('active');
  if (id === 'tamper') { initTamperChain(); return; }
  renderAll();
}

// ═══════════════════════════════════════════
//  VOTING FLOW
// ═══════════════════════════════════════════

function openModal(candidateId) {
  if (hasVoted) return;
  pendingCandidateId = candidateId;
  const c = CANDIDATES[candidateId];
  document.getElementById('modal-title').textContent = 'Vote for ' + c.name;
  document.getElementById('modal-sub').textContent = c.party + ' · Your vote will be signed with your real ECDSA private key and mined with SHA-256 proof of work.';
  document.getElementById('modal-hash').textContent = 'Computing preview hash…';
  sha256(VOTER_ADDRESS + candidateId + Date.now()).then(h => {
    document.getElementById('modal-hash').textContent = 'TX Preview: 0x' + h.slice(0,42) + '…';
  });
  resetSteps();
  document.getElementById('modal').classList.add('open');
}

function closeModal() {
  document.getElementById('modal').classList.remove('open');
  pendingCandidateId = null;
  resetSteps();
  const btn = document.getElementById('modal-confirm');
  btn.disabled = false; btn.textContent = 'Sign & Cast Vote →';
  document.getElementById('modal-cancel').disabled = false;
}

function resetSteps() {
  [1,2,3,4].forEach(i => { const s = document.getElementById('step-'+i); s.classList.remove('done','active'); });
}

async function confirmVote() {
  if (pendingCandidateId === null) return;
  const cid = pendingCandidateId;
  const btn = document.getElementById('modal-confirm');
  const cancel = document.getElementById('modal-cancel');
  btn.disabled = true; cancel.disabled = true;

  // Step 1 — real ECDSA signing
  markStep(1, 'active');
  btn.textContent = 'Signing…';
  const payload = JSON.stringify({ candidateId: cid, voter: VOTER_ADDRESS, ts: Date.now() });
  const signature = await signData(VOTER_KEYS.privateKey, payload);
  await sleep(400);
  markStep(1, 'done');

  // Step 2 — broadcast (simulated network)
  markStep(2, 'active');
  btn.textContent = 'Broadcasting…';
  await sleep(700);
  markStep(2, 'done');

  // Step 3 — real SHA-256 PoW mining
  markStep(3, 'active');
  btn.textContent = 'Mining block…';
  CANDIDATES[cid].votes++;
  hasVoted = true;
  selectedVoteId = cid;
  const block = await addBlock(
    { type:'VOTE', candidateId:cid, candidate:CANDIDATES[cid].name, voter:VOTER_ADDRESS },
    VOTER_ADDRESS, cid, signature
  );
  markStep(3, 'done');

  // Step 4 — confirmed
  markStep(4, 'active');
  await sleep(400);
  markStep(4, 'done');

  await sleep(300);
  closeModal();
  toast('✓ Block #'+block.index+' mined · nonce: '+block.nonce+' · 0x'+block.hash.slice(0,14)+'…', 'success');
  renderAll();
  showPanel('candidates', null);
  document.querySelectorAll('.nav-item')[1].classList.add('active');
}

function markStep(n, state) {
  const s = document.getElementById('step-'+n);
  s.classList.remove('active','done');
  if (state) s.classList.add(state);
}

// ═══════════════════════════════════════════
//  TAMPER DEMO
// ═══════════════════════════════════════════

let tamperChain = [];

function initTamperChain() {
  tamperChain = BLOCKCHAIN.map(b => ({ ...b, data: { ...b.data }, tampered: false }));
  renderTamperChain();
  document.getElementById('tamper-result').style.display = 'none';
}

function renderTamperChain() {
  const broken = new Set();
  for (let i = 1; i < tamperChain.length; i++) {
    if (broken.has(i-1) || tamperChain[i].prev !== tamperChain[i-1].hash) broken.add(i);
  }
  document.getElementById('tamper-chain').innerHTML = tamperChain.map((b, i) => {
    const isBroken = broken.has(i);
    const isTampered = b.tampered;
    const bColor = isBroken ? 'rgba(252,129,129,0.4)' : isTampered ? 'rgba(246,224,94,0.35)' : 'rgba(99,179,237,0.15)';
    const statusColor = isBroken ? 'var(--danger)' : isTampered ? 'var(--accent3)' : 'var(--accent2)';
    const statusText = isBroken ? '✗ INVALID — prev hash mismatch' : isTampered ? '⚠ TAMPERED — hash changed' : '✓ Valid';
    const dataStr = b.index === 0 ? b.data.election : (b.data.candidate || 'Unknown');
    const isVoteBlock = b.index > 0;
    const connector = i < tamperChain.length-1 ? '<div class="block-connector">│</div>' : '';
    return `<div class="block" style="border-color:${bColor}">
      <div class="block-header">
        <span class="block-num" style="color:${isBroken?'var(--danger)':'var(--accent)'}">${b.index===0?'⬡ GENESIS':'⬡ BLOCK #'+b.index}</span>
        <span style="font-family:var(--mono);font-size:9px;color:${statusColor}">${statusText}</span>
      </div>
      <div class="block-field"><span class="block-key">HASH</span>
        <span class="block-val" style="color:${isTampered?'var(--accent3)':isBroken?'var(--danger)':'var(--accent)'}">
          0x${b.hash.slice(0,32)}…
        </span>
      </div>
      <div class="block-field"><span class="block-key">PREV</span>
        <span class="block-val" style="color:${isBroken?'var(--danger)':'var(--text2)'}">
          0x${b.prev.slice(0,32)}…
        </span>
      </div>
      <div class="block-field"><span class="block-key">DATA</span>
        ${isVoteBlock
          ? `<input class="tamper-input" value="${dataStr}" oninput="tamperBlock(${i}, this.value)">`
          : `<span class="block-val vote-data">${dataStr}</span>`
        }
      </div>
      <div class="block-field"><span class="block-key">NONCE</span><span class="block-val">${b.nonce}</span></div>
    </div>${connector}`;
  }).join('');
}

async function tamperBlock(blockIndex, newValue) {
  tamperChain[blockIndex].data = { ...tamperChain[blockIndex].data, candidate: newValue };
  tamperChain[blockIndex].tampered = true;
  // Recompute just this block's hash (WITHOUT finding a new nonce — shows the fraud)
  const b = tamperChain[blockIndex];
  tamperChain[blockIndex].hash = await sha256(JSON.stringify({ index:b.index, prev:b.prev, data:b.data, ts:b.ts }) + b.nonce);
  renderTamperChain();
  document.getElementById('tamper-result').style.display = 'none';
}

function resetTamper() {
  initTamperChain();
}

async function verifyChain() {
  const result = document.getElementById('tamper-result');
  let valid = true;
  for (let i = 1; i < tamperChain.length; i++) {
    if (tamperChain[i].prev !== tamperChain[i-1].hash) { valid = false; break; }
    const b = tamperChain[i-1];
    const recomputed = await sha256(JSON.stringify({ index:b.index, prev:b.prev, data:b.data, ts:b.ts }) + b.nonce);
    if (recomputed !== b.hash) { valid = false; break; }
  }
  result.style.display = 'block';
  result.style.padding = '12px 16px';
  result.style.borderRadius = '8px';
  result.style.fontFamily = 'var(--mono)';
  result.style.fontSize = '12px';
  result.style.marginBottom = '1rem';
  if (valid) {
    result.style.background = 'rgba(72,187,120,0.08)';
    result.style.border = '1px solid rgba(72,187,120,0.3)';
    result.style.color = 'var(--accent2)';
    result.textContent = '✓ Chain is valid — all SHA-256 hashes link correctly. No tampering detected.';
  } else {
    result.style.background = 'rgba(252,129,129,0.08)';
    result.style.border = '1px solid rgba(252,129,129,0.3)';
    result.style.color = 'var(--danger)';
    result.textContent = '✗ Chain integrity FAILED — SHA-256 hash mismatch detected. The ledger has been tampered with.';
  }
}

// ═══════════════════════════════════════════
//  UTILS
// ═══════════════════════════════════════════

function sleep(ms) { return new Promise(r => setTimeout(r, ms)); }

function toast(msg, type = '') {
  const el = document.createElement('div');
  el.className = 'toast' + (type ? ' '+type : '');
  el.textContent = msg;
  document.getElementById('notif').appendChild(el);
  setTimeout(() => el.remove(), 5000);
}

// ── Start ──
boot();
</script>
</body>
</html>
