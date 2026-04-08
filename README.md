[LinkedIn_Banner_Senior_Dev.html](https://github.com/user-attachments/files/26577863/LinkedIn_Banner_Senior_Dev.html)
[Uploadi<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=1584">
<title>LinkedIn Banner - Senior Full Stack Developer</title>
<style>/* Using system fonts */</style>
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    width: 1584px;
    height: 396px;
    overflow: hidden;
    font-family: Consolas, 'Courier New', monospace;
    background: #030712;
  }

  .banner {
    width: 1584px;
    height: 396px;
    position: relative;
    overflow: hidden;
    background: linear-gradient(135deg, #020817 0%, #0a1628 40%, #0d1b38 70%, #070e1f 100%);
  }

  /* Deep background mesh */
  .bg-mesh {
    position: absolute; inset: 0;
    background:
      radial-gradient(ellipse 900px 500px at 75% 50%, rgba(56, 189, 248, 0.05) 0%, transparent 70%),
      radial-gradient(ellipse 600px 400px at 20% 30%, rgba(139, 92, 246, 0.07) 0%, transparent 60%),
      radial-gradient(ellipse 400px 300px at 90% 80%, rgba(6, 182, 212, 0.06) 0%, transparent 60%);
  }

  /* Animated grid */
  .grid-overlay {
    position: absolute; inset: 0;
    background-image:
      linear-gradient(rgba(56,189,248,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(56,189,248,0.04) 1px, transparent 1px);
    background-size: 44px 44px;
    mask-image: linear-gradient(to right, transparent 0%, black 30%, black 65%, transparent 100%);
  }

  /* Left glow column */
  .left-glow {
    position: absolute;
    left: 0; top: 0; bottom: 0;
    width: 520px;
    background: linear-gradient(to right,
      rgba(139,92,246,0.12) 0%,
      rgba(56,189,248,0.06) 60%,
      transparent 100%
    );
    pointer-events: none;
  }

  /* Rim light on subject */
  .rim-light {
    position: absolute;
    left: 260px;
    top: -50px;
    width: 380px;
    height: 550px;
    background: radial-gradient(ellipse at 50% 40%,
      rgba(56,189,248,0.18) 0%,
      rgba(139,92,246,0.1) 40%,
      transparent 70%
    );
    border-radius: 50%;
    filter: blur(30px);
  }

  /* Photo container */
  .photo-wrapper {
    position: absolute;
    left: 60px;
    bottom: 0;
    width: 320px;
    height: 370px;
    z-index: 10;
  }

  .photo-frame {
    position: absolute;
    bottom: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 260px;
    height: 340px;
    border-radius: 18px 18px 0 0;
    overflow: hidden;
    box-shadow:
      0 0 0 1px rgba(56,189,248,0.2),
      0 0 40px rgba(56,189,248,0.15),
      -8px 0 30px rgba(139,92,246,0.2),
      0 -20px 60px rgba(56,189,248,0.08);
  }

  .photo-frame img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center top;
    filter: contrast(1.05) brightness(0.95) saturate(0.9);
  }

  /* Blue rim edge */
  .photo-frame::before {
    content: '';
    position: absolute;
    inset: 0;
    border-radius: 18px 18px 0 0;
    background: linear-gradient(to right,
      rgba(56,189,248,0.15) 0%,
      transparent 30%,
      transparent 70%,
      rgba(139,92,246,0.1) 100%
    );
    z-index: 2;
    pointer-events: none;
  }

  /* Scan line effect on photo */
  .photo-frame::after {
    content: '';
    position: absolute;
    inset: 0;
    background: repeating-linear-gradient(
      0deg,
      transparent,
      transparent 2px,
      rgba(0,0,0,0.04) 2px,
      rgba(0,0,0,0.04) 4px
    );
    z-index: 3;
    pointer-events: none;
  }

  /* CONTENT RIGHT SIDE */
  .content {
    position: absolute;
    left: 420px;
    top: 0;
    right: 0;
    bottom: 0;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 0 80px 0 30px;
  }

  .status-line {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 18px;
    opacity: 0;
    animation: fadeUp 0.6s ease 0.3s forwards;
  }

  .status-dot {
    width: 8px; height: 8px;
    background: #22d3ee;
    border-radius: 50%;
    box-shadow: 0 0 10px #22d3ee, 0 0 20px rgba(34,211,238,0.5);
    animation: pulse 2s ease infinite;
  }

  @keyframes pulse {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.6; transform: scale(0.85); }
  }

  .status-text {
    font-family: Consolas, 'Courier New', monospace;
    font-size: 11px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: rgba(34,211,238,0.8);
  }

  .name {
    font-family: 'Arial Black', 'Impact', sans-serif;
    font-size: 52px;
    font-weight: 800;
    line-height: 1.0;
    letter-spacing: -1px;
    color: #ffffff;
    margin-bottom: 6px;
    opacity: 0;
    animation: fadeUp 0.6s ease 0.45s forwards;
  }

  .name span {
    background: linear-gradient(90deg, #38bdf8, #818cf8, #c084fc);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .title-line {
    display: flex;
    align-items: center;
    gap: 12px;
    margin-bottom: 22px;
    opacity: 0;
    animation: fadeUp 0.6s ease 0.6s forwards;
  }

  .title-text {
    font-family: Consolas, 'Courier New', monospace;
    font-size: 16px;
    font-weight: 600;
    color: rgba(148,163,184,0.9);
    letter-spacing: 1px;
  }

  .title-separator {
    color: rgba(56,189,248,0.4);
    font-size: 20px;
  }

  /* Skill tags */
  .tags {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-bottom: 28px;
    opacity: 0;
    animation: fadeUp 0.6s ease 0.75s forwards;
  }

  .tag {
    padding: 5px 14px;
    border: 1px solid rgba(56,189,248,0.2);
    border-radius: 4px;
    font-family: Consolas, 'Courier New', monospace;
    font-size: 11px;
    letter-spacing: 1px;
    color: rgba(148,163,184,0.8);
    background: rgba(56,189,248,0.04);
    transition: all 0.2s;
  }

  .tag.highlight {
    border-color: rgba(129,140,248,0.4);
    color: rgba(165,180,252,0.9);
    background: rgba(129,140,248,0.08);
  }

  /* Code snippet floating elements */
  .code-snippet {
    position: absolute;
    font-family: Consolas, 'Courier New', monospace;
    font-size: 11px;
    line-height: 1.6;
    color: rgba(100,116,139,0.5);
    pointer-events: none;
  }

  .code-snippet .kw { color: rgba(192,132,252,0.45); }
  .code-snippet .fn { color: rgba(56,189,248,0.4); }
  .code-snippet .str { color: rgba(34,197,94,0.35); }
  .code-snippet .num { color: rgba(251,146,60,0.4); }

  .snippet-1 {
    top: 28px; right: 60px;
    opacity: 0;
    animation: fadeIn 1s ease 1.2s forwards;
  }

  .snippet-2 {
    bottom: 30px; right: 55px;
    opacity: 0;
    animation: fadeIn 1s ease 1.5s forwards;
  }

  /* Dashboard mockup */
  .dashboard-mock {
    position: absolute;
    top: 50px; right: 30px;
    width: 220px;
    background: rgba(15,23,42,0.7);
    border: 1px solid rgba(56,189,248,0.12);
    border-radius: 10px;
    padding: 14px;
    backdrop-filter: blur(8px);
    opacity: 0;
    animation: fadeIn 0.8s ease 1.8s forwards;
    box-shadow: 0 0 30px rgba(56,189,248,0.05);
  }

  .dash-header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 10px;
  }

  .dash-dots {
    display: flex; gap: 5px;
  }

  .dash-dot {
    width: 7px; height: 7px; border-radius: 50%;
  }
  .dash-dot:nth-child(1) { background: rgba(239,68,68,0.6); }
  .dash-dot:nth-child(2) { background: rgba(234,179,8,0.6); }
  .dash-dot:nth-child(3) { background: rgba(34,197,94,0.6); }

  .dash-title {
    font-size: 9px;
    color: rgba(100,116,139,0.7);
    letter-spacing: 1px;
    text-transform: uppercase;
  }

  .dash-bars {
    display: flex;
    align-items: flex-end;
    gap: 6px;
    height: 50px;
    margin-bottom: 10px;
  }

  .bar {
    flex: 1;
    border-radius: 3px 3px 0 0;
    background: rgba(56,189,248,0.25);
    animation: barGrow 1s ease forwards;
    transform-origin: bottom;
  }
  .bar:nth-child(2) { background: rgba(129,140,248,0.3); animation-delay: 0.1s; }
  .bar:nth-child(3) { background: rgba(192,132,252,0.25); animation-delay: 0.2s; }
  .bar:nth-child(4) { background: rgba(56,189,248,0.35); animation-delay: 0.15s; }
  .bar:nth-child(5) { background: rgba(34,211,238,0.3); animation-delay: 0.25s; }

  @keyframes barGrow {
    from { transform: scaleY(0.2); opacity: 0.3; }
    to { transform: scaleY(1); opacity: 1; }
  }

  .dash-metric {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 5px 0;
    border-top: 1px solid rgba(56,189,248,0.07);
  }

  .dash-label { font-size: 9px; color: rgba(100,116,139,0.6); letter-spacing: 0.5px; }
  .dash-value { font-size: 11px; color: rgba(34,211,238,0.8); font-weight: 600; }

  /* Glassmorphism card */
  .glass-card {
    position: absolute;
    bottom: 45px; right: 35px;
    width: 190px;
    background: rgba(15,23,42,0.5);
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 12px;
    padding: 14px 16px;
    backdrop-filter: blur(12px);
    opacity: 0;
    animation: fadeIn 0.8s ease 2.1s forwards;
    box-shadow:
      0 0 0 1px rgba(56,189,248,0.08),
      inset 0 1px 0 rgba(255,255,255,0.05);
  }

  .glass-row {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 8px;
  }

  .glass-icon {
    width: 28px; height: 28px;
    border-radius: 6px;
    background: linear-gradient(135deg, rgba(56,189,248,0.2), rgba(129,140,248,0.15));
    border: 1px solid rgba(56,189,248,0.15);
    display: flex; align-items: center; justify-content: center;
    font-size: 13px;
  }

  .glass-info {}
  .glass-label { font-size: 9px; color: rgba(100,116,139,0.6); letter-spacing: 0.5px; text-transform: uppercase; }
  .glass-val { font-size: 12px; color: rgba(226,232,240,0.85); font-weight: 600; }

  .progress-bar-wrap {
    margin-top: 10px;
    height: 3px;
    background: rgba(56,189,248,0.1);
    border-radius: 2px;
    overflow: hidden;
  }

  .progress-fill {
    height: 100%;
    background: linear-gradient(90deg, #38bdf8, #818cf8);
    border-radius: 2px;
    width: 0;
    animation: fillBar 2s ease 2.5s forwards;
  }

  @keyframes fillBar { to { width: 78%; } }

  /* Floating particles */
  .particles {
    position: absolute; inset: 0;
    pointer-events: none;
  }

  .particle {
    position: absolute;
    width: 2px; height: 2px;
    background: rgba(56,189,248,0.5);
    border-radius: 50%;
    animation: float linear infinite;
  }

  @keyframes float {
    0% { transform: translateY(0) translateX(0); opacity: 0; }
    10% { opacity: 1; }
    90% { opacity: 0.3; }
    100% { transform: translateY(-300px) translateX(20px); opacity: 0; }
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(16px); }
    to { opacity: 1; transform: translateY(0); }
  }

  @keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
  }

  /* Decorative line */
  .deco-line {
    position: absolute;
    left: 390px;
    top: 0; bottom: 0;
    width: 1px;
    background: linear-gradient(to bottom, transparent, rgba(56,189,248,0.2) 30%, rgba(56,189,248,0.2) 70%, transparent);
  }

  /* Bottom bar */
  .bottom-accent {
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(to right,
      transparent 5%,
      rgba(139,92,246,0.4) 20%,
      rgba(56,189,248,0.6) 45%,
      rgba(34,211,238,0.5) 60%,
      transparent 90%
    );
  }
</style>
</head>
<body>
<div class="banner">
  <div class="bg-mesh"></div>
  <div class="grid-overlay"></div>
  <div class="left-glow"></div>
  <div class="rim-light"></div>
  <div class="deco-line"></div>

  <!-- Floating particles -->
  <div class="particles">
    <div class="particle" style="left:42%;top:80%;width:3px;height:3px;animation-duration:8s;animation-delay:0s;"></div>
    <div class="particle" style="left:55%;top:90%;animation-duration:12s;animation-delay:2s;"></div>
    <div class="particle" style="left:70%;top:75%;width:3px;height:3px;animation-duration:10s;animation-delay:4s;background:rgba(192,132,252,0.6);"></div>
    <div class="particle" style="left:80%;top:85%;animation-duration:9s;animation-delay:1s;background:rgba(34,211,238,0.5);"></div>
    <div class="particle" style="left:48%;top:70%;animation-duration:11s;animation-delay:5s;"></div>
    <div class="particle" style="left:62%;top:92%;width:4px;height:4px;animation-duration:13s;animation-delay:3s;background:rgba(129,140,248,0.5);"></div>
  </div>

  <!-- Photo -->
  <div class="photo-wrapper">
    <div class="photo-frame">
      <img src="data:image/jpeg;base64,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" alt="Profile Photo" />
    </div>
  </div>

  <!-- Main content -->
  <div class="content">
    <div class="status-line">
      <div class="status-dot"></div>
      <span class="status-text">Available for opportunities</span>
    </div>

    <div class="name">Safayet<br><span>Hossain</span></div>

    <div class="title-line">
      <span class="title-text">Senior Full Stack Developer</span>
      <span class="title-separator">/</span>
      <span class="title-text">Web Architect</span>
    </div>

    <div class="tags">
      <span class="tag highlight">React.js</span>
      <span class="tag highlight">Node.js</span>
      <span class="tag">TypeScript</span>
      <span class="tag">Next.js</span>
      <span class="tag">PostgreSQL</span>
      <span class="tag">AWS</span>
      <span class="tag">Docker</span>
      <span class="tag">REST API</span>
    </div>
  </div>

  <!-- Floating code snippet top right -->
  <div class="code-snippet snippet-1">
    <div><span class="kw">const</span> <span class="fn">buildApp</span> = <span class="kw">async</span> () =&gt; {</div>
    <div>&nbsp;&nbsp;<span class="kw">const</span> server = <span class="kw">await</span> <span class="fn">createServer</span>({</div>
    <div>&nbsp;&nbsp;&nbsp;&nbsp;port: <span class="num">3000</span>,</div>
    <div>&nbsp;&nbsp;&nbsp;&nbsp;env: <span class="str">'production'</span></div>
    <div>&nbsp;&nbsp;});</div>
    <div>&nbsp;&nbsp;<span class="kw">return</span> server.<span class="fn">listen</span>();</div>
    <div>};</div>
  </div>

  <!-- Floating code snippet bottom right -->
  <div class="code-snippet snippet-2">
    <div><span class="kw">SELECT</span> users.*, <span class="fn">COUNT</span>(orders.id) <span class="kw">AS</span> total</div>
    <div><span class="kw">FROM</span> users <span class="kw">LEFT JOIN</span> orders</div>
    <div><span class="kw">ON</span> users.id = orders.user_id</div>
    <div><span class="kw">GROUP BY</span> users.id <span class="kw">HAVING</span> total &gt; <span class="num">5</span>;</div>
  </div>

  <!-- Dashboard mockup -->
  <div class="dashboard-mock">
    <div class="dash-header">
      <div class="dash-dots">
        <div class="dash-dot"></div>
        <div class="dash-dot"></div>
        <div class="dash-dot"></div>
      </div>
      <div class="dash-title">Performance</div>
    </div>
    <div class="dash-bars">
      <div class="bar" style="height:65%"></div>
      <div class="bar" style="height:85%"></div>
      <div class="bar" style="height:50%"></div>
      <div class="bar" style="height:90%"></div>
      <div class="bar" style="height:72%"></div>
      <div class="bar" style="height:60%"></div>
    </div>
    <div class="dash-metric">
      <span class="dash-label">API Uptime</span>
      <span class="dash-value">99.97%</span>
    </div>
    <div class="dash-metric">
      <span class="dash-label">Response</span>
      <span class="dash-value">84ms</span>
    </div>
  </div>

  <!-- Glassmorphism card -->
  <div class="glass-card">
    <div class="glass-row">
      <div class="glass-icon">🚀</div>
      <div class="glass-info">
        <div class="glass-label">Projects Delivered</div>
        <div class="glass-val">50+ Solutions</div>
      </div>
    </div>
    <div class="glass-row">
      <div class="glass-icon">⚡</div>
      <div class="glass-info">
        <div class="glass-label">Expertise</div>
        <div class="glass-val">5+ Years</div>
      </div>
    </div>
    <div class="progress-bar-wrap">
      <div class="progress-fill"></div>
    </div>
  </div>

  <div class="bottom-accent"></div>
</div>
</body>
</html>
ng LinkedIn_Banner_Senior_Dev.html…]()

<h1 align="center">Hi 👋, I'm Safayet</h1>
<h3 align="center">A passionate frontend developer from Bangladesh</h3>

<p align="left"> <img src="https://komarev.com/ghpvc/?username=safa-yet&label=Profile%20views&color=0e75b6&style=flat" alt="safa-yet" /> </p>

<p align="left"> <a href="https://github.com/ryo-ma/github-profile-trophy"><img src="https://github-profile-trophy.vercel.app/?username=safa-yet" alt="safa-yet" /></a> </p>

- 🔭 I’m currently working on **Sundarban Tour & Travels**

<h3 align="left">Connect with me:</h3>
<p align="left">
<a href="https://linkedin.com/in/safayet-ul-islam" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="safayet-ul-islam" height="30" width="40" /></a>
</p>

<h3 align="left">Languages and Tools:</h3>
<p align="left"> <a href="https://getbootstrap.com" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/bootstrap/bootstrap-plain-wordmark.svg" alt="bootstrap" width="40" height="40"/> </a> <a href="https://www.w3schools.com/css/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original-wordmark.svg" alt="css3" width="40" height="40"/> </a> <a href="https://www.figma.com/" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/figma/figma-icon.svg" alt="figma" width="40" height="40"/> </a> <a href="https://www.w3.org/html/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original-wordmark.svg" alt="html5" width="40" height="40"/> </a> <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" alt="javascript" width="40" height="40"/> </a> <a href="https://www.mongodb.com/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mongodb/mongodb-original-wordmark.svg" alt="mongodb" width="40" height="40"/> </a> <a href="https://nestjs.com/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nestjs/nestjs-plain.svg" alt="nestjs" width="40" height="40"/> </a> <a href="https://nextjs.org/" target="_blank" rel="noreferrer"> <img src="https://cdn.worldvectorlogo.com/logos/nextjs-2.svg" alt="nextjs" width="40" height="40"/> </a> <a href="https://nodejs.org" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original-wordmark.svg" alt="nodejs" width="40" height="40"/> </a> <a href="https://www.photoshop.com/en" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/photoshop/photoshop-line.svg" alt="photoshop" width="40" height="40"/> </a> <a href="https://reactjs.org/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original-wordmark.svg" alt="react" width="40" height="40"/> </a> <a href="https://reactnative.dev/" target="_blank" rel="noreferrer"> <img src="https://reactnative.dev/img/header_logo.svg" alt="reactnative" width="40" height="40"/> </a> <a href="https://tailwindcss.com/" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/tailwindcss/tailwindcss-icon.svg" alt="tailwind" width="40" height="40"/> </a> <a href="https://www.typescriptlang.org/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/typescript/typescript-original.svg" alt="typescript" width="40" height="40"/> </a> </p>

<p><img align="left" src="https://github-readme-stats.vercel.app/api/top-langs?username=safa-yet&show_icons=true&locale=en&layout=compact" alt="safa-yet" /></p>

<p>&nbsp;<img align="center" src="https://github-readme-stats.vercel.app/api?username=safa-yet&show_icons=true&locale=en" alt="safa-yet" /></p>
