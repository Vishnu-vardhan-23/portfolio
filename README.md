
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Vishnu Vardhan G — ECE Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #050810;
    --bg2: #080c18;
    --card: #0b1020;
    --border: #161e32;
    --purple: #7c6fff;
    --purple-dim: #5c50cc;
    --purple-glow: rgba(124,111,255,0.15);
    --green: #39e8a0;
    --text: #ccd6f6;
    --text-muted: #5a6a8a;
    --white: #e8f0ff;
    --mono: 'Space Mono', monospace;
    --sans: 'Space Grotesk', sans-serif;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--sans);
    overflow-x: hidden;
  }

  /* STAR FIELD */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      radial-gradient(1px 1px at 10% 20%, rgba(124,111,255,0.4) 0%, transparent 100%),
      radial-gradient(1px 1px at 30% 60%, rgba(57,232,160,0.3) 0%, transparent 100%),
      radial-gradient(1px 1px at 55% 15%, rgba(255,255,255,0.3) 0%, transparent 100%),
      radial-gradient(1px 1px at 75% 40%, rgba(124,111,255,0.3) 0%, transparent 100%),
      radial-gradient(1px 1px at 90% 75%, rgba(57,232,160,0.2) 0%, transparent 100%),
      radial-gradient(1px 1px at 20% 80%, rgba(255,255,255,0.2) 0%, transparent 100%),
      radial-gradient(1px 1px at 65% 90%, rgba(124,111,255,0.25) 0%, transparent 100%);
    pointer-events: none;
    z-index: 0;
  }

  /* GLOW ORB */
  body::after {
    content: '';
    position: fixed;
    top: -20%;
    right: -10%;
    width: 600px;
    height: 600px;
    background: radial-gradient(circle, rgba(124,111,255,0.08) 0%, transparent 70%);
    pointer-events: none;
    z-index: 0;
  }

  section, nav, footer { position: relative; z-index: 1; }

  /* NAV */
  nav {
    position: fixed;
    top: 0; left: 0; right: 0;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1.2rem 4rem;
    background: rgba(5,8,16,0.8);
    backdrop-filter: blur(16px);
    border-bottom: 1px solid var(--border);
    z-index: 100;
  }

  .nav-logo {
    font-family: var(--mono);
    font-size: 0.85rem;
    color: var(--purple);
    letter-spacing: 0.08em;
  }

  nav ul { list-style: none; display: flex; gap: 2.5rem; }

  nav a {
    font-family: var(--mono);
    font-size: 0.75rem;
    color: var(--text-muted);
    text-decoration: none;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    transition: color 0.2s;
  }

  nav a:hover { color: var(--purple); }

  /* HERO */
  #hero {
    min-height: 100vh;
    display: flex;
    align-items: center;
    padding: 7rem 4rem 4rem;
  }

  .hero-inner {
    max-width: 1100px;
    margin: 0 auto;
    width: 100%;
    display: grid;
    grid-template-columns: 1.1fr 0.9fr;
    gap: 5rem;
    align-items: center;
  }

  .hero-eyebrow {
    font-family: var(--mono);
    font-size: 0.72rem;
    color: var(--green);
    letter-spacing: 0.25em;
    text-transform: uppercase;
    margin-bottom: 1.2rem;
    display: flex;
    align-items: center;
    gap: 0.8rem;
  }

  .hero-eyebrow::before {
    content: '';
    width: 24px;
    height: 1px;
    background: var(--green);
  }

  h1 {
    font-size: clamp(3rem, 5.5vw, 4.8rem);
    font-weight: 700;
    line-height: 1.0;
    letter-spacing: -0.03em;
    color: var(--white);
    margin-bottom: 1.2rem;
  }

  h1 em {
    font-style: normal;
    background: linear-gradient(135deg, var(--purple) 0%, var(--green) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-desc {
    font-size: 0.95rem;
    color: var(--text-muted);
    line-height: 1.8;
    max-width: 440px;
    margin-bottom: 2.5rem;
    font-weight: 300;
  }

  .hero-btns { display: flex; gap: 1rem; flex-wrap: wrap; }

  .btn {
    font-family: var(--mono);
    font-size: 0.75rem;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    text-decoration: none;
    padding: 0.9rem 2rem;
    border-radius: 2px;
    transition: all 0.25s;
    cursor: pointer;
    border: none;
  }

  .btn-primary {
    background: var(--purple);
    color: #fff;
    box-shadow: 0 0 24px rgba(124,111,255,0.35);
  }

  .btn-primary:hover {
    background: #9488ff;
    box-shadow: 0 0 32px rgba(124,111,255,0.5);
    transform: translateY(-2px);
  }

  .btn-outline {
    background: transparent;
    border: 1px solid var(--border);
    color: var(--text-muted);
  }

  .btn-outline:hover {
    border-color: var(--purple);
    color: var(--purple);
    transform: translateY(-2px);
  }

  /* HERO CARD */
  .hero-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 2rem;
    position: relative;
    overflow: hidden;
  }

  .hero-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--purple), transparent);
  }

  .card-header {
    font-family: var(--mono);
    font-size: 0.65rem;
    color: var(--text-muted);
    letter-spacing: 0.2em;
    text-transform: uppercase;
    margin-bottom: 1.5rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

  .online-dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--green);
    animation: blink 2s infinite;
  }

  @keyframes blink {
    0%,100% { opacity: 1; }
    50% { opacity: 0.2; }
  }

  .info-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0.8rem 0;
    border-bottom: 1px solid var(--border);
    gap: 1rem;
  }

  .info-row:last-child { border-bottom: none; }

  .info-key {
    font-family: var(--mono);
    font-size: 0.68rem;
    color: var(--text-muted);
    letter-spacing: 0.1em;
    text-transform: uppercase;
    white-space: nowrap;
  }

  .info-val {
    font-family: var(--mono);
    font-size: 0.8rem;
    color: var(--text);
    text-align: right;
  }

  .info-val.purple { color: var(--purple); }
  .info-val.green { color: var(--green); }

  /* SECTIONS */
  .section {
    padding: 6rem 4rem;
    max-width: 1100px;
    margin: 0 auto;
  }

  .section-full {
    padding: 6rem 0;
    background: var(--bg2);
    position: relative;
    z-index: 1;
  }

  .section-full .inner {
    max-width: 1100px;
    margin: 0 auto;
    padding: 0 4rem;
  }

  .sec-label {
    font-family: var(--mono);
    font-size: 0.68rem;
    color: var(--purple);
    letter-spacing: 0.25em;
    text-transform: uppercase;
    margin-bottom: 0.5rem;
  }

  h2 {
    font-size: clamp(1.8rem, 3vw, 2.4rem);
    font-weight: 700;
    color: var(--white);
    letter-spacing: -0.02em;
    margin-bottom: 3rem;
  }

  /* SKILLS */
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.2rem;
  }

  .skill-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 1.6rem;
    transition: all 0.3s;
    position: relative;
    overflow: hidden;
  }

  .skill-card::after {
    content: '';
    position: absolute;
    inset: 0;
    background: var(--purple-glow);
    opacity: 0;
    transition: opacity 0.3s;
    border-radius: 10px;
  }

  .skill-card:hover { border-color: rgba(124,111,255,0.4); transform: translateY(-4px); }
  .skill-card:hover::after { opacity: 1; }

  .skill-icon {
    font-size: 1.4rem;
    margin-bottom: 0.8rem;
    line-height: 1;
  }

  .skill-title {
    font-weight: 600;
    font-size: 0.9rem;
    color: var(--white);
    margin-bottom: 0.6rem;
    position: relative;
    z-index: 1;
  }

  .skill-items {
    font-family: var(--mono);
    font-size: 0.7rem;
    color: var(--text-muted);
    line-height: 2;
    position: relative;
    z-index: 1;
  }

  /* PROJECTS */
  .projects-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.2rem;
  }

  .proj-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 2rem 1.8rem;
    transition: all 0.3s;
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .proj-card:hover {
    border-color: rgba(124,111,255,0.35);
    transform: translateY(-5px);
    box-shadow: 0 20px 40px rgba(0,0,0,0.4);
  }

  .proj-number {
    font-family: var(--mono);
    font-size: 0.65rem;
    color: var(--purple);
    letter-spacing: 0.15em;
  }

  .proj-title {
    font-weight: 700;
    font-size: 1rem;
    color: var(--white);
    line-height: 1.4;
  }

  .proj-desc {
    font-size: 0.83rem;
    color: var(--text-muted);
    line-height: 1.7;
    flex: 1;
  }

  .proj-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 0.4rem;
  }

  .tag {
    font-family: var(--mono);
    font-size: 0.62rem;
    padding: 0.25rem 0.6rem;
    background: rgba(124,111,255,0.08);
    border: 1px solid rgba(124,111,255,0.2);
    color: #a89fff;
    border-radius: 3px;
    letter-spacing: 0.05em;
  }

  /* EDUCATION */
  .edu-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1.5rem;
  }

  .edu-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 2rem;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s;
  }

  .edu-card::before {
    content: '';
    position: absolute;
    left: 0; top: 0; bottom: 0;
    width: 3px;
    background: linear-gradient(180deg, var(--purple), var(--green));
    border-radius: 3px 0 0 3px;
  }

  .edu-card:hover { border-color: rgba(124,111,255,0.3); }

  .edu-period {
    font-family: var(--mono);
    font-size: 0.68rem;
    color: var(--purple);
    letter-spacing: 0.1em;
    margin-bottom: 0.5rem;
  }

  .edu-degree {
    font-weight: 700;
    font-size: 1rem;
    color: var(--white);
    margin-bottom: 0.3rem;
  }

  .edu-school {
    font-size: 0.85rem;
    color: var(--text-muted);
    margin-bottom: 0.8rem;
  }

  .edu-score {
    display: inline-block;
    font-family: var(--mono);
    font-size: 0.72rem;
    color: var(--green);
    background: rgba(57,232,160,0.08);
    border: 1px solid rgba(57,232,160,0.2);
    padding: 0.2rem 0.7rem;
    border-radius: 3px;
  }

  /* CONTACT */
  .contact-wrap {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 4rem;
    align-items: start;
  }

  .contact-text {
    font-size: 0.95rem;
    color: var(--text-muted);
    line-height: 1.8;
    margin-bottom: 2rem;
  }

  .contact-links { display: flex; flex-direction: column; gap: 0.8rem; }

  .clink {
    display: flex;
    align-items: center;
    gap: 1rem;
    padding: 1rem 1.2rem;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 8px;
    text-decoration: none;
    transition: all 0.25s;
  }

  .clink:hover {
    border-color: rgba(124,111,255,0.35);
    transform: translateX(4px);
  }

  .clink-icon {
    font-family: var(--mono);
    font-size: 1rem;
    color: var(--purple);
    width: 1.5rem;
    text-align: center;
  }

  .clink-body { flex: 1; }

  .clink-label {
    font-family: var(--mono);
    font-size: 0.62rem;
    color: var(--text-muted);
    letter-spacing: 0.15em;
    text-transform: uppercase;
  }

  .clink-val {
    font-size: 0.85rem;
    color: var(--text);
    margin-top: 0.1rem;
  }

  .clink-arr {
    font-size: 0.75rem;
    color: var(--text-muted);
    transition: all 0.2s;
  }

  .clink:hover .clink-arr { color: var(--purple); transform: translateX(3px); }

  /* FOOTER */
  footer {
    border-top: 1px solid var(--border);
    padding: 2rem 4rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: relative;
    z-index: 1;
  }

  .footer-txt {
    font-family: var(--mono);
    font-size: 0.68rem;
    color: var(--text-muted);
    letter-spacing: 0.08em;
  }

  .footer-txt span { color: var(--purple); }

  /* ANIMATIONS */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .hero-inner > * { animation: fadeUp 0.7s ease both; }
  .hero-inner > *:nth-child(2) { animation-delay: 0.12s; }

  /* RESPONSIVE */
  @media (max-width: 768px) {
    nav { padding: 1rem 1.5rem; }
    nav ul { gap: 1.2rem; }
    .section, .section-full .inner { padding: 4rem 1.5rem; }
    .hero-inner { grid-template-columns: 1fr; gap: 2.5rem; padding: 0; }
    #hero { padding: 7rem 1.5rem 4rem; }
    .skills-grid, .projects-grid, .edu-grid, .contact-wrap { grid-template-columns: 1fr; }
    footer { flex-direction: column; gap: 0.8rem; text-align: center; padding: 1.5rem; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">VV.ECE</div>
  <ul>
    <li><a href="#about">About</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#education">Education</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="about" style="padding:0; max-width:100%;">
  <div id="hero">
    <div class="hero-inner">
      <div>
        <div class="hero-eyebrow">ECE Student · Anna University</div>
        <h1>VISHNU<br>VARDHAN <em>G</em></h1>
        <p class="hero-desc">
          Motivated Electronics & Communication Engineer with a passion for core electronics, PCB design, and IoT technologies. Quick learner with strong analytical skills and a drive to apply technical knowledge to real-world engineering problems.
        </p>
        <div class="hero-btns">
          <a href="#projects" class="btn btn-primary">View Projects</a>
          <a href="tel:9342878538" class="btn btn-outline">Get In Touch</a>
        </div>
      </div>

      <div class="hero-card">
        <div class="card-header">
          <span>// Profile Status</span>
          <div class="online-dot"></div>
        </div>
        <div class="info-row">
          <span class="info-key">Status</span>
          <span class="info-val green">Available</span>
        </div>
        <div class="info-row">
          <span class="info-key">Location</span>
          <span class="info-val">Tamil Nadu, IN</span>
        </div>
        <div class="info-row">
          <span class="info-key">Programme</span>
          <span class="info-val">B.E. ECE · 2023–2027</span>
        </div>
        <div class="info-row">
          <span class="info-key">CGPA</span>
          <span class="info-val purple">6.52</span>
        </div>
        <div class="info-row">
          <span class="info-key">Focus</span>
          <span class="info-val">IoT · PCB · Embedded</span>
        </div>
        <div class="info-row">
          <span class="info-key">Languages</span>
          <span class="info-val">English · Tamil</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- SKILLS -->
<div class="section-full" id="skills">
  <div class="inner">
    <div class="sec-label">01 — Capabilities</div>
    <h2>Skills & Tools</h2>
    <div class="skills-grid">

      <div class="skill-card">
        <div class="skill-icon">💻</div>
        <div class="skill-title">Programming</div>
        <div class="skill-items">C<br>C++<br>Python (Basic)</div>
      </div>

      <div class="skill-card">
        <div class="skill-icon">⚙️</div>
        <div class="skill-title">Embedded & IoT</div>
        <div class="skill-items">Arduino IDE<br>ESP32<br>Microcontrollers</div>
      </div>

      <div class="skill-card">
        <div class="skill-icon">🔌</div>
        <div class="skill-title">Electronics</div>
        <div class="skill-items">Digital Electronics<br>Basic Circuit Design<br>Basic PCB Design</div>
      </div>

      <div class="skill-card">
        <div class="skill-icon">🛠️</div>
        <div class="skill-title">EDA Tools</div>
        <div class="skill-items">LT Spice<br>Keil<br>Tinkercad</div>
      </div>

      <div class="skill-card">
        <div class="skill-icon">🤝</div>
        <div class="skill-title">Dev & Collab</div>
        <div class="skill-items">GitHub<br>MS Office Suite<br>Documentation</div>
      </div>

      <div class="skill-card">
        <div class="skill-icon">🧠</div>
        <div class="skill-title">Core Concepts</div>
        <div class="skill-items">Analog & Digital Circuits<br>Signal Processing<br>Sensor Integration</div>
      </div>

    </div>
  </div>
</div>

<!-- PROJECTS -->
<section class="section" id="projects">
  <div class="sec-label">02 — Work</div>
  <h2>Projects</h2>
  <div class="projects-grid">

    <div class="proj-card">
      <div class="proj-number">// PROJ-01</div>
      <div class="proj-title">Mobile Network Jammer using 555 Timer IC</div>
      <p class="proj-desc">
        Designed a mobile signal jamming circuit using the versatile 555 Timer IC. Demonstrates core analog electronics principles including oscillator design and RF interference fundamentals.
      </p>
      <div class="proj-tags">
        <span class="tag">555 Timer IC</span>
        <span class="tag">Analog Circuits</span>
        <span class="tag">RF</span>
        <span class="tag">LT Spice</span>
      </div>
    </div>

    <div class="proj-card">
      <div class="proj-number">// PROJ-02</div>
      <div class="proj-title">Gas Leak Detection System</div>
      <p class="proj-desc">
        Built an IoT-based safety system that detects hazardous gas leaks using gas sensors and triggers real-time alerts. Integrates embedded programming with hardware sensor interfacing.
      </p>
      <div class="proj-tags">
        <span class="tag">Arduino</span>
        <span class="tag">Gas Sensor</span>
        <span class="tag">IoT</span>
        <span class="tag">ESP32</span>
        <span class="tag">C</span>
      </div>
    </div>

    <div class="proj-card">
      <div class="proj-number">// PROJ-03</div>
      <div class="proj-title">Air Quality Prediction using ML</div>
      <p class="proj-desc">
        Developed a machine learning model to predict air quality index based on sensor data. Combines Python-based ML techniques with real-world environmental data for predictive analysis.
      </p>
      <div class="proj-tags">
        <span class="tag">Python</span>
        <span class="tag">Machine Learning</span>
        <span class="tag">Data Analysis</span>
        <span class="tag">Sensors</span>
      </div>
    </div>

  </div>
</section>

<!-- EDUCATION -->
<div class="section-full" id="education">
  <div class="inner">
    <div class="sec-label">03 — Background</div>
    <h2>Education</h2>
    <div class="edu-grid">

      <div class="edu-card">
        <div class="edu-period">09/2023 — 05/2027</div>
        <div class="edu-degree">B.E. Electronics & Communication Engineering</div>
        <div class="edu-school">Anna University, Coimbatore, India</div>
        <span class="edu-score">CGPA: 6.52</span>
      </div>

      <div class="edu-card">
        <div class="edu-period">06/2022 — 05/2023</div>
        <div class="edu-degree">Higher Secondary Certificate (HSC)</div>
        <div class="edu-school">SVGV MHSS, Karamadai, Coimbatore</div>
        <span class="edu-score">Percentage: 79%</span>
      </div>

    </div>
  </div>
</div>

<!-- CONTACT -->
<section class="section" id="contact">
  <div class="sec-label">04 — Connect</div>
  <h2>Get In Touch</h2>
  <div class="contact-wrap">
    <div>
      <p class="contact-text">
        Currently a second-year ECE student at Anna University, open to internship opportunities, collaborative projects, and hands-on learning in embedded systems, IoT, and PCB design.
      </p>
      <a href="#projects" class="btn btn-primary">See My Work</a>
    </div>
    <div class="contact-links">
      <a href="tel:9342878538" class="clink">
        <span class="clink-icon">✆</span>
        <div class="clink-body">
          <div class="clink-label">Phone</div>
          <div class="clink-val">+91 9342878538</div>
        </div>
        <span class="clink-arr">→</span>
      </a>
      <a href="#" class="clink">
        <span class="clink-icon">⌥</span>
        <div class="clink-body">
          <div class="clink-label">GitHub</div>
          <div class="clink-val">github.com/VishnuVardhan</div>
        </div>
        <span class="clink-arr">→</span>
      </a>
      <a href="#" class="clink">
        <span class="clink-icon">in</span>
        <div class="clink-body">
          <div class="clink-label">LinkedIn</div>
          <div class="clink-val">linkedin.com/in/VishnuVardhan</div>
        </div>
        <span class="clink-arr">→</span>
      </a>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-txt">© 2025 <span>VISHNU VARDHAN G</span> · ECE Engineer</div>
  <div class="footer-txt">Tamil Nadu, <span>India</span></div>
</footer>

</body>
</html>
