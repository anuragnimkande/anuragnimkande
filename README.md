<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Anurag Nimkande — Software Engineer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600;700;800&family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">
<style>
/* ============ TOKENS ============ */
:root{
  --bg:#0a0e14;
  --bg-1:#0d131c;
  --panel:#111823;
  --panel-2:#141d29;
  --border:#212c3a;
  --border-soft:#1a2432;
  --text:#e7edf5;
  --text-dim:#93a1b5;
  --text-faint:#5b6b82;
  --cyan:#5eead4;
  --amber:#fbbf6a;
  --magenta:#d9a7f0;
  --blue:#7dd3fc;
  --green:#8be28f;
  --mono:'JetBrains Mono', ui-monospace, monospace;
  --sans:'Inter', system-ui, sans-serif;
  --shadow-glow: 0 0 40px rgba(94,234,212,0.08);
}

*{margin:0;padding:0;box-sizing:border-box;}
html{scroll-behavior:smooth;}
body{
  background:
    radial-gradient(1200px 600px at 15% -10%, rgba(94,234,212,0.06), transparent 60%),
    radial-gradient(1000px 500px at 90% 10%, rgba(217,167,240,0.05), transparent 55%),
    var(--bg);
  color:var(--text);
  font-family:var(--sans);
  line-height:1.6;
  overflow-x:hidden;
  -webkit-font-smoothing:antialiased;
}

::selection{background:rgba(94,234,212,0.25); color:#fff;}
::-webkit-scrollbar{width:10px;}
::-webkit-scrollbar-track{background:var(--bg);}
::-webkit-scrollbar-thumb{background:var(--border); border-radius:6px;}
::-webkit-scrollbar-thumb:hover{background:var(--text-faint);}

a{color:inherit; text-decoration:none;}
ul{list-style:none;}
img{max-width:100%; display:block;}

.wrap{max-width:1140px; margin:0 auto; padding:0 28px;}
.mono{font-family:var(--mono);}
.grad-text{
  background:linear-gradient(90deg,var(--cyan),var(--blue) 45%,var(--magenta));
  -webkit-background-clip:text; background-clip:text; color:transparent;
}
.eyebrow{
  font-family:var(--mono); font-size:12.5px; letter-spacing:.14em; text-transform:uppercase;
  color:var(--cyan); display:flex; align-items:center; gap:10px; margin-bottom:14px;
}
.eyebrow::before{content:''; width:18px; height:1px; background:var(--cyan); opacity:.6;}
h1,h2,h3{font-family:var(--mono); font-weight:700; letter-spacing:-0.01em; color:var(--text);}
.section{padding:120px 0;}
.section-head{max-width:640px; margin-bottom:56px;}
.section-title{font-size:clamp(26px,3.4vw,38px); line-height:1.15;}
.section-sub{color:var(--text-dim); margin-top:14px; font-size:15.5px; max-width:560px;}

/* ============ REVEAL ============ */
[data-reveal]{
  opacity:0; transform:translateY(26px);
  transition:opacity .7s cubic-bezier(.16,.8,.24,1), transform .7s cubic-bezier(.16,.8,.24,1);
}
[data-reveal].in-view{opacity:1; transform:translateY(0);}
@media (prefers-reduced-motion: reduce){
  *{animation-duration:.001ms !important; animation-iteration-count:1 !important; transition-duration:.001ms !important; scroll-behavior:auto !important;}
  [data-reveal]{opacity:1 !important; transform:none !important;}
}

/* ============ NAV ============ */
nav{
  position:fixed; top:0; left:0; right:0; z-index:100;
  backdrop-filter:blur(14px) saturate(140%);
  background:rgba(10,14,20,0.72);
  border-bottom:1px solid var(--border-soft);
}
.nav-inner{display:flex; align-items:center; justify-content:space-between; height:64px;}
.logo{font-family:var(--mono); font-weight:700; font-size:15px; display:flex; align-items:center; gap:8px;}
.logo .bracket{color:var(--cyan);}
.nav-links{display:flex; gap:6px; align-items:center;}
.nav-links a{
  font-family:var(--mono); font-size:13px; color:var(--text-dim); padding:8px 14px; border-radius:7px;
  transition:color .2s ease, background .2s ease;
}
.nav-links a:hover{color:var(--text); background:rgba(255,255,255,0.04);}
.nav-links a .num{color:var(--text-faint); margin-right:6px;}
.nav-cta{
  font-family:var(--mono); font-size:12.5px; padding:9px 16px; border-radius:7px;
  border:1px solid var(--cyan); color:var(--cyan); transition:all .25s ease;
}
.nav-cta:hover{background:rgba(94,234,212,0.1); box-shadow:0 0 22px rgba(94,234,212,0.25);}
.nav-toggle{display:none; flex-direction:column; gap:5px; cursor:pointer; background:none; border:none;}
.nav-toggle span{width:22px; height:2px; background:var(--text); border-radius:2px; transition:.3s;}

/* ============ HERO ============ */
.hero{min-height:100vh; display:flex; align-items:center; padding-top:64px; position:relative;}
.hero-grid{
  position:absolute; inset:0; z-index:0; opacity:.5;
  background-image:
    linear-gradient(rgba(94,234,212,0.045) 1px, transparent 1px),
    linear-gradient(90deg, rgba(94,234,212,0.045) 1px, transparent 1px);
  background-size:44px 44px;
  mask-image:radial-gradient(ellipse 70% 50% at 50% 30%, black 10%, transparent 75%);
}
.hero-inner{position:relative; z-index:1; display:grid; grid-template-columns:1.1fr .9fr; gap:56px; align-items:center; width:100%;}
.hero-tag{
  display:inline-flex; align-items:center; gap:8px; font-family:var(--mono); font-size:12.5px;
  color:var(--green); border:1px solid rgba(139,226,143,0.3); background:rgba(139,226,143,0.06);
  padding:6px 12px; border-radius:20px; margin-bottom:22px;
}
.dot-live{width:7px; height:7px; border-radius:50%; background:var(--green); animation:pulse-dot 2s infinite;}
@keyframes pulse-dot{
  0%{box-shadow:0 0 0 0 rgba(139,226,143,0.55);}
  70%{box-shadow:0 0 0 8px rgba(139,226,143,0);}
  100%{box-shadow:0 0 0 0 rgba(139,226,143,0);}
}
.hero h1{font-size:clamp(34px,5vw,56px); line-height:1.08; letter-spacing:-0.02em;}
.hero-role{font-family:var(--mono); color:var(--text-dim); font-size:17px; margin-top:16px; min-height:26px;}
.cursor-blink{display:inline-block; width:9px; height:19px; background:var(--cyan); margin-left:2px; vertical-align:-3px; animation:blink 1s step-end infinite;}
@keyframes blink{50%{opacity:0;}}
.hero-desc{color:var(--text-dim); font-size:15.5px; margin-top:22px; max-width:480px;}
.hero-btns{display:flex; gap:14px; margin-top:34px; flex-wrap:wrap;}
.btn{
  font-family:var(--mono); font-size:13.5px; padding:13px 22px; border-radius:8px; font-weight:500;
  display:inline-flex; align-items:center; gap:8px; transition:all .25s cubic-bezier(.2,.8,.3,1);
  cursor:pointer; border:1px solid transparent;
}
.btn-primary{background:var(--cyan); color:#04201c;}
.btn-primary:hover{transform:translateY(-2px); box-shadow:0 10px 30px -8px rgba(94,234,212,0.5);}
.btn-ghost{border-color:var(--border); color:var(--text);}
.btn-ghost:hover{border-color:var(--text-faint); background:rgba(255,255,255,0.03); transform:translateY(-2px);}

.terminal{
  background:var(--panel); border:1px solid var(--border); border-radius:12px; overflow:hidden;
  box-shadow:0 30px 80px -30px rgba(0,0,0,0.6), var(--shadow-glow);
}
.terminal-bar{display:flex; align-items:center; gap:8px; padding:12px 14px; border-bottom:1px solid var(--border); background:var(--panel-2);}
.tdot{width:11px; height:11px; border-radius:50%;}
.tdot.r{background:#ff5f56;} .tdot.y{background:#ffbd2e;} .tdot.g{background:#27c93f;}
.terminal-title{margin-left:auto; margin-right:auto; font-family:var(--mono); font-size:11.5px; color:var(--text-faint);}
.terminal-body{padding:20px 20px 24px; font-family:var(--mono); font-size:13px; color:var(--text-dim); min-height:230px;}
.terminal-body .line{margin-bottom:9px; white-space:pre-wrap;}
.prompt{color:var(--cyan);}
.prompt2{color:var(--magenta);}
.tval{color:var(--text);}
.tkey{color:var(--blue);}
.tstr{color:var(--amber);}
#typedOut{color:var(--text);}

/* ============ STATS ============ */
.stats-strip{border-top:1px solid var(--border-soft); border-bottom:1px solid var(--border-soft); background:var(--bg-1);}
.stats-grid{display:grid; grid-template-columns:repeat(4,1fr);}
.stat-cell{padding:38px 24px; text-align:center; border-right:1px solid var(--border-soft);}
.stat-cell:last-child{border-right:none;}
.stat-num{font-family:var(--mono); font-size:clamp(26px,3vw,38px); font-weight:700;}
.stat-label{color:var(--text-faint); font-size:12.5px; margin-top:6px; font-family:var(--mono); letter-spacing:.04em;}

/* ============ ABOUT ============ */
.about-grid{display:grid; grid-template-columns:1fr 1fr; gap:64px; align-items:start;}
.about-text p{color:var(--text-dim); font-size:15.5px; margin-bottom:16px;}
.about-text strong{color:var(--text); font-weight:600;}
.focus-list{margin-top:26px; display:flex; flex-direction:column; gap:12px;}
.focus-item{display:flex; align-items:center; gap:12px; font-family:var(--mono); font-size:13.5px; color:var(--text-dim);}
.focus-item .ic{color:var(--cyan);}

.code-card{background:var(--panel); border:1px solid var(--border); border-radius:12px; overflow:hidden;}
.code-lines{padding:18px 0; font-family:var(--mono); font-size:12.8px; line-height:1.85;}
.code-line{display:flex; padding:0 18px;}
.ln{width:26px; color:var(--text-faint); user-select:none; flex-shrink:0;}
.code-content{white-space:pre;}
.c-kw{color:var(--magenta);} .c-str{color:var(--amber);} .c-fn{color:var(--blue);} .c-com{color:var(--text-faint); font-style:italic;} .c-prop{color:var(--cyan);}

/* ============ SKILLS ============ */
.skills-grid{display:grid; grid-template-columns:repeat(2,1fr); gap:40px 56px;}
.skill-group-title{font-family:var(--mono); font-size:12.5px; color:var(--text-faint); text-transform:uppercase; letter-spacing:.1em; margin-bottom:14px;}
.chip-cloud{display:flex; flex-wrap:wrap; gap:9px; margin-bottom:26px;}
.chip{
  font-family:var(--mono); font-size:12px; padding:7px 12px; border-radius:20px; border:1px solid var(--border);
  color:var(--text-dim); transition:all .2s ease; cursor:default;
}
.chip:hover{border-color:var(--cyan); color:var(--cyan); background:rgba(94,234,212,0.06); transform:translateY(-2px);}

/* ============ TIMELINE (verified dates only) ============ */
.gitlog{position:relative; padding-left:28px;}
.gitlog::before{content:''; position:absolute; left:5px; top:6px; bottom:6px; width:1px; background:linear-gradient(var(--border), var(--border) 90%, transparent);}
.commit{position:relative; padding-bottom:34px;}
.commit:last-child{padding-bottom:0;}
.commit::before{
  content:''; position:absolute; left:-28px; top:4px; width:11px; height:11px; border-radius:50%;
  background:var(--bg); border:2px solid var(--cyan); box-shadow:0 0 0 4px var(--bg);
}
.commit-head{display:flex; align-items:center; gap:10px; flex-wrap:wrap; font-family:var(--mono); font-size:12.5px;}
.commit-branch{color:var(--text-faint); background:var(--panel-2); border:1px solid var(--border-soft); padding:2px 8px; border-radius:12px; font-size:11px;}
.commit-date{color:var(--text-faint); margin-left:auto;}
.commit-msg{font-weight:600; margin-top:8px; font-size:15px;}
.commit-body{color:var(--text-dim); font-size:13.5px; margin-top:6px;}
.commit-tags{display:flex; gap:8px; margin-top:10px; flex-wrap:wrap;}
.commit-tags span{font-family:var(--mono); font-size:11px; color:var(--blue); background:rgba(125,211,252,0.08); border:1px solid rgba(125,211,252,0.2); padding:3px 9px; border-radius:5px;}

/* ============ PROJECTS ============ */
.projects-grid{display:grid; grid-template-columns:repeat(2,1fr); gap:22px;}
.pcard{
  background:var(--panel); border:1px solid var(--border); border-radius:12px; overflow:hidden;
  transition:transform .35s cubic-bezier(.16,.8,.24,1), border-color .35s ease, box-shadow .35s ease;
  display:flex; flex-direction:column;
}
.pcard:hover{transform:translateY(-6px); border-color:rgba(94,234,212,0.35); box-shadow:0 24px 50px -20px rgba(0,0,0,0.55), 0 0 30px -10px rgba(94,234,212,0.15);}
.pcard-top{padding:12px 16px; display:flex; align-items:center; gap:8px; border-bottom:1px solid var(--border); background:var(--panel-2);}
.pcard-top .fname{margin-left:6px; font-family:var(--mono); font-size:11.5px; color:var(--text-faint);}
.pcard-domain{margin-left:auto; font-family:var(--mono); font-size:10.5px; color:var(--cyan); border:1px solid rgba(94,234,212,0.25); padding:2px 8px; border-radius:10px;}
.pcard-body{padding:20px 20px 22px; flex:1; display:flex; flex-direction:column;}
.pcard-body h3{font-size:16.5px; margin-bottom:10px;}
.pcard-body p{color:var(--text-dim); font-size:13.8px; margin-bottom:16px; flex:1;}
.pcard-stack{display:flex; flex-wrap:wrap; gap:7px;}
.pcard-stack span{font-family:var(--mono); font-size:10.8px; color:var(--text-dim); border:1px solid var(--border-soft); padding:4px 9px; border-radius:5px; background:var(--panel-2);}

/* ============ AWARDS ============ */
.awards-grid{display:grid; grid-template-columns:repeat(2,1fr); gap:18px;}
.award-card{background:var(--panel); border:1px solid var(--border); border-radius:12px; padding:22px; display:flex; gap:16px; transition:border-color .3s ease, transform .3s ease;}
.award-card:hover{border-color:rgba(251,191,106,0.35); transform:translateY(-3px);}
.award-ic{font-size:22px; flex-shrink:0;}
.award-card h4{font-size:14.5px; margin-bottom:5px;}
.award-card p{color:var(--text-dim); font-size:13px;}
.award-card a{color:var(--cyan); font-family:var(--mono); font-size:12px;}

/* ============ CONTACT ============ */
.contact-panel{
  background:linear-gradient(135deg, var(--panel), var(--panel-2));
  border:1px solid var(--border); border-radius:16px; padding:56px; text-align:center; position:relative; overflow:hidden;
}
.contact-panel::before{
  content:''; position:absolute; inset:0; background:radial-gradient(500px 260px at 50% 0%, rgba(94,234,212,0.09), transparent 70%);
}
.contact-panel > *{position:relative; z-index:1;}
.contact-panel h2{font-size:clamp(24px,3.2vw,34px);}
.contact-panel p{color:var(--text-dim); margin-top:14px; max-width:460px; margin-left:auto; margin-right:auto;}
.contact-btns{display:flex; gap:14px; justify-content:center; margin-top:30px; flex-wrap:wrap;}

footer{border-top:1px solid var(--border-soft); padding:34px 0; color:var(--text-faint); font-family:var(--mono); font-size:12.5px;}
.footer-inner{display:flex; justify-content:space-between; align-items:center; flex-wrap:wrap; gap:12px;}
.footer-links{display:flex; gap:18px;}
.footer-links a:hover{color:var(--cyan);}

/* ============ RESPONSIVE ============ */
@media (max-width:900px){
  .hero-inner{grid-template-columns:1fr;}
  .about-grid{grid-template-columns:1fr; gap:44px;}
  .skills-grid{grid-template-columns:1fr;}
  .projects-grid{grid-template-columns:1fr;}
  .awards-grid{grid-template-columns:1fr;}
  .stats-grid{grid-template-columns:repeat(2,1fr);}
  .stat-cell:nth-child(2){border-right:none;}
  .stat-cell{border-bottom:1px solid var(--border-soft);}
}
@media (max-width:720px){
  .nav-links{position:fixed; top:64px; left:0; right:0; background:var(--bg-1); border-bottom:1px solid var(--border); flex-direction:column; align-items:stretch; padding:10px; gap:2px; transform:translateY(-130%); opacity:0; transition:.3s ease; pointer-events:none;}
  .nav-links.open{transform:translateY(0); opacity:1; pointer-events:auto;}
  .nav-cta{display:none;}
  .nav-toggle{display:flex;}
  .section{padding:80px 0;}
}
</style>
</head>
<body>

<!-- ============ NAV ============ -->
<nav>
  <div class="wrap nav-inner">
    <div class="logo"><span class="bracket">&lt;</span>Anurag.dev<span class="bracket">/&gt;</span></div>
    <ul class="nav-links" id="navLinks">
      <li><a href="#about"><span class="num">01.</span>About</a></li>
      <li><a href="#skills"><span class="num">02.</span>Skills</a></li>
      <li><a href="#timeline"><span class="num">03.</span>Timeline</a></li>
      <li><a href="#projects"><span class="num">04.</span>Projects</a></li>
      <li><a href="#awards"><span class="num">05.</span>Awards</a></li>
    </ul>
    <a href="#contact" class="nav-cta">./connect</a>
    <button class="nav-toggle" id="navToggle" aria-label="Toggle menu"><span></span><span></span><span></span></button>
  </div>
</nav>

<!-- ============ HERO ============ -->
<header class="hero">
  <div class="hero-grid"></div>
  <div class="wrap hero-inner">
    <div>
      <div class="hero-tag"><span class="dot-live"></span> open to opportunities</div>
      <h1>Anurag Nimkande</h1>
      <div class="hero-role mono">&gt; <span id="roleTyped"></span><span class="cursor-blink"></span></div>
      <p class="hero-desc">B.Tech Computer Engineering student at Vishwakarma Institute of Technology, Pune (CGPA 9.22). I work comfortably with C++, Java, Python, and full-stack web development, building scalable, database-driven applications that are secure and user-friendly.</p>
      <div class="hero-btns">
        <a href="#projects" class="btn btn-primary">View Projects →</a>
        <a href="mailto:anurag.nimkande@gmail.com" class="btn btn-ghost">Say Hello</a>
      </div>
    </div>

    <div class="terminal" data-reveal>
      <div class="terminal-bar">
        <span class="tdot r"></span><span class="tdot y"></span><span class="tdot g"></span>
        <span class="terminal-title">anurag@vit-pune: ~</span>
      </div>
      <div class="terminal-body">
        <div class="line"><span class="prompt">$</span> <span class="tval">whoami</span></div>
        <div class="line" style="color:var(--text-faint)">anurag-nimkande</div>
        <div class="line"><span class="prompt">$</span> <span class="tval">cat profile.json</span></div>
        <div class="line">{</div>
        <div class="line">&nbsp;&nbsp;<span class="tkey">"institute"</span>: <span class="tstr">"VIT, Pune"</span>,</div>
        <div class="line">&nbsp;&nbsp;<span class="tkey">"cgpa"</span>: <span class="tval">9.22</span>,</div>
        <div class="line">&nbsp;&nbsp;<span class="tkey">"languages"</span>: [<span class="tstr">"C++"</span>, <span class="tstr">"Java"</span>, <span class="tstr">"Python"</span>],</div>
        <div class="line">&nbsp;&nbsp;<span class="tkey">"dsa_solved"</span>: <span class="tstr">"250+"</span>,</div>
        <div class="line">&nbsp;&nbsp;<span class="tkey">"location"</span>: <span class="tstr">"Pune, India"</span></div>
        <div class="line">}</div>
        <div class="line"><span class="prompt2">$</span> <span id="typedOut"></span><span class="cursor-blink" id="termCursor"></span></div>
      </div>
    </div>
  </div>
</header>

<!-- ============ STATS STRIP ============ -->
<section class="stats-strip">
  <div class="wrap stats-grid">
    <div class="stat-cell" data-reveal>
      <div class="stat-num grad-text"><span class="counter" data-target="250">0</span>+</div>
      <div class="stat-label">DSA PROBLEMS SOLVED</div>
    </div>
    <div class="stat-cell" data-reveal>
      <div class="stat-num grad-text"><span class="counter" data-target="7">0</span></div>
      <div class="stat-label">PROJECTS BUILT</div>
    </div>
    <div class="stat-cell" data-reveal>
      <div class="stat-num grad-text">9.22</div>
      <div class="stat-label">CGPA / 10</div>
    </div>
    <div class="stat-cell" data-reveal>
      <div class="stat-num grad-text"><span class="counter" data-target="1">0</span></div>
      <div class="stat-label">IEEE PAPER PUBLISHED</div>
    </div>
  </div>
</section>

<!-- ============ ABOUT ============ -->
<section class="section" id="about">
  <div class="wrap">
    <div class="section-head" data-reveal>
      <div class="eyebrow">01 // about</div>
      <h2 class="section-title">Turning ideas into working, scalable systems</h2>
    </div>
    <div class="about-grid">
      <div class="about-text" data-reveal>
        <p>I am a <strong>B.Tech Computer Engineering student</strong> at Vishwakarma Institute of Technology, Pune, passionate about turning ideas into real, working solutions. I work comfortably with <strong>C++, Java, Python</strong>, and full-stack web development, and I enjoy building scalable, database-driven applications that are secure and user-friendly.</p>
        <p>I thrive in problem-solving, love collaborating with teams, and consistently seek creative solutions to tackle real-world challenges — across full-stack systems, applied machine learning, and healthcare & decision-support platforms.</p>
        <div class="focus-list">
          <div class="focus-item"><span class="ic">▹</span> Full-stack web development (Django, React, Node.js)</div>
          <div class="focus-item"><span class="ic">▹</span> Applied machine learning & predictive analytics</div>
          <div class="focus-item"><span class="ic">▹</span> Healthcare & decision-support systems</div>
          <div class="focus-item"><span class="ic">▹</span> Hybrid quantum-classical machine learning (exploratory research)</div>
          <div class="focus-item"><span class="ic">▹</span> Clean architecture, documentation, and reproducible results</div>
        </div>
      </div>

      <div class="code-card" data-reveal>
        <div class="terminal-bar">
          <span class="tdot r"></span><span class="tdot y"></span><span class="tdot g"></span>
          <span class="terminal-title">education.py</span>
        </div>
        <div class="code-lines">
          <div class="code-line"><span class="ln">1</span><span class="code-content"><span class="c-kw">class</span> <span class="c-fn">Education</span>:</span></div>
          <div class="code-line"><span class="ln">2</span><span class="code-content">    <span class="c-prop">degree</span> = <span class="c-str">"B.Tech, Computer Engineering"</span></span></div>
          <div class="code-line"><span class="ln">3</span><span class="code-content">    <span class="c-prop">institute</span> = <span class="c-str">"VIT, Pune"</span></span></div>
          <div class="code-line"><span class="ln">4</span><span class="code-content">    <span class="c-prop">cgpa</span> = <span class="c-str">9.22</span></span></div>
          <div class="code-line"><span class="ln">5</span><span class="code-content"></span></div>
          <div class="code-line"><span class="ln">6</span><span class="code-content">    <span class="c-com"># prior qualification</span></span></div>
          <div class="code-line"><span class="ln">7</span><span class="code-content">    <span class="c-prop">diploma</span> = <span class="c-str">"Govt. Polytechnic, Amravati"</span></span></div>
          <div class="code-line"><span class="ln">8</span><span class="code-content">    <span class="c-prop">diploma_score</span> = <span class="c-str">"94.5%"</span> <span class="c-com"># 2024</span></span></div>
          <div class="code-line"><span class="ln">9</span><span class="code-content"></span></div>
          <div class="code-line"><span class="ln">10</span><span class="code-content">    <span class="c-kw">def</span> <span class="c-fn">internship</span>(<span class="c-prop">self</span>):</span></div>
          <div class="code-line"><span class="ln">11</span><span class="code-content">        <span class="c-kw">return</span> <span class="c-str">"Sun Infotech — Jun–Jul 2023"</span></span></div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ============ SKILLS ============ -->
<section class="section" id="skills" style="background:var(--bg-1); border-top:1px solid var(--border-soft); border-bottom:1px solid var(--border-soft);">
  <div class="wrap">
    <div class="section-head" data-reveal>
      <div class="eyebrow">02 // stack</div>
      <h2 class="section-title">Technical toolkit</h2>
    </div>

    <div class="skills-grid">
      <div data-reveal>
        <div class="skill-group-title">Programming Languages</div>
        <div class="chip-cloud">
          <span class="chip">C++</span><span class="chip">Java</span><span class="chip">Python</span><span class="chip">JavaScript</span>
        </div>
        <div class="skill-group-title">Frameworks</div>
        <div class="chip-cloud">
          <span class="chip">Django</span><span class="chip">Servlet</span><span class="chip">Flask</span>
        </div>
        <div class="skill-group-title">Web Technologies</div>
        <div class="chip-cloud">
          <span class="chip">HTML</span><span class="chip">CSS</span><span class="chip">JavaScript</span>
        </div>
      </div>

      <div data-reveal>
        <div class="skill-group-title">Databases & Tools</div>
        <div class="chip-cloud">
          <span class="chip">MySQL</span><span class="chip">MongoDB</span><span class="chip">Git</span><span class="chip">GitHub</span><span class="chip">VS Code</span>
        </div>
        <div class="skill-group-title">Soft Skills</div>
        <div class="chip-cloud">
          <span class="chip">Problem Solving</span><span class="chip">Attention to Detail</span><span class="chip">Team Collaboration</span><span class="chip">Logical Reasoning</span>
        </div>
        <div class="skill-group-title">Certification</div>
        <div class="chip-cloud">
          <span class="chip">IBM Full Stack Software Developer</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ============ TIMELINE ============ -->
<section class="section" id="timeline">
  <div class="wrap">
    <div class="section-head" data-reveal>
      <div class="eyebrow">03 // timeline</div>
      <h2 class="section-title">Education & experience</h2>
    </div>

    <div class="gitlog">
      <div class="commit" data-reveal>
        <div class="commit-head"><span class="commit-branch">education</span><span class="commit-date">2024</span></div>
        <div class="commit-msg">Diploma in Computer Engineering</div>
        <div class="commit-body">Government Polytechnic, Amravati — 94.5%</div>
      </div>
      <div class="commit" data-reveal>
        <div class="commit-head"><span class="commit-branch">internship</span><span class="commit-date">Jun 2023 – Jul 2023</span></div>
        <div class="commit-msg">Industrial Training — Sun Infotech, Amravati</div>
        <div class="commit-body">Developed a blood bank management system using Java Servlets and MySQL. Designed inventory tracking and donor search features, and gained hands-on backend and relational database experience.</div>
        <div class="commit-tags"><span>Java Servlets</span><span>MySQL</span></div>
      </div>
      <div class="commit" data-reveal>
        <div class="commit-head"><span class="commit-branch">education</span></div>
        <div class="commit-msg">B.Tech in Computer Engineering — VIT, Pune</div>
        <div class="commit-body">Currently pursuing, CGPA: 9.22</div>
      </div>
    </div>
  </div>
</section>

<!-- ============ PROJECTS ============ -->
<section class="section" id="projects" style="background:var(--bg-1); border-top:1px solid var(--border-soft); border-bottom:1px solid var(--border-soft);">
  <div class="wrap">
    <div class="section-head" data-reveal>
      <div class="eyebrow">04 // projects</div>
      <h2 class="section-title">Selected work</h2>
    </div>

    <div class="projects-grid">
      <div class="pcard" data-reveal>
        <div class="pcard-top"><span class="tdot r"></span><span class="tdot y"></span><span class="tdot g"></span><span class="fname">alumni_domain</span><span class="pcard-domain">Enterprise Web Apps</span></div>
        <div class="pcard-body">
          <h3>Alumni Information Domain</h3>
          <p>Full-stack alumni management platform to collect, organize, and analyze alumni data. Implemented authentication, profile management, event posting, job sharing, and networking features with RESTful endpoints.</p>
          <div class="pcard-stack"><span>HTML</span><span>CSS</span><span>JavaScript</span><span>Django</span><span>MongoDB</span></div>
        </div>
      </div>

      <div class="pcard" data-reveal>
        <div class="pcard-top"><span class="tdot r"></span><span class="tdot y"></span><span class="tdot g"></span><span class="fname">ipfs_drive</span><span class="pcard-domain">Decentralized Storage</span></div>
        <div class="pcard-body">
          <h3>Personal Drive — Secure File Storage on IPFS</h3>
          <p>Decentralized personal storage system leveraging IPFS for distributed file hosting, with secure upload, retrieval, hash-based file tracking, and Django-backed authentication and metadata management.</p>
          <div class="pcard-stack"><span>HTML</span><span>CSS</span><span>JavaScript</span><span>Django</span><span>IPFS</span></div>
        </div>
      </div>

      <div class="pcard" data-reveal>
        <div class="pcard-top"><span class="tdot r"></span><span class="tdot y"></span><span class="tdot g"></span><span class="fname">safeher_app</span><span class="pcard-domain">Safety Tech</span></div>
        <div class="pcard-body">
          <h3>SafeHer: AI-Driven Women Safety</h3>
          <p>AI-powered safety monitoring system with real-time emergency alert generation. React-based dashboard for live location tracking, GPS API integration for risk detection, and a Node.js backend connecting ML models for threat prediction.</p>
          <div class="pcard-stack"><span>React.js</span><span>Node.js</span><span>Python (ML)</span><span>GPS APIs</span></div>
        </div>
      </div>

      <div class="pcard" data-reveal>
        <div class="pcard-top"><span class="tdot r"></span><span class="tdot y"></span><span class="tdot g"></span><span class="fname">hospital_mgmt</span><span class="pcard-domain">Healthcare Systems</span></div>
        <div class="pcard-body">
          <h3>Hospital Management System</h3>
          <p>Django platform with ML-based patient readmission and risk prediction.</p>
          <div class="pcard-stack"><span>Django</span><span>Machine Learning</span></div>
        </div>
      </div>

      <div class="pcard" data-reveal>
        <div class="pcard-top"><span class="tdot r"></span><span class="tdot y"></span><span class="tdot g"></span><span class="fname">depression_predictor</span><span class="pcard-domain">Mental Health AI</span></div>
        <div class="pcard-body">
          <h3>Depression Prediction System</h3>
          <p>Machine learning models built using clinical and survey datasets.</p>
          <div class="pcard-stack"><span>Python</span><span>Machine Learning</span></div>
        </div>
      </div>

      <div class="pcard" data-reveal>
        <div class="pcard-top"><span class="tdot r"></span><span class="tdot y"></span><span class="tdot g"></span><span class="fname">code_analyzer</span><span class="pcard-domain">Developer Tools</span></div>
        <div class="pcard-body">
          <h3>AI Code Analyzer</h3>
          <p>Intelligent code analysis tool built with the Gemini API, a Flask backend, and a Tailwind front end.</p>
          <div class="pcard-stack"><span>Flask</span><span>Gemini API</span><span>Tailwind</span></div>
        </div>
      </div>

      <div class="pcard" data-reveal>
        <div class="pcard-top"><span class="tdot r"></span><span class="tdot y"></span><span class="tdot g"></span><span class="fname">quantum_ml</span><span class="pcard-domain">Quantum Computing</span></div>
        <div class="pcard-body">
          <h3>Hybrid Quantum–Classical ML</h3>
          <p>Exploratory research on quantum-enhanced learning models.</p>
          <div class="pcard-stack"><span>Quantum Computing</span><span>Machine Learning</span></div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ============ AWARDS ============ -->
<section class="section" id="awards">
  <div class="wrap">
    <div class="section-head" data-reveal>
      <div class="eyebrow">05 // recognition</div>
      <h2 class="section-title">Awards & achievements</h2>
    </div>
    <div class="awards-grid">
      <div class="award-card" data-reveal>
        <div class="award-ic">🧩</div>
        <div><h4>Competitive Programming</h4><p>Solved 250+ DSA problems.</p></div>
      </div>
      <div class="award-card" data-reveal>
        <div class="award-ic">🥉</div>
        <div><h4>2nd Runner-Up</h4><p>Regional Level Paper Presentation Competition, organized by GP Amravati.</p></div>
      </div>
      <div class="award-card" data-reveal>
        <div class="award-ic">📄</div>
        <div><h4>Research Paper</h4><p>Real-Time ECG Analytics and Arrhythmia Detection. <a href="https://ieeexplore.ieee.org/document/11308545" target="_blank" rel="noopener">View on IEEE Xplore →</a></p></div>
      </div>
      <div class="award-card" data-reveal>
        <div class="award-ic">🎖️</div>
        <div><h4>Certification</h4><p>IBM Full Stack Software Developer.</p></div>
      </div>
    </div>
  </div>
</section>

<!-- ============ CONTACT ============ -->
<section class="section" id="contact" style="background:var(--bg-1); border-top:1px solid var(--border-soft);">
  <div class="wrap">
    <div class="contact-panel" data-reveal>
      <div class="eyebrow" style="justify-content:center;">— get in touch</div>
      <h2>Let's build something worth committing.</h2>
      <p>Open to internships, collaborations, and research conversations around full-stack systems and applied ML.</p>
      <div class="contact-btns">
        <a href="mailto:anurag.nimkande@gmail.com" class="btn btn-primary">anurag.nimkande@gmail.com</a>
        <a href="https://linkedin.com/in/anurag-nimkande" target="_blank" rel="noopener" class="btn btn-ghost">LinkedIn</a>
        <a href="https://github.com/anuragnimkande" target="_blank" rel="noopener" class="btn btn-ghost">GitHub</a>
      </div>
    </div>
  </div>
</section>

<footer>
  <div class="wrap footer-inner">
    <span>© 2026 Anurag Nimkande</span>
    <div class="footer-links">
      <a href="mailto:anurag.nimkande@gmail.com">Email</a>
      <a href="https://linkedin.com/in/anurag-nimkande" target="_blank" rel="noopener">LinkedIn</a>
      <a href="https://github.com/anuragnimkande" target="_blank" rel="noopener">GitHub</a>
      <a href="tel:+919325873943">+91 9325873943</a>
    </div>
  </div>
</footer>

<script>
(function(){
  var reduceMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches;

  /* ---- Nav toggle ---- */
  var navToggle = document.getElementById('navToggle');
  var navLinks = document.getElementById('navLinks');
  navToggle.addEventListener('click', function(){
    navLinks.classList.toggle('open');
  });
  navLinks.querySelectorAll('a').forEach(function(a){
    a.addEventListener('click', function(){ navLinks.classList.remove('open'); });
  });

  /* ---- Hero role typing (roles drawn from resume/README skill areas) ---- */
  var roles = ["Full-Stack Developer", "Machine Learning Enthusiast", "Computer Engineering Student"];
  var roleEl = document.getElementById('roleTyped');
  var ri = 0, ci = 0, deleting = false;
  function typeRole(){
    if(reduceMotion){ roleEl.textContent = roles[0]; return; }
    var current = roles[ri];
    if(!deleting){
      ci++;
      roleEl.textContent = current.slice(0, ci);
      if(ci === current.length){ deleting = true; setTimeout(typeRole, 1400); return; }
    } else {
      ci--;
      roleEl.textContent = current.slice(0, ci);
      if(ci === 0){ deleting = false; ri = (ri+1) % roles.length; }
    }
    setTimeout(typeRole, deleting ? 34 : 62);
  }
  typeRole();

  /* ---- Terminal closing command typing ---- */
  var cmdEl = document.getElementById('typedOut');
  var cmd = "echo 'let's build something.'";
  var idx = 0;
  function typeCmd(){
    if(reduceMotion){ cmdEl.textContent = cmd; return; }
    if(idx <= cmd.length){
      cmdEl.textContent = cmd.slice(0, idx);
      idx++;
      setTimeout(typeCmd, 48);
    }
  }
  setTimeout(typeCmd, 900);

  /* ---- Scroll reveal with staggered delay per section ---- */
  var revealEls = document.querySelectorAll('[data-reveal]');
  var seen = new Map();
  var io = new IntersectionObserver(function(entries){
    entries.forEach(function(entry){
      if(entry.isIntersecting){
        var el = entry.target;
        var parent = el.parentElement;
        if(!seen.has(parent)) seen.set(parent, 0);
        var i = seen.get(parent);
        seen.set(parent, i+1);
        el.style.transitionDelay = reduceMotion ? '0ms' : (Math.min(i,6) * 90) + 'ms';
        el.classList.add('in-view');
        io.unobserve(el);
      }
    });
  }, {threshold:0.15, rootMargin:'0px 0px -60px 0px'});
  revealEls.forEach(function(el){ io.observe(el); });

  /* ---- Counters (real numbers only: 250 DSA, 7 projects, 1 paper) ---- */
  var counters = document.querySelectorAll('.counter');
  var counterIO = new IntersectionObserver(function(entries){
    entries.forEach(function(entry){
      if(entry.isIntersecting){
        var el = entry.target;
        var target = parseInt(el.getAttribute('data-target'), 10);
        if(reduceMotion){ el.textContent = target; counterIO.unobserve(el); return; }
        var duration = 1400, startTime = null;
        function step(ts){
          if(!startTime) startTime = ts;
          var progress = Math.min((ts - startTime) / duration, 1);
          var eased = 1 - Math.pow(1 - progress, 3);
          el.textContent = Math.floor(eased * target);
          if(progress < 1) requestAnimationFrame(step);
          else el.textContent = target;
        }
        requestAnimationFrame(step);
        counterIO.unobserve(el);
      }
    });
  }, {threshold:0.5});
  counters.forEach(function(el){ counterIO.observe(el); });

  /* ---- Active nav link on scroll ---- */
  var sections = document.querySelectorAll('section[id], header[id]');
  var navA = document.querySelectorAll('.nav-links a');
  window.addEventListener('scroll', function(){
    var pos = window.scrollY + 120;
    sections.forEach(function(sec){
      if(pos >= sec.offsetTop && pos < sec.offsetTop + sec.offsetHeight){
        navA.forEach(function(a){
          a.style.color = a.getAttribute('href') === '#'+sec.id ? 'var(--cyan)' : '';
        });
      }
    });
  });
})();
</script>
</body>
</html>
