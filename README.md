[visagia (2).html](https://github.com/user-attachments/files/25868215/visagia.2.html)
<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ViSaGiA — L'IA pour couper tes cheveux et doutes !</title>
<link href="https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:opsz,wght@12..96,400;12..96,600;12..96,700;12..96,800&family=DM+Sans:wght@400;500;600&display=swap" rel="stylesheet">
<style>
:root {
  --white: #ffffff;
  --black: #0a0a0a;
  --bg: #f5f4f0;
  --coral: #ff4d4d;
  --yellow: #ffe14d;
  --green: #1dbd6e;
  --blue: #1a6bff;
  --ink: #1a1a1a;
  --muted: #8a8a8a;
  --card: #ffffff;
  --border: #e8e8e8;
  --radius: 20px;
  --radius-sm: 12px;
}

* { margin: 0; padding: 0; box-sizing: border-box; }

body {
  font-family: 'DM Sans', sans-serif;
  background: var(--bg);
  color: var(--ink);
  min-height: 100vh;
}

/* ── LAYOUT ── */
#app {
  max-width: 600px;
  margin: 0 auto;
  padding: 32px 20px 80px;
}

/* ── HEADER ── */
header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 48px;
}

.logo-wrap { display: flex; align-items: center; gap: 10px; }

.logo-icon {
  width: 40px; height: 40px;
  background: var(--black);
  border-radius: 10px;
  display: flex; align-items: center; justify-content: center;
  font-size: 1.2rem;
}

.logo-text {
  font-family: 'Bricolage Grotesque', sans-serif;
  font-size: 1.25rem;
  font-weight: 800;
  color: var(--black);
  letter-spacing: -0.5px;
}

.logo-text .ia { color: var(--coral); }
.logo-text .a-end { color: var(--blue); }

.beta-pill {
  background: var(--yellow);
  color: var(--black);
  font-size: 0.7rem;
  font-weight: 700;
  padding: 5px 12px;
  border-radius: 100px;
  letter-spacing: 0.5px;
}

/* ── HERO ── */
.hero {
  margin-bottom: 40px;
}

.hero-eyebrow {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  background: var(--white);
  border: 1.5px solid var(--border);
  border-radius: 100px;
  padding: 6px 14px;
  font-size: 0.78rem;
  font-weight: 600;
  color: var(--muted);
  margin-bottom: 20px;
}

.hero-eyebrow span { font-size: 0.9rem; }

.hero h1 {
  font-family: 'Bricolage Grotesque', sans-serif;
  font-size: clamp(2rem, 6vw, 2.8rem);
  font-weight: 800;
  line-height: 1.1;
  letter-spacing: -1.5px;
  color: var(--black);
  margin-bottom: 14px;
}

.hero h1 em {
  font-style: normal;
  color: var(--coral);
}

.hero p {
  font-size: 1rem;
  color: var(--muted);
  line-height: 1.65;
  max-width: 420px;
}

/* ── CARDS ── */
.card {
  background: var(--card);
  border-radius: var(--radius);
  border: 1.5px solid var(--border);
  overflow: hidden;
}

/* ── UPLOAD ── */
.upload-card {
  padding: 40px 28px;
  text-align: center;
  cursor: pointer;
  transition: border-color 0.2s, box-shadow 0.2s;
  margin-bottom: 16px;
}

.upload-card:hover {
  border-color: var(--coral);
  box-shadow: 0 0 0 4px rgba(255,77,77,0.08);
}

.upload-card.drag-over {
  border-color: var(--coral);
  background: rgba(255,77,77,0.03);
}

.upload-emoji {
  font-size: 3.5rem;
  margin-bottom: 16px;
  display: block;
  line-height: 1;
}

.upload-card h3 {
  font-family: 'Bricolage Grotesque', sans-serif;
  font-size: 1.2rem;
  font-weight: 700;
  color: var(--black);
  margin-bottom: 6px;
}

.upload-card p {
  font-size: 0.85rem;
  color: var(--muted);
  margin-bottom: 24px;
  line-height: 1.5;
}

.upload-btn-inner {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: var(--black);
  color: var(--white);
  padding: 13px 24px;
  border-radius: 100px;
  font-size: 0.9rem;
  font-weight: 600;
  transition: transform 0.15s, background 0.15s;
}

.upload-card:hover .upload-btn-inner {
  background: var(--coral);
  transform: scale(1.03);
}

input[type=file] { display: none; }

/* ── FEATURES ROW ── */
.features-row {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 10px;
  margin-bottom: 32px;
}

.feature-pill {
  background: var(--white);
  border: 1.5px solid var(--border);
  border-radius: var(--radius-sm);
  padding: 14px 12px;
  text-align: center;
}

.feature-pill .icon { font-size: 1.4rem; margin-bottom: 6px; display: block; }
.feature-pill .label { font-size: 0.72rem; font-weight: 600; color: var(--ink); line-height: 1.3; }

/* ── PREVIEW ── */
.preview-card {
  margin-bottom: 16px;
  position: relative;
}

.preview-img-wrap {
  position: relative;
  overflow: hidden;
  border-radius: var(--radius) var(--radius) 0 0;
  background: #f0f0f0;
  max-height: 380px;
}

.preview-img-wrap img {
  width: 100%;
  max-height: 380px;
  object-fit: cover;
  display: block;
}

/* SCISSORS ANIMATION */
.scissors-overlay {
  position: absolute;
  inset: 0;
  pointer-events: none;
  opacity: 0;
  transition: opacity 0.3s;
}

.scissors-overlay.active { opacity: 1; }

.scissors-container {
  position: absolute;
  inset: 0;
}

/* Horizontal cut line */
.cut-line {
  position: absolute;
  left: 0; right: 0;
  height: 2px;
  background: repeating-linear-gradient(90deg, var(--coral) 0px, var(--coral) 8px, transparent 8px, transparent 16px);
  animation: cutMove 2.2s ease-in-out infinite;
  opacity: 0.7;
}

@keyframes cutMove {
  0%   { top: 15%; }
  25%  { top: 45%; }
  50%  { top: 70%; }
  75%  { top: 40%; }
  100% { top: 15%; }
}

/* Scissors emoji following the line */
.scissors-emoji {
  position: absolute;
  left: -10px;
  font-size: 1.8rem;
  animation: scissorsMove 2.2s ease-in-out infinite;
  filter: drop-shadow(0 2px 6px rgba(0,0,0,0.15));
  transform: rotate(90deg);
  line-height: 1;
}

@keyframes scissorsMove {
  0%   { top: calc(15% - 18px); left: 10%; }
  25%  { top: calc(45% - 18px); left: 40%; }
  50%  { top: calc(70% - 18px); left: 70%; }
  75%  { top: calc(40% - 18px); left: 50%; }
  100% { top: calc(15% - 18px); left: 10%; }
}

/* Second scissors going opposite */
.scissors-emoji-2 {
  position: absolute;
  font-size: 1.4rem;
  animation: scissorsMove2 2.8s ease-in-out infinite 0.4s;
  filter: drop-shadow(0 2px 6px rgba(0,0,0,0.1));
  transform: rotate(-45deg);
  opacity: 0.6;
  line-height: 1;
}

@keyframes scissorsMove2 {
  0%   { top: 60%; left: 80%; }
  33%  { top: 20%; left: 55%; }
  66%  { top: 75%; left: 25%; }
  100% { top: 60%; left: 80%; }
}

/* Cut lines - multiple horizontal snips */
.snip-line {
  position: absolute;
  height: 1.5px;
  background: var(--coral);
  border-radius: 2px;
  animation: snipAppear 2s ease-in-out infinite;
  opacity: 0;
}
.snip-line:nth-child(3) { width: 60px; top: 30%; left: 20%; animation-delay: 0.3s; }
.snip-line:nth-child(4) { width: 45px; top: 55%; left: 55%; animation-delay: 0.9s; }
.snip-line:nth-child(5) { width: 70px; top: 72%; left: 30%; animation-delay: 1.5s; }

@keyframes snipAppear {
  0%   { opacity: 0; width: 0; }
  30%  { opacity: 0.6; }
  60%  { opacity: 0.4; }
  100% { opacity: 0; }
}

/* Corner brackets */
.bracket {
  position: absolute;
  width: 22px; height: 22px;
}
.bracket-tl { top: 12px; left: 12px; border-top: 3px solid var(--coral); border-left: 3px solid var(--coral); border-radius: 3px 0 0 0; }
.bracket-tr { top: 12px; right: 12px; border-top: 3px solid var(--coral); border-right: 3px solid var(--coral); border-radius: 0 3px 0 0; }
.bracket-bl { bottom: 12px; left: 12px; border-bottom: 3px solid var(--coral); border-left: 3px solid var(--coral); border-radius: 0 0 0 3px; }
.bracket-br { bottom: 12px; right: 12px; border-bottom: 3px solid var(--coral); border-right: 3px solid var(--coral); border-radius: 0 0 3px 0; }

/* Scanning label */
.scanning-label {
  position: absolute;
  bottom: 16px;
  left: 50%;
  transform: translateX(-50%);
  background: rgba(255,255,255,0.92);
  border: 1.5px solid var(--border);
  border-radius: 100px;
  padding: 6px 16px;
  font-size: 0.75rem;
  font-weight: 700;
  color: var(--coral);
  letter-spacing: 0.5px;
  white-space: nowrap;
  backdrop-filter: blur(8px);
}

.preview-actions {
  display: flex;
  gap: 10px;
  padding: 16px;
  background: var(--white);
  border-top: 1.5px solid var(--border);
}

/* ── BUTTONS ── */
.btn-primary {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  background: var(--black);
  color: var(--white);
  border: none;
  padding: 15px 24px;
  border-radius: 100px;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.92rem;
  font-weight: 700;
  cursor: pointer;
  transition: background 0.2s, transform 0.15s;
}

.btn-primary:hover { background: var(--coral); transform: scale(1.02); }
.btn-primary:disabled { background: var(--border); color: var(--muted); cursor: not-allowed; transform: none; }

.btn-ghost {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 6px;
  background: transparent;
  color: var(--muted);
  border: 1.5px solid var(--border);
  padding: 15px 18px;
  border-radius: 100px;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.85rem;
  font-weight: 600;
  cursor: pointer;
  transition: border-color 0.2s, color 0.2s;
}
.btn-ghost:hover { border-color: var(--ink); color: var(--ink); }

/* ── LOADING ── */
.loading-card {
  padding: 48px 28px;
  text-align: center;
}

.scissors-loader {
  font-size: 3rem;
  display: block;
  margin-bottom: 20px;
  animation: snip 0.7s ease-in-out infinite alternate;
}

@keyframes snip {
  from { transform: rotate(-15deg) scale(1); }
  to   { transform: rotate(15deg) scale(1.1); }
}

.loading-title {
  font-family: 'Bricolage Grotesque', sans-serif;
  font-size: 1.3rem;
  font-weight: 700;
  color: var(--black);
  margin-bottom: 8px;
}

.loading-sub {
  font-size: 0.88rem;
  color: var(--muted);
  margin-bottom: 32px;
}

.steps-list {
  list-style: none;
  text-align: left;
  max-width: 280px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.step-item {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 12px 16px;
  border-radius: var(--radius-sm);
  background: var(--bg);
  border: 1.5px solid transparent;
  font-size: 0.85rem;
  font-weight: 500;
  color: var(--muted);
  transition: all 0.3s;
}

.step-item.active {
  background: var(--white);
  border-color: var(--coral);
  color: var(--black);
}

.step-item.done {
  background: rgba(29,189,110,0.07);
  border-color: rgba(29,189,110,0.2);
  color: var(--green);
}

.step-dot {
  width: 8px; height: 8px;
  border-radius: 50%;
  background: var(--border);
  flex-shrink: 0;
  transition: background 0.3s;
}

.step-item.active .step-dot { background: var(--coral); animation: dotPulse 0.8s ease-in-out infinite alternate; }
.step-item.done .step-dot { background: var(--green); }

@keyframes dotPulse {
  from { transform: scale(1); opacity: 1; }
  to   { transform: scale(1.5); opacity: 0.6; }
}

/* ── RESULTS ── */
.results-wrap { animation: fadeUp 0.5s ease; }

@keyframes fadeUp {
  from { opacity: 0; transform: translateY(16px); }
  to   { opacity: 1; transform: translateY(0); }
}

/* Analysis summary */
.analysis-summary {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
  margin-bottom: 24px;
}

.summary-card {
  background: var(--white);
  border: 1.5px solid var(--border);
  border-radius: var(--radius-sm);
  padding: 16px;
}

.summary-card .s-label {
  font-size: 0.7rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  color: var(--muted);
  margin-bottom: 6px;
}

.summary-card .s-value {
  font-family: 'Bricolage Grotesque', sans-serif;
  font-size: 1.15rem;
  font-weight: 700;
  color: var(--black);
  margin-bottom: 4px;
}

.summary-card .s-detail {
  font-size: 0.8rem;
  color: var(--muted);
  line-height: 1.4;
}

.shape-pill {
  display: inline-block;
  background: var(--yellow);
  color: var(--black);
  font-size: 0.68rem;
  font-weight: 700;
  padding: 3px 10px;
  border-radius: 100px;
  margin-top: 6px;
  letter-spacing: 0.3px;
}

/* Section headers */
.section-label {
  font-size: 0.72rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 1px;
  color: var(--muted);
  margin-bottom: 14px;
  margin-top: 28px;
  display: flex;
  align-items: center;
  gap: 8px;
}
.section-label::after { content: ''; flex: 1; height: 1.5px; background: var(--border); }

/* Haircut cards */
.haircut-card {
  background: var(--white);
  border: 1.5px solid var(--border);
  border-radius: var(--radius);
  padding: 24px;
  margin-bottom: 12px;
  transition: border-color 0.2s, box-shadow 0.2s;
  position: relative;
  overflow: hidden;
}

.haircut-card:hover {
  border-color: #d0d0d0;
  box-shadow: 0 4px 24px rgba(0,0,0,0.06);
}

.haircut-card.best {
  border-color: var(--coral);
}

.best-badge {
  position: absolute;
  top: 16px; right: 16px;
  background: var(--coral);
  color: var(--white);
  font-size: 0.65rem;
  font-weight: 700;
  padding: 4px 12px;
  border-radius: 100px;
  letter-spacing: 0.3px;
}

.trend-badge {
  display: inline-block;
  background: rgba(26,107,255,0.1);
  color: var(--blue);
  font-size: 0.65rem;
  font-weight: 700;
  padding: 3px 10px;
  border-radius: 100px;
  margin-left: 6px;
  letter-spacing: 0.3px;
}

.haircut-rank {
  font-size: 0.7rem;
  font-weight: 700;
  color: var(--muted);
  text-transform: uppercase;
  letter-spacing: 0.5px;
  margin-bottom: 6px;
}

.haircut-name {
  font-family: 'Bricolage Grotesque', sans-serif;
  font-size: 1.35rem;
  font-weight: 800;
  color: var(--black);
  letter-spacing: -0.5px;
  margin-bottom: 4px;
}

.haircut-inspo {
  font-size: 0.82rem;
  color: var(--muted);
  margin-bottom: 18px;
}

.haircut-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 14px;
  margin-bottom: 14px;
}

@media (max-width: 480px) { .haircut-grid { grid-template-columns: 1fr; } }

.haircut-block-label {
  font-size: 0.68rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  color: var(--muted);
  margin-bottom: 5px;
}

.haircut-block-text {
  font-size: 0.85rem;
  color: #444;
  line-height: 1.55;
}

.haircut-avoid {
  background: rgba(255,77,77,0.05);
  border: 1.5px solid rgba(255,77,77,0.12);
  border-radius: 10px;
  padding: 10px 14px;
  font-size: 0.82rem;
  color: #c0392b;
  line-height: 1.5;
  margin-top: 4px;
}

.haircut-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
  margin-top: 14px;
}

.tag {
  background: var(--bg);
  border: 1.5px solid var(--border);
  border-radius: 100px;
  padding: 4px 12px;
  font-size: 0.72rem;
  font-weight: 600;
  color: var(--ink);
}

/* Coiffeur tip */
.coiffeur-card {
  background: var(--black);
  border-radius: var(--radius);
  padding: 24px;
  color: var(--white);
  margin-top: 8px;
}

.coiffeur-card .c-icon { font-size: 1.8rem; margin-bottom: 10px; display: block; }
.coiffeur-card .c-title {
  font-family: 'Bricolage Grotesque', sans-serif;
  font-size: 1rem;
  font-weight: 700;
  margin-bottom: 8px;
}
.coiffeur-card .c-text { font-size: 0.87rem; color: rgba(255,255,255,0.7); line-height: 1.6; }

/* Restart */
.restart-row {
  display: flex;
  justify-content: center;
  margin-top: 32px;
}

.btn-restart {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: transparent;
  color: var(--muted);
  border: 1.5px solid var(--border);
  padding: 12px 22px;
  border-radius: 100px;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.85rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.2s;
}
.btn-restart:hover { border-color: var(--ink); color: var(--ink); }

/* Error */
.error-card {
  background: rgba(255,77,77,0.06);
  border: 1.5px solid rgba(255,77,77,0.25);
  border-radius: var(--radius);
  padding: 24px;
  text-align: center;
}
.error-card .e-icon { font-size: 2rem; margin-bottom: 10px; display: block; }
.error-card .e-title { font-family: 'Bricolage Grotesque', sans-serif; font-size: 1rem; font-weight: 700; color: var(--coral); margin-bottom: 6px; }
.error-card .e-msg { font-size: 0.85rem; color: var(--muted); margin-bottom: 16px; line-height: 1.5; }
</style>
</head>
<body>
<div id="app">

  <!-- HEADER -->
  <header>
    <div class="logo-wrap">
      <div class="logo-icon">✂️</div>
      <div>
        <div class="logo-text">ViSaG<span class="ia">IA</span></div>
      </div>
    </div>
    <div class="beta-pill">✨ Bêta</div>
  </header>

  <!-- HERO -->
  <div class="hero" id="heroSection">
    <div class="hero-eyebrow">
      <span>🧠</span> Analyse IA · Tendances 2026
    </div>
    <h1>L'IA qui coupe tes cheveux<br><em>et tes doutes.</em></h1>
    <p>Upload ta photo, on analyse ta morphologie et on te dit exactement quelle coupe te fera péter la forme.</p>
  </div>

  <!-- UPLOAD -->
  <div id="uploadSection">
    <div class="card upload-card" id="dropZone">
      <span class="upload-emoji">🤳</span>
      <h3>Montre-nous ta tête !</h3>
      <p>Une photo de face, bien éclairée<br>JPG, PNG ou WEBP</p>
      <div class="upload-btn-inner">
        <span>📸</span> Choisir une photo
      </div>
      <input type="file" id="fileInput" accept="image/*">
    </div>

    <div class="features-row">
      <div class="feature-pill">
        <span class="icon">🔍</span>
        <div class="label">Analyse morpho</div>
      </div>
      <div class="feature-pill">
        <span class="icon">✂️</span>
        <div class="label">3 coupes perso</div>
      </div>
      <div class="feature-pill">
        <span class="icon">🔥</span>
        <div class="label">Tendances 2026</div>
      </div>
    </div>
  </div>

  <!-- PREVIEW -->
  <div id="previewSection" style="display:none">
    <div class="card preview-card">
      <div class="preview-img-wrap">
        <img id="previewImg" src="" alt="Ta photo">
        <div class="scissors-overlay" id="scissorsOverlay">
          <div class="scissors-container">
            <div class="cut-line"></div>
            <div class="scissors-emoji">✂️</div>
            <div class="scissors-emoji-2">✂️</div>
            <div class="snip-line"></div>
            <div class="snip-line"></div>
            <div class="snip-line"></div>
          </div>
          <div class="bracket bracket-tl"></div>
          <div class="bracket bracket-tr"></div>
          <div class="bracket bracket-bl"></div>
          <div class="bracket bracket-br"></div>
          <div class="scanning-label">✂️ Analyse en cours…</div>
        </div>
      </div>
      <div class="preview-actions">
        <button class="btn-primary" id="analyzeBtn">
          ✂️ Analyser ma tête !
        </button>
        <button class="btn-ghost" id="changeBtn">Changer</button>
      </div>
    </div>
  </div>

  <!-- LOADING -->
  <div id="loadingSection" style="display:none">
    <div class="card loading-card">
      <span class="scissors-loader">✂️</span>
      <div class="loading-title">On taille dans le vif !</div>
      <div class="loading-sub">L'IA analyse ta morphologie…</div>
      <ul class="steps-list" id="stepsList">
        <li class="step-item" id="step0"><div class="step-dot"></div>Lecture de ta morphologie</li>
        <li class="step-item" id="step1"><div class="step-dot"></div>Estimation de l'âge & texture</li>
        <li class="step-item" id="step2"><div class="step-dot"></div>Croisement tendances 2026</li>
        <li class="step-item" id="step3"><div class="step-dot"></div>Génération des recommandations</li>
      </ul>
    </div>
  </div>

  <!-- RESULTS -->
  <div id="resultsSection" style="display:none">
    <div class="results-wrap" id="resultsContent"></div>
    <div class="restart-row">
      <button class="btn-restart" id="restartBtn">🔄 Nouvelle analyse</button>
    </div>
  </div>

  <!-- ERROR -->
  <div id="errorSection" style="display:none">
    <div class="error-card">
      <span class="e-icon">😬</span>
      <div class="e-title">Oups, quelque chose a raté</div>
      <div class="e-msg" id="errorMsg">Essaie avec une photo plus nette, de face et bien éclairée.</div>
      <button class="btn-primary" style="max-width:200px;margin:0 auto" id="errorRetryBtn">Réessayer</button>
    </div>
  </div>

</div>

<script>
// ── PROMPTS ──────────────────────────────────────────────────
const TRENDS = `TENDANCES COIFFURE 2025-2026 :
- Wolf Cut / Shag : couches déstructurées, fusion mulet + shag, rebelle chic
- Butterfly Haircut : couches dégradées, volume haut, mouvement naturel
- Carré graphique / Bob parisien : lignes nettes, légèrement ondulé
- Frange rideau (curtain bangs) : encadre le visage, doux et flatteur
- Pixie long : effilé, polyvalent
- Fade / Dégradé (low, mid, high) : incontournable
- Undercut : contraste volume haut vs côtés courts
- French Crop + fade : net, streetwear
- Quiet Luxury Hair : longueurs naturelles, minimaliste
- Mulet revisité (version longue) : avant-gardiste
- Buzz cut géométrique : ultra net`;

const SYSTEM = `Tu es ViSaGiA, un visagiste expert et pote bienveillant. Tu analyses une photo de visage et donnes 3 recommandations de coupes ultra-personnalisées, avec un ton décontracté et tutoiement.

${TRENDS}

Réponds UNIQUEMENT en JSON valide, sans markdown ni texte autour.

{
  "analyse": {
    "forme_visage": "Ovale | Carré | Rond | Cœur | Diamant | Rectangle | Triangle",
    "age_estime": "ex: 22-28 ans",
    "traits_cles": "traits distinctifs en 1 phrase décontractée",
    "texture_estimee": "ex: cheveux fins, épais, bouclés (si visible)",
    "conseil_general": "1-2 phrases fun et bienveillantes sur la philosophie de coupe"
  },
  "recommandations": [
    {
      "rang": 1,
      "nom": "Nom de la coupe",
      "inspiration": "ex: À la Zendaya / Timothée Chalamet",
      "tendance_2026": "oui | non",
      "pourquoi": "Pourquoi cette coupe va parfaitement à CE visage — ton décontracté",
      "comment_porter": "Conseils pratiques : texture, longueur, produits, entretien",
      "a_eviter": "Ce qui ne fonctionnerait pas sur ce visage",
      "tags": ["tag1","tag2","tag3"]
    },
    {"rang": 2},
    {"rang": 3}
  ],
  "conseil_coiffeur": "Ce qu'il faut dire exactement chez le coiffeur, façon pote qui conseille"
}`;

// ── STATE ─────────────────────────────────────────────────────
let b64 = null, mtype = null;

// ── DOM ───────────────────────────────────────────────────────
const fileInput     = document.getElementById('fileInput');
const dropZone      = document.getElementById('dropZone');
const previewImg    = document.getElementById('previewImg');
const analyzeBtn    = document.getElementById('analyzeBtn');
const changeBtn     = document.getElementById('changeBtn');
const restartBtn    = document.getElementById('restartBtn');
const errorRetryBtn = document.getElementById('errorRetryBtn');
const scissorsOverlay = document.getElementById('scissorsOverlay');

const sections = {
  upload:  document.getElementById('uploadSection'),
  preview: document.getElementById('previewSection'),
  loading: document.getElementById('loadingSection'),
  results: document.getElementById('resultsSection'),
  error:   document.getElementById('errorSection'),
  hero:    document.getElementById('heroSection'),
};

function show(name) {
  Object.keys(sections).forEach(k => {
    if (k === 'hero') return; // always visible initially
    sections[k].style.display = k === name ? 'block' : 'none';
  });
  if (name !== 'upload') sections.hero.style.display = 'none';
  else sections.hero.style.display = 'block';
}

// ── FILE HANDLING ─────────────────────────────────────────────
dropZone.addEventListener('click', () => fileInput.click());
dropZone.addEventListener('dragover', e => { e.preventDefault(); dropZone.classList.add('drag-over'); });
dropZone.addEventListener('dragleave', () => dropZone.classList.remove('drag-over'));
dropZone.addEventListener('drop', e => {
  e.preventDefault();
  dropZone.classList.remove('drag-over');
  if (e.dataTransfer.files[0]) loadFile(e.dataTransfer.files[0]);
});
fileInput.addEventListener('change', e => { if (e.target.files[0]) loadFile(e.target.files[0]); });

function loadFile(file) {
  if (!file.type.startsWith('image/')) return;
  mtype = file.type;
  const reader = new FileReader();
  reader.onload = ev => {
    previewImg.src = ev.target.result;
    b64 = ev.target.result.split(',')[1];
    show('preview');
  };
  reader.readAsDataURL(file);
}

// ── RESET ─────────────────────────────────────────────────────
function reset() {
  b64 = null; mtype = null;
  fileInput.value = '';
  previewImg.src = '';
  scissorsOverlay.classList.remove('active');
  show('upload');
}

changeBtn.addEventListener('click', reset);
restartBtn.addEventListener('click', reset);
errorRetryBtn.addEventListener('click', reset);

// ── LOADING STEPS ─────────────────────────────────────────────
let stepTimers = [];

function animateSteps() {
  stepTimers.forEach(clearTimeout);
  for (let i = 0; i < 4; i++) document.getElementById('step'+i).className = 'step-item';
  stepTimers = [0,1,2,3].map(i =>
    setTimeout(() => {
      if (i > 0) document.getElementById('step'+(i-1)).className = 'step-item done';
      document.getElementById('step'+i).className = 'step-item active';
    }, i * 1500)
  );
}

function doneSteps() {
  stepTimers.forEach(clearTimeout);
  for (let i = 0; i < 4; i++) document.getElementById('step'+i).className = 'step-item done';
}

// ── ANALYZE ───────────────────────────────────────────────────
analyzeBtn.addEventListener('click', async () => {
  // Scissors animation on photo
  scissorsOverlay.classList.add('active');
  analyzeBtn.disabled = true;

  await new Promise(r => setTimeout(r, 1400));
  scissorsOverlay.classList.remove('active');
  show('loading');
  animateSteps();

  try {
    const res = await fetch('https://api.anthropic.com/v1/messages', {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
        'x-api-key': window.__HAIRU_KEY__ || '',
        'anthropic-version': '2023-06-01',
        'anthropic-dangerous-direct-browser-access': 'true'
      },
      body: JSON.stringify({
        model: 'claude-sonnet-4-20250514',
        max_tokens: 1024,
        system: SYSTEM,
        messages: [{
          role: 'user',
          content: [
            { type: 'image', source: { type: 'base64', media_type: mtype, data: b64 } },
            { type: 'text', text: 'Analyse ce visage et donne 3 recommandations de coupes en JSON.' }
          ]
        }]
      })
    });

    const data = await res.json();
    if (data.error) throw new Error(data.error.message);

    const raw = data.content.map(b => b.text||'').join('');
    let json = raw.replace(/```json|```/g,'').trim();
    const s = json.indexOf('{'), e = json.lastIndexOf('}');
    if (s !== -1) json = json.slice(s, e+1);
    const parsed = JSON.parse(json);

    doneSteps();
    renderResults(parsed);

  } catch(err) {
    doneSteps();
    document.getElementById('errorMsg').textContent = err.message || 'Essaie avec une photo plus nette, de face.';
    show('error');
    analyzeBtn.disabled = false;
  }
});

// ── RENDER ────────────────────────────────────────────────────
function renderResults(d) {
  const a = d.analyse;
  let html = `
    <div class="analysis-summary">
      <div class="summary-card">
        <div class="s-label">Forme du visage</div>
        <div class="s-value">${a.forme_visage}</div>
        <div class="s-detail">${a.traits_cles}</div>
        <span class="shape-pill">${a.forme_visage.toUpperCase()}</span>
      </div>
      <div class="summary-card">
        <div class="s-label">Profil</div>
        <div class="s-value">${a.age_estime}</div>
        <div class="s-detail">${a.texture_estimee || ''}</div>
        <div class="s-detail" style="margin-top:8px;color:#555">${a.conseil_general}</div>
      </div>
    </div>
    <div class="section-label">Tes 3 coupes idéales</div>
  `;

  d.recommandations.forEach((r, i) => {
    html += `
      <div class="haircut-card ${i===0?'best':''}">
        ${i===0 ? '<div class="best-badge">⭐ Meilleur match</div>' : ''}
        <div class="haircut-rank">Coupe n°${r.rang} ${r.tendance_2026==='oui'?'<span class="trend-badge">🔥 Trend 2026</span>':''}</div>
        <div class="haircut-name">${r.nom}</div>
        <div class="haircut-inspo">✨ ${r.inspiration}</div>
        <div class="haircut-grid">
          <div>
            <div class="haircut-block-label">Pourquoi ça te va</div>
            <div class="haircut-block-text">${r.pourquoi}</div>
          </div>
          <div>
            <div class="haircut-block-label">Comment le porter</div>
            <div class="haircut-block-text">${r.comment_porter}</div>
          </div>
        </div>
        <div class="haircut-block-label" style="margin-top:12px">À éviter</div>
        <div class="haircut-avoid">⚠️ ${r.a_eviter}</div>
        <div class="haircut-tags">${(r.tags||[]).map(t=>`<span class="tag">${t}</span>`).join('')}</div>
      </div>
    `;
  });

  if (d.conseil_coiffeur) {
    html += `
      <div class="section-label">Chez le coiffeur</div>
      <div class="coiffeur-card">
        <span class="c-icon">💈</span>
        <div class="c-title">Ce que tu dis en entrant :</div>
        <div class="c-text">${d.conseil_coiffeur}</div>
      </div>
    `;
  }

  document.getElementById('resultsContent').innerHTML = html;
  show('results');
}

// ── API KEY SCREEN ────────────────────────────────────────────
(function() {
  const stored = sessionStorage.getItem('visagia_key');
  if (stored) { window.__HAIRU_KEY__ = stored; return; }

  const overlay = document.createElement('div');
  overlay.style.cssText = 'position:fixed;inset:0;z-index:999;background:var(--bg);display:flex;align-items:center;justify-content:center;padding:24px;font-family:DM Sans,sans-serif;';
  overlay.innerHTML = `
    <div style="background:#fff;border-radius:24px;border:1.5px solid #e8e8e8;padding:40px 32px;max-width:420px;width:100%;">
      <div style="font-size:2.5rem;margin-bottom:16px;">✂️</div>
      <div style="font-family:Bricolage Grotesque,sans-serif;font-size:1.5rem;font-weight:800;color:#0a0a0a;margin-bottom:8px;">Bienvenue sur ViSaGIA !</div>
      <p style="font-size:0.9rem;color:#8a8a8a;line-height:1.6;margin-bottom:28px;">Entre ta clé API Anthropic pour démarrer.<br>Elle reste <strong style='color:#0a0a0a'>uniquement dans ton navigateur</strong>, jamais partagée.</p>
      <label style="font-size:0.72rem;font-weight:700;text-transform:uppercase;letter-spacing:0.5px;color:#8a8a8a;display:block;margin-bottom:8px;">Clé API Anthropic</label>
      <input id="keyInput" type="password" placeholder="sk-ant-api03-..." style="width:100%;padding:13px 16px;border-radius:12px;border:1.5px solid #e8e8e8;font-family:DM Sans,sans-serif;font-size:0.88rem;outline:none;color:#0a0a0a;background:#f5f4f0;margin-bottom:8px;">
      <div id="keyError" style="color:#ff4d4d;font-size:0.8rem;min-height:20px;margin-bottom:12px;"></div>
      <button id="keySubmit" style="width:100%;padding:14px;border-radius:100px;border:none;background:#0a0a0a;color:#fff;font-family:DM Sans,sans-serif;font-size:0.92rem;font-weight:700;cursor:pointer;">C'est parti ✂️</button>
      <p style="font-size:0.72rem;color:#aaa;text-align:center;margin-top:16px;">Pas de clé ? → <a href="https://console.anthropic.com/settings/keys" target="_blank" style="color:#ff4d4d;">console.anthropic.com</a></p>
    </div>
  `;
  document.body.appendChild(overlay);

  const input = document.getElementById('keyInput');
  const btn   = document.getElementById('keySubmit');
  const err   = document.getElementById('keyError');

  btn.addEventListener('mouseover', () => btn.style.background = '#ff4d4d');
  btn.addEventListener('mouseout',  () => btn.style.background = '#0a0a0a');

  function submit() {
    const val = input.value.trim();
    if (!val.startsWith('sk-ant-')) { err.textContent = '⚠️ La clé doit commencer par sk-ant-…'; return; }
    window.__HAIRU_KEY__ = val;
    sessionStorage.setItem('visagia_key', val);
    overlay.remove();
  }

  btn.addEventListener('click', submit);
  input.addEventListener('keydown', e => { if (e.key === 'Enter') submit(); });
  input.focus();
})();
</script>
</body>
</html>
