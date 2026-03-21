<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Sandesh Shingankar – GitHub Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Mono:wght@300;400;500&display=swap" rel="stylesheet"/>
<style>
  :root {
    --bg: #0a0c10;
    --surface: #0f1218;
    --card: #131720;
    --border: #1e2530;
    --accent: #00e5a0;
    --accent2: #00aaff;
    --accent3: #ff6b6b;
    --text: #e8edf5;
    --muted: #6b7a8d;
    --font-head: 'Syne', sans-serif;
    --font-mono: 'DM Mono', monospace;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--font-mono);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Animated grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(0,229,160,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,229,160,0.03) 1px, transparent 1px);
    background-size: 40px 40px;
    pointer-events: none;
    z-index: 0;
  }

  .wrapper {
    max-width: 860px;
    margin: 0 auto;
    padding: 48px 24px 80px;
    position: relative;
    z-index: 1;
  }

  /* ── HERO ── */
  .hero {
    text-align: center;
    padding: 60px 0 40px;
    position: relative;
  }

  .hero::after {
    content: '';
    display: block;
    width: 200px;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--accent), transparent);
    margin: 40px auto 0;
  }

  .hero-label {
    font-family: var(--font-mono);
    font-size: 11px;
    letter-spacing: 4px;
    color: var(--accent);
    text-transform: uppercase;
    margin-bottom: 18px;
    opacity: 0;
    animation: fadeUp 0.5s ease forwards 0.1s;
  }

  .hero h1 {
    font-family: var(--font-head);
    font-size: clamp(2.4rem, 6vw, 3.8rem);
    font-weight: 800;
    line-height: 1.1;
    letter-spacing: -1px;
    opacity: 0;
    animation: fadeUp 0.6s ease forwards 0.2s;
  }

  .hero h1 .name-highlight {
    background: linear-gradient(135deg, var(--accent) 0%, var(--accent2) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-sub {
    font-family: var(--font-mono);
    font-size: 13px;
    color: var(--muted);
    margin-top: 14px;
    letter-spacing: 1px;
    opacity: 0;
    animation: fadeUp 0.6s ease forwards 0.35s;
  }

  .hero-tags {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 10px;
    margin-top: 28px;
    opacity: 0;
    animation: fadeUp 0.6s ease forwards 0.45s;
  }

  .tag {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 5px 14px;
    font-size: 11px;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    color: var(--muted);
    transition: all 0.2s;
  }
  .tag:hover { border-color: var(--accent); color: var(--accent); }

  .links {
    display: flex;
    justify-content: center;
    gap: 16px;
    margin-top: 32px;
    opacity: 0;
    animation: fadeUp 0.6s ease forwards 0.55s;
  }

  .link-btn {
    display: flex;
    align-items: center;
    gap: 8px;
    padding: 10px 22px;
    border-radius: 6px;
    font-family: var(--font-mono);
    font-size: 12px;
    letter-spacing: 1px;
    text-decoration: none;
    transition: all 0.2s;
    border: 1px solid;
  }

  .link-btn.li {
    border-color: var(--accent2);
    color: var(--accent2);
    background: rgba(0,170,255,0.06);
  }
  .link-btn.li:hover { background: rgba(0,170,255,0.15); box-shadow: 0 0 16px rgba(0,170,255,0.2); }

  .link-btn.gm {
    border-color: var(--accent3);
    color: var(--accent3);
    background: rgba(255,107,107,0.06);
  }
  .link-btn.gm:hover { background: rgba(255,107,107,0.15); box-shadow: 0 0 16px rgba(255,107,107,0.2); }

  /* ── SECTION ── */
  .section {
    margin-top: 64px;
    opacity: 0;
    animation: fadeUp 0.6s ease forwards 0.6s;
  }

  .section-header {
    display: flex;
    align-items: center;
    gap: 14px;
    margin-bottom: 28px;
  }

  .section-num {
    font-size: 10px;
    color: var(--accent);
    letter-spacing: 2px;
    font-family: var(--font-mono);
  }

  .section-title {
    font-family: var(--font-head);
    font-size: 1.3rem;
    font-weight: 700;
    letter-spacing: -0.3px;
  }

  .section-line {
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  /* ── ABOUT GRID ── */
  .about-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 14px;
  }

  .about-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 20px;
    transition: all 0.25s;
    position: relative;
    overflow: hidden;
  }

  .about-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent2));
    transform: scaleX(0);
    transform-origin: left;
    transition: transform 0.3s;
  }

  .about-card:hover { border-color: rgba(0,229,160,0.2); transform: translateY(-2px); }
  .about-card:hover::before { transform: scaleX(1); }

  .about-card .icon { font-size: 1.4rem; margin-bottom: 10px; }
  .about-card .card-title { font-family: var(--font-head); font-size: 13px; font-weight: 600; margin-bottom: 4px; }
  .about-card .card-desc { font-size: 11px; color: var(--muted); line-height: 1.6; }

  /* ── SKILLS GRID ── */
  .skills-category { margin-bottom: 32px; }

  .cat-label {
    font-size: 10px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 14px;
    font-family: var(--font-mono);
  }

  .skills-row {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }

  .skill-pill {
    display: flex;
    align-items: center;
    gap: 7px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 6px;
    padding: 8px 14px;
    font-size: 12px;
    font-family: var(--font-mono);
    color: var(--text);
    transition: all 0.2s;
    cursor: default;
  }

  .skill-pill:hover {
    border-color: var(--accent);
    color: var(--accent);
    background: rgba(0,229,160,0.05);
    transform: translateY(-1px);
  }

  .skill-dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--accent);
    flex-shrink: 0;
  }
  .skill-dot.blue { background: var(--accent2); }
  .skill-dot.red  { background: var(--accent3); }
  .skill-dot.yellow { background: #f5c842; }

  /* ── CURRENTLY WORKING ── */
  .work-list {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
    gap: 14px;
  }

  .work-item {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 18px 20px;
    display: flex;
    flex-direction: column;
    gap: 8px;
    transition: all 0.25s;
  }

  .work-item:hover { border-color: rgba(0,170,255,0.3); transform: translateY(-2px); }

  .work-icon { font-size: 1.3rem; }
  .work-title { font-family: var(--font-head); font-size: 13px; font-weight: 600; }
  .work-desc { font-size: 11px; color: var(--muted); line-height: 1.5; }

  /* ── TERMINAL QUOTE ── */
  .terminal {
    background: #08090d;
    border: 1px solid var(--border);
    border-radius: 10px;
    overflow: hidden;
    margin-top: 64px;
    opacity: 0;
    animation: fadeUp 0.6s ease forwards 0.7s;
  }

  .terminal-bar {
    background: var(--card);
    border-bottom: 1px solid var(--border);
    padding: 10px 16px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .dot-r { width: 11px; height: 11px; border-radius: 50%; background: #ff5f57; }
  .dot-y { width: 11px; height: 11px; border-radius: 50%; background: #ffbd2e; }
  .dot-g { width: 11px; height: 11px; border-radius: 50%; background: #28ca40; }
  .terminal-title { font-size: 11px; color: var(--muted); margin-left: 8px; letter-spacing: 1px; }

  .terminal-body {
    padding: 20px 24px;
    font-size: 13px;
    line-height: 1.8;
  }

  .t-prompt { color: var(--accent); }
  .t-cmd    { color: var(--accent2); }
  .t-out    { color: var(--text); opacity: 0.85; }
  .t-cursor { display: inline-block; width: 8px; height: 14px; background: var(--accent); animation: blink 1s step-end infinite; vertical-align: middle; }

  /* ── GOAL BANNER ── */
  .goal-banner {
    margin-top: 64px;
    background: linear-gradient(135deg, rgba(0,229,160,0.06) 0%, rgba(0,170,255,0.06) 100%);
    border: 1px solid rgba(0,229,160,0.15);
    border-radius: 12px;
    padding: 36px;
    text-align: center;
    opacity: 0;
    animation: fadeUp 0.6s ease forwards 0.8s;
  }

  .goal-banner p {
    font-family: var(--font-head);
    font-size: clamp(1rem, 2.5vw, 1.25rem);
    font-weight: 600;
    line-height: 1.7;
    color: var(--text);
  }

  .goal-banner p span { color: var(--accent); }

  /* ── FOOTER ── */
  .footer {
    margin-top: 64px;
    text-align: center;
    font-size: 11px;
    color: var(--muted);
    letter-spacing: 2px;
    text-transform: uppercase;
    opacity: 0;
    animation: fadeUp 0.5s ease forwards 0.9s;
  }

  /* ── KEYFRAMES ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(16px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  @keyframes blink {
    0%, 100% { opacity: 1; }
    50%       { opacity: 0; }
  }

  /* stagger children of each section */
  .section:nth-child(2) { animation-delay: 0.65s; }
  .section:nth-child(3) { animation-delay: 0.70s; }
  .section:nth-child(4) { animation-delay: 0.75s; }
</style>
</head>
<body>
<div class="wrapper">

  <!-- HERO -->
  <header class="hero">
    <p class="hero-label">// portfolio readme</p>
    <h1>Hi, I'm <span class="name-highlight">Sandesh</span><br/>Shingankar</h1>
    <p class="hero-sub">B.E. Information Technology &nbsp;·&nbsp; Nashik, India</p>

    <div class="hero-tags">
      <span class="tag">UI/UX Design</span>
      <span class="tag">Data Science</span>
      <span class="tag">Web Dev</span>
      <span class="tag">App Dev</span>
      <span class="tag">Machine Learning</span>
    </div>

    <div class="links">
      <a href="https://www.linkedin.com/in/sandeshs-shingankar" class="link-btn li" target="_blank">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6zM2 9h4v12H2z"/><circle cx="4" cy="4" r="2"/></svg>
        LinkedIn
      </a>
      <a href="mailto:sandeshshingankar8@gmail.com" class="link-btn gm">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="2" y="4" width="20" height="16" rx="2"/><polyline points="2,4 12,13 22,4"/></svg>
        Email
      </a>
    </div>
  </header>

  <!-- ABOUT -->
  <section class="section">
    <div class="section-header">
      <span class="section-num">01</span>
      <h2 class="section-title">About Me</h2>
      <div class="section-line"></div>
    </div>

    <div class="about-grid">
      <div class="about-card">
        <div class="icon">🎓</div>
        <div class="card-title">B.E. IT Student</div>
        <div class="card-desc">Currently pursuing Information Technology engineering</div>
      </div>
      <div class="about-card">
        <div class="icon">📊</div>
        <div class="card-title">Data Science</div>
        <div class="card-desc">Exploring ML & analytics with Python</div>
      </div>
      <div class="about-card">
        <div class="icon">🌐</div>
        <div class="card-title">Web Dev</div>
        <div class="card-desc">Building modern full-stack applications</div>
      </div>
      <div class="about-card">
        <div class="icon">📱</div>
        <div class="card-title">App Dev</div>
        <div class="card-desc">Cross-platform mobile applications</div>
      </div>
    </div>
  </section>

  <!-- TECH STACK -->
  <section class="section">
    <div class="section-header">
      <span class="section-num">02</span>
      <h2 class="section-title">Tech Stack</h2>
      <div class="section-line"></div>
    </div>

    <div class="skills-category">
      <div class="cat-label">// languages</div>
      <div class="skills-row">
        <div class="skill-pill"><span class="skill-dot yellow"></span>Python</div>
        <div class="skill-pill"><span class="skill-dot yellow"></span>JavaScript</div>
        <div class="skill-pill"><span class="skill-dot blue"></span>Kotlin</div>
        <div class="skill-pill"><span class="skill-dot blue"></span>Java</div>
      </div>
    </div>

    <div class="skills-category">
      <div class="cat-label">// web development</div>
      <div class="skills-row">
        <div class="skill-pill"><span class="skill-dot red"></span>HTML5</div>
        <div class="skill-pill"><span class="skill-dot blue"></span>CSS3</div>
        <div class="skill-pill"><span class="skill-dot blue"></span>React</div>
        <div class="skill-pill"><span class="skill-dot"></span>Next.js</div>
        <div class="skill-pill"><span class="skill-dot blue"></span>Tailwind CSS</div>
        <div class="skill-pill"><span class="skill-dot"></span>Express.js</div>
      </div>
    </div>

    <div class="skills-category">
      <div class="cat-label">// data science & ml</div>
      <div class="skills-row">
        <div class="skill-pill"><span class="skill-dot"></span>NumPy</div>
        <div class="skill-pill"><span class="skill-dot"></span>Pandas</div>
        <div class="skill-pill"><span class="skill-dot red"></span>Scikit-learn</div>
        <div class="skill-pill"><span class="skill-dot blue"></span>Matplotlib</div>
        <div class="skill-pill"><span class="skill-dot blue"></span>Seaborn</div>
      </div>
    </div>
  </section>

  <!-- CURRENTLY WORKING ON -->
  <section class="section">
    <div class="section-header">
      <span class="section-num">03</span>
      <h2 class="section-title">Currently Working On</h2>
      <div class="section-line"></div>
    </div>

    <div class="work-list">
      <div class="work-item">
        <span class="work-icon">📊</span>
        <span class="work-title">Data Science Projects</span>
        <span class="work-desc">Python-based analysis & ML models</span>
      </div>
      <div class="work-item">
        <span class="work-icon">🌐</span>
        <span class="work-title">Full-Stack Web Apps</span>
        <span class="work-desc">End-to-end web applications</span>
      </div>
      <div class="work-item">
        <span class="work-icon">📱</span>
        <span class="work-title">Mobile Apps</span>
        <span class="work-desc">Cross-platform mobile development</span>
      </div>
      <div class="work-item">
        <span class="work-icon">🧪</span>
        <span class="work-title">DSA & CS Fundamentals</span>
        <span class="work-desc">Core problem-solving skills</span>
      </div>
    </div>
  </section>

  <!-- TERMINAL QUOTE -->
  <div class="terminal">
    <div class="terminal-bar">
      <span class="dot-r"></span>
      <span class="dot-y"></span>
      <span class="dot-g"></span>
      <span class="terminal-title">sandesh@dev ~ philosophy.sh</span>
    </div>
    <div class="terminal-body">
      <div><span class="t-prompt">$ </span><span class="t-cmd">cat</span> philosophy.txt</div>
      <div class="t-out">&nbsp;</div>
      <div class="t-out">&nbsp;&nbsp;"Learning by doing, improving with consistency."</div>
      <div class="t-out">&nbsp;</div>
      <div><span class="t-prompt">$ </span><span class="t-cursor"></span></div>
    </div>
  </div>

  <!-- CAREER GOAL -->
  <div class="goal-banner">
    <p>
      🎯 Goal: Become an <span>industry-ready software developer</span> by mastering<br/>
      Data Science, Web Development &amp; App Development —<br/>
      and contribute to <span>impactful, real-world products</span>.
    </p>
  </div>

  <!-- FOOTER -->
  <footer class="footer">
    <p>⭐ &nbsp; Thanks for visiting · Let's connect &amp; build something great &nbsp; 🤝</p>
  </footer>

</div>
</body>
</html>
