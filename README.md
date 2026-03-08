<!DOCTYPE html>
<html lang="it">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>J0joFra — GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Mono:ital,wght@0,300;0,400;0,500;1,300&family=Instrument+Serif:ital@0;1&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0a0a;
    --surface: #111;
    --border: #1e1e1e;
    --accent: #e8ff47;
    --accent2: #ff4747;
    --text: #f0f0f0;
    --muted: #555;
    --card: #131313;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Mono', monospace;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* grain overlay */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
    pointer-events: none;
    z-index: 999;
    opacity: 0.6;
  }

  .page {
    max-width: 860px;
    margin: 0 auto;
    padding: 60px 24px 80px;
  }

  /* ── HERO ── */
  .hero {
    border: 1px solid var(--border);
    padding: 48px 48px 40px;
    position: relative;
    margin-bottom: 2px;
    overflow: hidden;
    animation: fadeUp 0.7s ease both;
  }

  .hero::after {
    content: '';
    position: absolute;
    top: 0; right: 0;
    width: 220px; height: 220px;
    background: radial-gradient(circle at top right, rgba(232,255,71,0.07), transparent 70%);
    pointer-events: none;
  }

  .hero-tag {
    font-size: 11px;
    letter-spacing: 0.2em;
    color: var(--muted);
    text-transform: uppercase;
    margin-bottom: 12px;
  }

  .hero-tag span {
    color: var(--accent);
  }

  .hero h1 {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(64px, 10vw, 112px);
    line-height: 0.9;
    letter-spacing: 0.02em;
    margin-bottom: 24px;
  }

  .hero h1 em {
    font-style: normal;
    color: var(--accent);
  }

  .hero-desc {
    font-size: 13px;
    color: #888;
    line-height: 1.7;
    max-width: 440px;
  }

  .hero-desc strong {
    color: var(--text);
    font-weight: 500;
  }

  .corner-label {
    position: absolute;
    bottom: 20px;
    right: 24px;
    font-size: 10px;
    letter-spacing: 0.15em;
    color: var(--muted);
    text-transform: uppercase;
  }

  /* ── GRID LAYOUT ── */
  .grid-2 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2px;
    margin-bottom: 2px;
  }

  .grid-3 {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 2px;
    margin-bottom: 2px;
  }

  /* ── CARD ── */
  .card {
    background: var(--card);
    border: 1px solid var(--border);
    padding: 28px 28px 24px;
    animation: fadeUp 0.7s ease both;
  }

  .card-label {
    font-size: 10px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .card-label::before {
    content: '';
    display: inline-block;
    width: 6px; height: 6px;
    background: var(--accent);
    border-radius: 50%;
  }

  /* ── ROLES ── */
  .roles { display: flex; flex-direction: column; gap: 10px; }

  .role-item {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 10px 14px;
    border: 1px solid var(--border);
    font-size: 12px;
    transition: border-color 0.2s, background 0.2s;
  }

  .role-item:hover {
    border-color: var(--accent);
    background: rgba(232,255,71,0.03);
  }

  .role-icon { font-size: 16px; }
  .role-title { color: var(--text); font-weight: 500; }
  .role-sub { color: var(--muted); font-size: 11px; margin-top: 1px; }

  /* ── SOCIALS ── */
  .socials { display: flex; flex-direction: column; gap: 8px; }

  .social-link {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 10px 14px;
    border: 1px solid var(--border);
    text-decoration: none;
    color: var(--text);
    font-size: 12px;
    transition: border-color 0.2s, background 0.2s;
  }

  .social-link:hover {
    border-color: var(--accent);
    background: rgba(232,255,71,0.03);
  }

  .social-platform {
    color: var(--muted);
    font-size: 10px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    margin-left: auto;
  }

  /* ── TECH STACK ── */
  .stack-section { margin-bottom: 2px; }

  .stack-category {
    border: 1px solid var(--border);
    padding: 20px 24px;
    margin-bottom: 2px;
    animation: fadeUp 0.7s ease both;
  }

  .stack-category-title {
    font-size: 10px;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: var(--muted);
    margin-bottom: 14px;
  }

  .tags {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
  }

  .tag {
    font-size: 11px;
    padding: 4px 10px;
    border: 1px solid var(--border);
    color: #aaa;
    letter-spacing: 0.05em;
    transition: all 0.15s;
    cursor: default;
  }

  .tag:hover {
    border-color: var(--accent);
    color: var(--accent);
    background: rgba(232,255,71,0.04);
  }

  .tag.highlight {
    border-color: rgba(232,255,71,0.3);
    color: var(--accent);
  }

  /* ── STATS ── */
  .stats-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2px;
    margin-bottom: 2px;
  }

  .stat-card {
    border: 1px solid var(--border);
    padding: 24px 20px;
    text-align: center;
    animation: fadeUp 0.7s ease both;
    position: relative;
    overflow: hidden;
  }

  .stat-card::before {
    content: '';
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: var(--accent);
    transform: scaleX(0);
    transition: transform 0.3s ease;
  }

  .stat-card:hover::before { transform: scaleX(1); }

  .stat-number {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 42px;
    line-height: 1;
    color: var(--accent);
    margin-bottom: 6px;
  }

  .stat-label {
    font-size: 10px;
    letter-spacing: 0.15em;
    text-transform: uppercase;
    color: var(--muted);
  }

  /* ── GITHUB IMAGES ── */
  .github-images {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2px;
    margin-bottom: 2px;
  }

  .gh-img-wrap {
    border: 1px solid var(--border);
    padding: 4px;
    animation: fadeUp 0.7s ease both;
  }

  .gh-img-wrap img {
    width: 100%;
    display: block;
    filter: brightness(0.95);
  }

  /* ── DONATE ── */
  .donate-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2px;
  }

  .donate-btn {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
    padding: 20px;
    border: 1px solid var(--border);
    text-decoration: none;
    color: var(--text);
    font-size: 12px;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    transition: all 0.2s;
  }

  .donate-btn:hover {
    border-color: var(--accent);
    color: var(--accent);
    background: rgba(232,255,71,0.04);
  }

  /* ── QUOTE ── */
  .quote-card {
    border: 1px solid var(--border);
    padding: 32px 32px;
    margin-bottom: 2px;
    position: relative;
    animation: fadeUp 0.7s ease both;
  }

  .quote-mark {
    font-family: 'Instrument Serif', serif;
    font-size: 80px;
    line-height: 0;
    color: rgba(232,255,71,0.15);
    position: absolute;
    top: 24px;
    left: 20px;
  }

  .quote-text {
    font-family: 'Instrument Serif', serif;
    font-style: italic;
    font-size: 18px;
    line-height: 1.6;
    color: #ccc;
    padding-left: 12px;
    border-left: 2px solid var(--accent);
  }

  /* ── FOOTER ── */
  .footer {
    border: 1px solid var(--border);
    padding: 20px 28px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 0.1em;
    animation: fadeUp 0.7s ease both;
  }

  .footer a {
    color: var(--accent);
    text-decoration: none;
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(16px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  .card:nth-child(1) { animation-delay: 0.05s; }
  .card:nth-child(2) { animation-delay: 0.1s; }
  .card:nth-child(3) { animation-delay: 0.15s; }
  .stat-card:nth-child(1) { animation-delay: 0.1s; }
  .stat-card:nth-child(2) { animation-delay: 0.15s; }
  .stat-card:nth-child(3) { animation-delay: 0.2s; }

  /* separator line */
  .sep {
    height: 1px;
    background: var(--border);
    margin: 32px 0;
  }

  @media (max-width: 600px) {
    .grid-2, .grid-3, .stats-grid, .github-images, .donate-row { grid-template-columns: 1fr; }
    .hero { padding: 32px 24px; }
    .hero h1 { font-size: 72px; }
  }
</style>
</head>
<body>
<div class="page">

  <!-- HERO -->
  <div class="hero">
    <div class="hero-tag">GitHub Profile <span>/ J0joFra</span></div>
    <h1>JOAQUIM<br><em>FRANCA</em><br>LANCI</h1>
    <p class="hero-desc">
      <strong>Business Analyst</strong> &amp; developer.<br>
      Fondatore di <strong>formula-rossa.it</strong> — appassionato di codice, dati e motori.
    </p>
    <div class="corner-label">Milano, IT</div>
  </div>

  <!-- ROLES + SOCIALS -->
  <div class="grid-2" style="margin-bottom:2px">
    <div class="card">
      <div class="card-label">Chi sono</div>
      <div class="roles">
        <div class="role-item">
          <span class="role-icon">🔭</span>
          <div>
            <div class="role-title">Business Analyst</div>
            <div class="role-sub">Dati, processi, insight</div>
          </div>
        </div>
        <div class="role-item">
          <span class="role-icon">🌱</span>
          <div>
            <div class="role-title">Founder</div>
            <div class="role-sub">formula-rossa.it</div>
          </div>
        </div>
        <div class="role-item">
          <span class="role-icon">💬</span>
          <div>
            <div class="role-title">Ask me about code</div>
            <div class="role-sub">Sempre disponibile</div>
          </div>
        </div>
      </div>
    </div>

    <div class="card">
      <div class="card-label">Socials</div>
      <div class="socials">
        <a class="social-link" href="https://twitch.tv/@big_eis" target="_blank">
          <svg width="16" height="16" fill="#9146FF" viewBox="0 0 24 24"><path d="M11.571 4.714h1.715v5.143H11.57zm4.715 0H18v5.143h-1.714zM6 0L1.714 4.286v15.428h5.143V24l4.286-4.286h3.428L22.286 12V0zm14.571 11.143l-3.428 3.428h-3.429l-3 3v-3H6.857V1.714h13.714z"/></svg>
          <div>
            <div>big_eis</div>
          </div>
          <span class="social-platform">Twitch</span>
        </a>
        <a class="social-link" href="https://youtube.com/@@jofrancalanci" target="_blank">
          <svg width="16" height="16" fill="#FF0000" viewBox="0 0 24 24"><path d="M23.495 6.205a3.007 3.007 0 0 0-2.088-2.088c-1.87-.501-9.396-.501-9.396-.501s-7.507-.01-9.396.501A3.007 3.007 0 0 0 .527 6.205a31.247 31.247 0 0 0-.522 5.805 31.247 31.247 0 0 0 .522 5.783 3.007 3.007 0 0 0 2.088 2.088c1.868.502 9.396.502 9.396.502s7.506 0 9.396-.502a3.007 3.007 0 0 0 2.088-2.088 31.247 31.247 0 0 0 .5-5.783 31.247 31.247 0 0 0-.5-5.805zM9.609 15.601V8.408l6.264 3.602z"/></svg>
          <div>
            <div>jofrancalanci</div>
          </div>
          <span class="social-platform">YouTube</span>
        </a>
        <a class="social-link" href="https://paypal.me/@JoaquimFrancalanci" target="_blank">
          <svg width="16" height="16" fill="#00457C" viewBox="0 0 24 24"><path d="M7.076 21.337H2.47a.641.641 0 0 1-.633-.74L4.944.901C5.026.382 5.474 0 5.998 0h7.46c2.57 0 4.578.543 5.69 1.81 1.01 1.15 1.304 2.42 1.012 4.287-.023.143-.047.291-.077.44l-.01.065v.045c-.12 3.162-2.17 5.345-5.956 5.345H11.3a.803.803 0 0 0-.795.679l-.85 5.384-.122.777a.64.64 0 0 1-.633.54H7.076z"/></svg>
          <div>
            <div>Supportami</div>
          </div>
          <span class="social-platform">PayPal</span>
        </a>
      </div>
    </div>
  </div>

  <!-- STATS -->
  <div class="stats-grid">
    <div class="stat-card">
      <div class="stat-number">7+</div>
      <div class="stat-label">Linguaggi</div>
    </div>
    <div class="stat-card">
      <div class="stat-number">30+</div>
      <div class="stat-label">Tool & Framework</div>
    </div>
    <div class="stat-card">
      <div class="stat-number">∞</div>
      <div class="stat-label">Curiosità</div>
    </div>
  </div>

  <!-- TECH STACK -->
  <div class="stack-category">
    <div class="stack-category-title">// Linguaggi</div>
    <div class="tags">
      <span class="tag highlight">Python</span>
      <span class="tag highlight">JavaScript</span>
      <span class="tag highlight">C#</span>
      <span class="tag">C</span>
      <span class="tag">Java</span>
      <span class="tag">HTML5</span>
      <span class="tag">CSS3</span>
      <span class="tag">R</span>
    </div>
  </div>

  <div class="stack-category">
    <div class="stack-category-title">// Framework &amp; Librerie</div>
    <div class="tags">
      <span class="tag highlight">Next.js</span>
      <span class="tag highlight">FastAPI</span>
      <span class="tag highlight">TailwindCSS</span>
      <span class="tag">.NET</span>
      <span class="tag">Node.js</span>
      <span class="tag">Express.js</span>
      <span class="tag">Flask</span>
      <span class="tag">Bootstrap</span>
      <span class="tag">Chart.js</span>
      <span class="tag">NumPy</span>
      <span class="tag">Pandas</span>
      <span class="tag">Plotly</span>
    </div>
  </div>

  <div class="stack-category" style="margin-bottom:2px">
    <div class="stack-category-title">// Database &amp; Cloud</div>
    <div class="tags">
      <span class="tag highlight">MongoDB</span>
      <span class="tag highlight">MySQL</span>
      <span class="tag">Redis</span>
      <span class="tag">Neo4J</span>
      <span class="tag">SQLite</span>
      <span class="tag">AWS</span>
      <span class="tag">Google Cloud</span>
      <span class="tag">Vercel</span>
    </div>
  </div>

  <!-- GITHUB STATS IMAGES -->
  <div class="github-images" style="margin-top:2px">
    <div class="gh-img-wrap">
      <img src="https://github-readme-stats.vercel.app/api?username=J0joFra&theme=dark&hide_border=true&include_all_commits=true&count_private=true&bg_color=0a0a0a&title_color=e8ff47&text_color=888888&icon_color=e8ff47" alt="GitHub Stats" loading="lazy"/>
    </div>
    <div class="gh-img-wrap">
      <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=J0joFra&theme=dark&hide_border=true&include_all_commits=true&count_private=true&layout=compact&bg_color=0a0a0a&title_color=e8ff47&text_color=888888" alt="Top Languages" loading="lazy"/>
    </div>
  </div>

  <div style="border:1px solid var(--border); padding:4px; margin-bottom:2px; animation: fadeUp 0.7s ease both;">
    <img src="https://nirzak-streak-stats.vercel.app/?user=J0joFra&theme=dark&hide_border=true&background=0a0a0a&stroke=1e1e1e&ring=e8ff47&fire=ff4747&currStreakLabel=e8ff47" style="width:100%;display:block;" alt="Streak Stats" loading="lazy"/>
  </div>

  <!-- QUOTE -->
  <div class="quote-card">
    <div class="quote-mark">"</div>
    <div class="quote-text">
      Il codice non è solo logica — è il modo in cui trasformiamo idee in realtà.
    </div>
  </div>

  <!-- DONATE -->
  <div class="donate-row">
    <a class="donate-btn" href="https://paypal.me/@JoaquimFrancalanci" target="_blank">
      <svg width="14" height="14" fill="currentColor" viewBox="0 0 24 24"><path d="M7.076 21.337H2.47a.641.641 0 0 1-.633-.74L4.944.901C5.026.382 5.474 0 5.998 0h7.46c2.57 0 4.578.543 5.69 1.81 1.01 1.15 1.304 2.42 1.012 4.287-.023.143-.047.291-.077.44l-.01.065v.045c-.12 3.162-2.17 5.345-5.956 5.345H11.3a.803.803 0 0 0-.795.679l-.85 5.384-.122.777a.64.64 0 0 1-.633.54H7.076z"/></svg>
      Dona via PayPal
    </a>
    <a class="donate-btn" href="https://ko-fi.com/joaquimfrancalanci" target="_blank">
      <svg width="14" height="14" fill="currentColor" viewBox="0 0 24 24"><path d="M23.881 8.948c-.773-4.085-4.859-4.593-4.859-4.593H.723c-.604 0-.679.798-.679.798s-.082 7.324-.022 11.822c.164 2.424 2.586 2.672 2.586 2.672s8.267-.023 11.966-.049c2.438-.426 2.683-2.566 2.658-3.734 4.352.24 7.422-2.831 6.649-6.916zm-11.062 3.511c-1.246 1.453-4.011 3.976-4.011 3.976s-.121.119-.31.023c-.076-.057-.108-.09-.108-.09-.443-.441-3.368-3.049-4.034-3.954-.317-.460-.476-.95-.476-1.395 0-1.233.958-2.224 2.138-2.224.799 0 1.346.374 1.738.858l.532.698.533-.698c.392-.484.939-.858 1.738-.858 1.18 0 2.138.991 2.138 2.224 0 .445-.159.935-.878 1.44z"/></svg>
      Dona via Ko‑fi
    </a>
  </div>

  <!-- FOOTER -->
  <div class="footer" style="margin-top:2px">
    <span>J0joFra &mdash; Cinisello Balsamo, Milano</span>
    <a href="https://formula-rossa.it" target="_blank">formula-rossa.it ↗</a>
  </div>

</div>
</body>
</html>
