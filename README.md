<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Vinusha Veeramalai — Software Developer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=IBM+Plex+Sans:wght@400;500;600&family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#0A1A17;
    --bg-alt:#0F2420;
    --surface:#143229;
    --surface-hi:#1A3D32;
    --copper:#D98E4A;
    --copper-bright:#F2A65A;
    --signal:#6FE8C2;
    --text:#EDEAE0;
    --text-muted:#8FA89F;
    --border:rgba(217,142,74,0.22);
    --border-soft:rgba(143,168,159,0.16);
    --display: 'Space Grotesk', sans-serif;
    --body: 'IBM Plex Sans', sans-serif;
    --mono: 'JetBrains Mono', monospace;
  }

  *{box-sizing:border-box; margin:0; padding:0;}

  html{scroll-behavior:smooth;}

  body{
    background:
      radial-gradient(ellipse 900px 500px at 15% -10%, rgba(217,142,74,0.08), transparent 60%),
      radial-gradient(ellipse 700px 500px at 100% 20%, rgba(111,232,194,0.05), transparent 55%),
      var(--bg);
    color:var(--text);
    font-family:var(--body);
    line-height:1.6;
    -webkit-font-smoothing:antialiased;
  }

  @media (prefers-reduced-motion: reduce){
    *{animation-duration:0.001ms !important; animation-iteration-count:1 !important; transition-duration:0.001ms !important; scroll-behavior:auto !important;}
  }

  a{color:inherit;}

  .wrap{
    max-width:920px;
    margin:0 auto;
    padding:0 28px;
  }

  /* ---------- micro components ---------- */

  .eyebrow{
    font-family:var(--mono);
    font-size:12px;
    letter-spacing:0.14em;
    text-transform:uppercase;
    color:var(--copper-bright);
    display:flex;
    align-items:center;
    gap:10px;
    margin-bottom:18px;
  }
  .eyebrow::before{
    content:"";
    width:7px; height:7px;
    border-radius:50%;
    background:var(--signal);
    box-shadow:0 0 8px 1px rgba(111,232,194,0.7);
    flex-shrink:0;
  }

  .designator{
    font-family:var(--mono);
    font-size:11px;
    letter-spacing:0.06em;
    color:var(--copper-bright);
    background:rgba(217,142,74,0.08);
    border:1px solid var(--border);
    border-radius:4px;
    padding:2px 7px;
    white-space:nowrap;
  }

  .section-head{
    display:flex;
    align-items:baseline;
    gap:14px;
    margin-bottom:34px;
  }
  .section-head h2{
    font-family:var(--display);
    font-weight:600;
    font-size:clamp(22px,3vw,28px);
    letter-spacing:-0.01em;
  }
  .section-head .designator{font-size:12px;}
  .section-head::after{
    content:"";
    flex:1;
    height:1px;
    background:linear-gradient(90deg, var(--border), transparent);
  }

  section{
    padding:74px 0;
    position:relative;
  }
  section + section{
    border-top:1px solid var(--border-soft);
  }

  /* ---------- hero ---------- */

  .hero{
    padding:88px 0 60px;
  }
  .hero h1{
    font-family:var(--display);
    font-weight:700;
    font-size:clamp(40px,7vw,68px);
    line-height:1.02;
    letter-spacing:-0.02em;
    color:var(--text);
  }
  .hero h1 span{
    color:var(--copper-bright);
  }
  .hero .role{
    font-family:var(--mono);
    font-size:clamp(14px,1.8vw,16px);
    color:var(--signal);
    margin-top:18px;
    letter-spacing:0.01em;
  }
  .hero .tagline{
    max-width:560px;
    margin-top:20px;
    font-size:16.5px;
    color:var(--text-muted);
  }
  .social-row{
    display:flex;
    gap:10px;
    margin-top:32px;
    flex-wrap:wrap;
  }
  .social-row .chip{
    font-family:var(--mono);
    font-size:13px;
    border:1px solid var(--border);
    border-radius:999px;
    padding:8px 16px;
    color:var(--text);
    background:rgba(217,142,74,0.05);
    transition:border-color .2s ease, background .2s ease;
  }
  .social-row .chip:hover{
    border-color:var(--copper-bright);
    background:rgba(217,142,74,0.12);
  }

  /* signal trace svg */
  .trace-wrap{
    margin-top:56px;
    height:64px;
  }
  .trace-wrap svg{width:100%; height:100%; display:block;}
  .trace-path{
    fill:none;
    stroke:var(--signal);
    stroke-width:1.6;
    stroke-linecap:round;
    filter:drop-shadow(0 0 6px rgba(111,232,194,0.45));
    stroke-dasharray:900;
    stroke-dashoffset:900;
    animation:draw 2.4s ease forwards .3s;
  }
  @keyframes draw{ to{ stroke-dashoffset:0; } }

  /* ---------- about ---------- */
  .about p{
    max-width:640px;
    font-size:16.5px;
    color:var(--text-muted);
  }
  .about p strong{color:var(--text); font-weight:500;}

  /* ---------- tech stack ---------- */
  .stack-group{
    margin-bottom:26px;
  }
  .stack-group:last-child{margin-bottom:0;}
  .stack-group .label{
    font-family:var(--mono);
    font-size:11.5px;
    color:var(--text-muted);
    letter-spacing:0.08em;
    text-transform:uppercase;
    margin-bottom:12px;
  }
  .pill-row{
    display:flex;
    flex-wrap:wrap;
    gap:8px;
  }
  .pill{
    font-family:var(--mono);
    font-size:13px;
    border:1px solid var(--border-soft);
    border-radius:6px;
    padding:7px 12px;
    background:var(--surface);
    color:var(--text);
  }

  /* ---------- projects (trace + nodes) ---------- */
  .proj-rail{
    position:relative;
    padding-left:34px;
  }
  .proj-rail::before{
    content:"";
    position:absolute;
    left:5px; top:8px; bottom:8px;
    width:1px;
    background:linear-gradient(var(--copper), var(--signal) 50%, var(--copper));
    opacity:0.35;
  }
  .proj{
    position:relative;
    padding-bottom:44px;
  }
  .proj:last-child{padding-bottom:0;}
  .proj::before{
    content:"";
    position:absolute;
    left:-34px; top:6px;
    width:11px; height:11px;
    border-radius:50%;
    background:var(--bg);
    border:2px solid var(--copper-bright);
  }
  .proj-top{
    display:flex;
    align-items:center;
    gap:12px;
    margin-bottom:8px;
    flex-wrap:wrap;
  }
  .proj h3{
    font-family:var(--display);
    font-weight:600;
    font-size:18.5px;
  }
  .proj p{
    color:var(--text-muted);
    font-size:14.5px;
    max-width:600px;
    margin-bottom:12px;
  }
  .tag-row{display:flex; flex-wrap:wrap; gap:6px;}
  .tag{
    font-family:var(--mono);
    font-size:11.5px;
    color:var(--text-muted);
    border:1px solid var(--border-soft);
    border-radius:4px;
    padding:3px 8px;
  }

  /* ---------- publications / certs ---------- */
  .pub-grid{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:18px;
  }
  .card{
    background:var(--surface);
    border:1px solid var(--border-soft);
    border-radius:10px;
    padding:20px;
  }
  .card .kicker{
    font-family:var(--mono);
    font-size:11px;
    color:var(--signal);
    letter-spacing:0.06em;
    margin-bottom:10px;
    display:block;
  }
  .card h4{
    font-family:var(--display);
    font-size:15.5px;
    font-weight:600;
    line-height:1.35;
    margin-bottom:8px;
  }
  .card .meta{
    font-size:13px;
    color:var(--text-muted);
  }

  .cert-list{
    display:flex;
    flex-direction:column;
    gap:10px;
    margin-top:28px;
  }
  .cert-row{
    display:flex;
    align-items:center;
    gap:14px;
    padding:13px 16px;
    background:var(--bg-alt);
    border:1px solid var(--border-soft);
    border-radius:8px;
    font-size:14px;
  }
  .cert-row .designator{flex-shrink:0;}

  /* ---------- experience timeline ---------- */
  .exp-item{
    display:grid;
    grid-template-columns:160px 1fr;
    gap:24px;
    padding:22px 0;
  }
  .exp-item + .exp-item{border-top:1px solid var(--border-soft);}
  .exp-date{
    font-family:var(--mono);
    font-size:12.5px;
    color:var(--copper-bright);
    white-space:nowrap;
  }
  .exp-role h4{
    font-family:var(--display);
    font-size:16.5px;
    font-weight:600;
    margin-bottom:4px;
  }
  .exp-role .org{
    font-size:13.5px;
    color:var(--text-muted);
    margin-bottom:10px;
    font-family:var(--mono);
  }
  .exp-role p{
    font-size:14.5px;
    color:var(--text-muted);
    max-width:520px;
  }

  /* ---------- activity ---------- */
  .activity-grid{
    display:grid;
    grid-template-columns:repeat(2, 1fr);
    gap:14px;
  }
  .stat-card{
    background:var(--surface);
    border:1px solid var(--border-soft);
    border-radius:10px;
    padding:18px 20px;
  }
  .stat-card .num{
    font-family:var(--display);
    font-size:30px;
    font-weight:700;
    color:var(--copper-bright);
  }
  .stat-card .lbl{
    font-family:var(--mono);
    font-size:12px;
    color:var(--text-muted);
    margin-top:4px;
  }
  .repo-list{
    margin-top:18px;
    display:flex;
    flex-wrap:wrap;
    gap:8px;
  }

  /* ---------- footer ---------- */
  footer{
    padding:50px 0 60px;
    text-align:center;
  }
  footer .role-line{
    font-family:var(--mono);
    font-size:13px;
    color:var(--signal);
    margin-bottom:10px;
  }
  footer .copy{
    font-size:12.5px;
    color:var(--text-muted);
  }

  @media (max-width:640px){
    .pub-grid{grid-template-columns:1fr;}
    .activity-grid{grid-template-columns:1fr;}
    .exp-item{grid-template-columns:1fr; gap:6px;}
    section{padding:54px 0;}
  }
</style>
</head>
<body>

<header class="hero wrap">
  <div class="eyebrow">PORTFOLIO — REV 2026.06</div>
  <h1>Vinusha <span>Veeramalai</span></h1>
  <div class="role">COMPUTER &amp; COMMUNICATION ENGINEERING — FINAL YEAR · SOFTWARE DEVELOPER</div>
  <p class="tagline">I build software that solves real problems — from banking workflows to safety navigation to AI-assisted operations — and I'm looking for a developer role where I can keep doing that.</p>
  <div class="social-row">
    <span class="chip">LinkedIn</span>
    <span class="chip">Email</span>
    <span class="chip">GitHub</span>
  </div>
  <div class="trace-wrap">
    <svg viewBox="0 0 880 64" preserveAspectRatio="none">
      <path class="trace-path" d="M0,32 L120,32 L150,10 L180,54 L210,10 L240,54 L270,32 L420,32 L450,18 L480,46 L510,32 L880,32" />
    </svg>
  </div>
</header>

<section class="about wrap">
  <div class="section-head"><span class="designator">ABOUT</span><h2>Who I am</h2></div>
  <p>I'm a final-year Computer &amp; Communication Engineering student who learns by shipping. <strong>Hands-on across the stack</strong> — from ATM-style transaction flows to safety-routing maps to a RAG-powered operations assistant — I'm driven by a strong pull toward learning, collaborating, and delivering things that work in the real world.</p>
</section>

<section class="wrap">
  <div class="section-head"><span class="designator">STACK</span><h2>Tech stack</h2></div>

  <div class="stack-group">
    <div class="label">Languages</div>
    <div class="pill-row">
      <span class="pill">Java</span><span class="pill">Python</span><span class="pill">JavaScript</span>
    </div>
  </div>
  <div class="stack-group">
    <div class="label">Web</div>
    <div class="pill-row">
      <span class="pill">HTML5</span><span class="pill">CSS3</span><span class="pill">React</span><span class="pill">Node.js</span>
    </div>
  </div>
  <div class="stack-group">
    <div class="label">Backend &amp; Frameworks</div>
    <div class="pill-row">
      <span class="pill">FastAPI</span><span class="pill">Django</span><span class="pill">Spring Boot</span>
    </div>
  </div>
  <div class="stack-group">
    <div class="label">Data</div>
    <div class="pill-row">
      <span class="pill">MySQL</span><span class="pill">MongoDB</span><span class="pill">SQLite</span>
    </div>
  </div>
  <div class="stack-group">
    <div class="label">Tooling</div>
    <div class="pill-row">
      <span class="pill">Git</span><span class="pill">VS Code</span>
    </div>
  </div>
</section>

<section class="wrap">
  <div class="section-head"><span class="designator">PROJECTS</span><h2>Things I've built</h2></div>

  <div class="proj-rail">

    <div class="proj">
      <div class="proj-top"><span class="designator">U1</span><h3>QR-Based Transaction Management System</h3></div>
      <p>Cardless cash withdrawal built around QR/UPI and PIN authentication, simulating a full 8-step ATM workflow with a fully responsive interface that mirrors real banking operations.</p>
      <div class="tag-row"><span class="tag">HTML</span><span class="tag">CSS</span><span class="tag">JavaScript</span><span class="tag">Django</span><span class="tag">SQLite</span><span class="tag">QR Integration</span></div>
    </div>

    <div class="proj">
      <div class="proj-top"><span class="designator">U2</span><h3>Multi-Language Code Translator — IDE Extension</h3></div>
      <p>A VS Code extension that translates code across languages, with a developer-friendly interface that cuts down manual rewriting when switching language environments.</p>
      <div class="tag-row"><span class="tag">JavaScript</span><span class="tag">HTML</span><span class="tag">CSS</span><span class="tag">VS Code Extension API</span></div>
    </div>

    <div class="proj">
      <div class="proj-top"><span class="designator">U3</span><h3>Smart Academic Overload &amp; Wellbeing Predictor</h3></div>
      <p>Predicts student burnout risk from personalized inputs, generates a customized 7-day study plan, and forecasts stress trends using linear regression on stored data.</p>
      <div class="tag-row"><span class="tag">Python</span><span class="tag">Pandas</span><span class="tag">Scikit-learn</span><span class="tag">Linear Regression</span><span class="tag">HTML</span><span class="tag">CSS</span></div>
    </div>

    <div class="proj">
      <div class="proj-top"><span class="designator">U4</span><h3>CapOps Agent</h3></div>
      <p>An intelligent BPO assistant for Capgemini's internal operations — resolves HR, Finance, and IT queries autonomously with RAG, live sentiment analysis, load balancing, and a real-time dashboard across web, voice, and email, escalating to humans when needed.</p>
      <div class="tag-row"><span class="tag">Python</span><span class="tag">FastAPI</span><span class="tag">LangChain</span><span class="tag">Claude API</span><span class="tag">ChromaDB</span><span class="tag">React</span><span class="tag">NGINX</span></div>
    </div>

    <div class="proj">
      <div class="proj-top"><span class="designator">U5</span><h3>FemRoute</h3></div>
      <p>An AI-powered safety navigation app for women — scores routes, shows color-coded risk segments on an interactive map, offers one-tap SOS, nearby help, ride-booking integration, and a 24/7 safety chatbot named Sakhi.</p>
      <div class="tag-row"><span class="tag">JavaScript</span><span class="tag">FastAPI</span><span class="tag">OpenRouteService API</span><span class="tag">Leaflet.js</span><span class="tag">HTML</span><span class="tag">CSS</span></div>
    </div>

    <div class="proj">
      <div class="proj-top"><span class="designator">U6</span><h3>BlockCred</h3></div>
      <p>A blockchain-based worker credential platform built for the OFFGRID 1.0 Hackathon, with 4-step OTP auth, face capture, a QR passport for banks and employers, a CIBIL score gauge, and AI-driven financial tips.</p>
      <div class="tag-row"><span class="tag">HTML</span><span class="tag">CSS</span><span class="tag">Vanilla JS</span></div>
    </div>

    <div class="proj">
      <div class="proj-top"><span class="designator">U7</span><h3>CivicFix</h3></div>
      <p>A crowdsourced civic issue reporting platform with AI-driven severity scoring, community upvoting, auto-escalation past ten votes, an interactive heatmap, and a gamified leaderboard, backed by a full municipal admin dashboard.</p>
      <div class="tag-row"><span class="tag">Java</span><span class="tag">Spring Boot</span><span class="tag">MongoDB</span><span class="tag">Leaflet.js</span><span class="tag">Thymeleaf</span><span class="tag">HTML</span><span class="tag">CSS</span></div>
    </div>

  </div>
</section>

<section class="wrap">
  <div class="section-head"><span class="designator">PUBLISH</span><h2>Publications &amp; achievements</h2></div>

  <div class="pub-grid">
    <div class="card">
      <span class="kicker">IEEE · APCIT-2025</span>
      <h4>Noise Reduction in Underwater Acoustic Signals Using Hybrid Wavelet Transform and GNN</h4>
      <div class="meta">Vidyavardhaka College of Engineering, Mysuru — Mar 2026</div>
    </div>
    <div class="card">
      <span class="kicker">IEEE · APCIT-2025</span>
      <h4>Multi-Agent Deep Reinforcement Learning-Based Adaptive Routing Strategy</h4>
      <div class="meta">Vidyavardhaka College of Engineering, Mysuru — Mar 2026</div>
    </div>
  </div>

  <div class="cert-list">
    <div class="cert-row"><span class="designator">CERT</span> NPTEL — Programming in Java (Elite + Gold, 88%)</div>
    <div class="cert-row"><span class="designator">CERT</span> Infosys Springboard — Python, Full Stack, Java, Data Science, IoT Foundation</div>
    <div class="cert-row"><span class="designator">CERT</span> Forage — Technology &amp; Cyber Security</div>
  </div>
</section>

<section class="wrap">
  <div class="section-head"><span class="designator">WORK</span><h2>Experience</h2></div>

  <div class="exp-item">
    <div class="exp-date">JUN – JUL 2025</div>
    <div class="exp-role">
      <h4>Full Stack Web Development Intern</h4>
      <div class="org">Mind View Technologies, Trichy</div>
      <p>Developed a responsive portfolio website and worked across the full development lifecycle, gaining hands-on front-end and back-end experience.</p>
    </div>
  </div>

  <div class="exp-item">
    <div class="exp-date">JUN – JUL 2024</div>
    <div class="exp-role">
      <h4>Web Development Intern</h4>
      <div class="org">Eduphoenix Private Limited, Bangalore</div>
      <p>Built static websites with HTML &amp; CSS, strengthening semantic markup, web structure, and responsive design fundamentals.</p>
    </div>
  </div>
</section>

<section class="wrap">
  <div class="section-head"><span class="designator">ACTIVITY</span><h2>On GitHub</h2></div>
  <div class="activity-grid">
    <div class="stat-card">
      <div class="num">47</div>
      <div class="lbl">CONTRIBUTIONS — LAST 12 MONTHS</div>
    </div>
    <div class="stat-card">
      <div class="num">6</div>
      <div class="lbl">ACTIVE REPOSITORIES</div>
    </div>
  </div>
  <div class="repo-list">
    <span class="pill">Java-Tech-Stack</span>
    <span class="pill">ShamirSecret</span>
    <span class="pill">Geeks-for-Geeks-problems</span>
    <span class="pill">CivicFix</span>
    <span class="pill">CapOps-Agent</span>
    <span class="pill">FemRoute</span>
  </div>
</section>

<footer class="wrap">
  <div class="role-line">OPEN TO SOFTWARE DEVELOPER ROLES</div>
  <div class="copy">© 2026 Vinusha Veeramalai</div>
</footer>

</body>
</html>
