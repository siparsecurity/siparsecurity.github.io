<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Sipar Security</title>
  <link href="https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Syne:wght@400;700;800&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg: #020408;
      --surface: #060d14;
      --border: #0f2535;
      --accent: #00d4ff;
      --accent2: #00ff9f;
      --danger: #ff3e3e;
      --text: #c8d8e8;
      --muted: #3a5060;
      --font-mono: 'Share Tech Mono', monospace;
      --font-display: 'Syne', sans-serif;
    }

    * { margin: 0; padding: 0; box-sizing: border-box; }

    html { scroll-behavior: smooth; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: var(--font-display);
      overflow-x: hidden;
      cursor: none;
    }

    /* CUSTOM CURSOR */
    .cursor {
      position: fixed;
      width: 8px; height: 8px;
      background: var(--accent);
      border-radius: 50%;
      pointer-events: none;
      z-index: 9999;
      transform: translate(-50%, -50%);
      transition: transform 0.1s;
      box-shadow: 0 0 12px var(--accent);
    }
    .cursor-ring {
      position: fixed;
      width: 32px; height: 32px;
      border: 1px solid var(--accent);
      border-radius: 50%;
      pointer-events: none;
      z-index: 9998;
      transform: translate(-50%, -50%);
      transition: all 0.15s ease;
      opacity: 0.5;
    }

    /* GRID BACKGROUND */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image:
        linear-gradient(var(--border) 1px, transparent 1px),
        linear-gradient(90deg, var(--border) 1px, transparent 1px);
      background-size: 60px 60px;
      opacity: 0.4;
      pointer-events: none;
      z-index: 0;
    }

    /* SCAN LINE */
    body::after {
      content: '';
      position: fixed;
      top: -100%;
      left: 0; right: 0;
      height: 200px;
      background: linear-gradient(transparent, rgba(0,212,255,0.03), transparent);
      animation: scanline 8s linear infinite;
      pointer-events: none;
      z-index: 1;
    }

    @keyframes scanline {
      0% { top: -200px; }
      100% { top: 100vh; }
    }

    /* NAV */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 100;
      padding: 1.25rem 3rem;
      display: flex;
      align-items: center;
      justify-content: space-between;
      border-bottom: 1px solid var(--border);
      background: rgba(2,4,8,0.85);
      backdrop-filter: blur(12px);
    }

    .nav-logo {
      font-family: var(--font-mono);
      font-size: 1rem;
      color: var(--accent);
      letter-spacing: 0.1em;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .nav-logo .bracket { color: var(--muted); }

    .nav-status {
      display: flex;
      align-items: center;
      gap: 0.5rem;
      font-family: var(--font-mono);
      font-size: 0.75rem;
      color: var(--muted);
    }

    .status-dot {
      width: 6px; height: 6px;
      background: var(--accent2);
      border-radius: 50%;
      animation: pulse 2s ease-in-out infinite;
    }

    @keyframes pulse {
      0%, 100% { opacity: 1; box-shadow: 0 0 6px var(--accent2); }
      50% { opacity: 0.4; box-shadow: none; }
    }

    .nav-links {
      display: flex;
      gap: 2rem;
      list-style: none;
    }

    .nav-links a {
      font-family: var(--font-mono);
      font-size: 0.8rem;
      color: var(--muted);
      text-decoration: none;
      letter-spacing: 0.05em;
      transition: color 0.2s;
    }

    .nav-links a:hover { color: var(--accent); }

    /* HERO */
    .hero {
      position: relative;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 6rem 3rem 4rem;
      z-index: 2;
    }

    .hero-inner {
      max-width: 900px;
      width: 100%;
      text-align: center;
    }

    .hero-tag {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      font-family: var(--font-mono);
      font-size: 0.75rem;
      color: var(--accent);
      border: 1px solid rgba(0,212,255,0.3);
      background: rgba(0,212,255,0.05);
      padding: 0.4rem 1rem;
      border-radius: 2px;
      margin-bottom: 2.5rem;
      letter-spacing: 0.15em;
      animation: fadeUp 0.6s ease both;
    }

    .hero-tag::before {
      content: '▶';
      font-size: 0.5rem;
    }

    .hero-title {
      font-size: clamp(3.5rem, 8vw, 7rem);
      font-weight: 800;
      line-height: 0.95;
      letter-spacing: -0.02em;
      margin-bottom: 1.5rem;
      animation: fadeUp 0.6s 0.1s ease both;
    }

    .hero-title .line1 { display: block; color: #fff; }
    .hero-title .line2 {
      display: block;
      color: transparent;
      -webkit-text-stroke: 1px var(--accent);
      position: relative;
    }

    .hero-sub {
      font-family: var(--font-mono);
      font-size: 0.95rem;
      color: var(--muted);
      line-height: 1.8;
      max-width: 520px;
      margin: 0 auto 3rem;
      animation: fadeUp 0.6s 0.2s ease both;
    }

    .hero-sub span { color: var(--accent2); }

    .hero-cta {
      display: flex;
      gap: 1rem;
      justify-content: center;
      flex-wrap: wrap;
      animation: fadeUp 0.6s 0.3s ease both;
    }

    .btn {
      font-family: var(--font-mono);
      font-size: 0.85rem;
      letter-spacing: 0.05em;
      padding: 0.75rem 1.75rem;
      border-radius: 2px;
      text-decoration: none;
      transition: all 0.2s;
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
    }

    .btn-primary {
      background: var(--accent);
      color: #000;
      font-weight: 700;
      border: 1px solid var(--accent);
    }

    .btn-primary:hover {
      background: transparent;
      color: var(--accent);
      box-shadow: 0 0 20px rgba(0,212,255,0.3);
    }

    .btn-ghost {
      background: transparent;
      color: var(--text);
      border: 1px solid var(--border);
    }

    .btn-ghost:hover {
      border-color: var(--accent);
      color: var(--accent);
    }

    /* TERMINAL BLOCK */
    .terminal-wrap {
      margin: 4rem auto 0;
      max-width: 620px;
      animation: fadeUp 0.6s 0.4s ease both;
    }

    .terminal {
      background: #020c14;
      border: 1px solid var(--border);
      border-radius: 6px;
      overflow: hidden;
      text-align: left;
    }

    .terminal-header {
      background: #060d14;
      padding: 0.6rem 1rem;
      display: flex;
      align-items: center;
      gap: 0.5rem;
      border-bottom: 1px solid var(--border);
    }

    .dot { width: 10px; height: 10px; border-radius: 50%; }
    .dot.r { background: #ff5f57; }
    .dot.y { background: #febc2e; }
    .dot.g { background: #28c840; }

    .terminal-title {
      font-family: var(--font-mono);
      font-size: 0.7rem;
      color: var(--muted);
      margin-left: auto;
    }

    .terminal-body {
      padding: 1.25rem 1.5rem;
      font-family: var(--font-mono);
      font-size: 0.82rem;
      line-height: 2;
    }

    .t-line { display: flex; gap: 0.75rem; }
    .t-prompt { color: var(--accent2); }
    .t-cmd { color: var(--text); }
    .t-out { color: var(--muted); padding-left: 1.5rem; }
    .t-event { color: var(--accent); }
    .t-alert { color: var(--danger); }
    .t-cursor {
      display: inline-block;
      width: 8px; height: 1em;
      background: var(--accent);
      animation: blink 1s step-end infinite;
      vertical-align: text-bottom;
    }

    @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

    /* STATS BAR */
    .stats-bar {
      position: relative;
      z-index: 2;
      border-top: 1px solid var(--border);
      border-bottom: 1px solid var(--border);
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      overflow: hidden;
    }

    .stat-item {
      padding: 2rem;
      text-align: center;
      border-right: 1px solid var(--border);
      position: relative;
      overflow: hidden;
    }

    .stat-item:last-child { border-right: none; }

    .stat-item::before {
      content: '';
      position: absolute;
      inset: 0;
      background: linear-gradient(135deg, rgba(0,212,255,0.03), transparent);
      opacity: 0;
      transition: opacity 0.3s;
    }

    .stat-item:hover::before { opacity: 1; }

    .stat-num {
      font-size: 2.5rem;
      font-weight: 800;
      color: #fff;
      line-height: 1;
      margin-bottom: 0.5rem;
    }

    .stat-num span { color: var(--accent); }
    .stat-label {
      font-family: var(--font-mono);
      font-size: 0.7rem;
      color: var(--muted);
      letter-spacing: 0.1em;
      text-transform: uppercase;
    }

    /* SECTION */
    section {
      position: relative;
      z-index: 2;
      padding: 6rem 3rem;
      max-width: 1100px;
      margin: 0 auto;
    }

    .section-label {
      font-family: var(--font-mono);
      font-size: 0.7rem;
      color: var(--accent);
      letter-spacing: 0.2em;
      text-transform: uppercase;
      margin-bottom: 1rem;
      display: flex;
      align-items: center;
      gap: 0.75rem;
    }

    .section-label::after {
      content: '';
      flex: 1;
      height: 1px;
      background: var(--border);
      max-width: 80px;
    }

    .section-title {
      font-size: clamp(2rem, 4vw, 3rem);
      font-weight: 800;
      color: #fff;
      margin-bottom: 3rem;
      line-height: 1.1;
    }

    /* FEATURES GRID */
    .features-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1px;
      background: var(--border);
      border: 1px solid var(--border);
    }

    .feature-card {
      background: var(--bg);
      padding: 2rem;
      position: relative;
      overflow: hidden;
      transition: background 0.3s;
    }

    .feature-card:hover { background: var(--surface); }

    .feature-card::after {
      content: '';
      position: absolute;
      top: 0; left: 0;
      width: 3px; height: 100%;
      background: var(--accent);
      transform: scaleY(0);
      transform-origin: top;
      transition: transform 0.3s;
    }

    .feature-card:hover::after { transform: scaleY(1); }

    .feature-icon {
      font-size: 1.5rem;
      margin-bottom: 1rem;
      display: block;
    }

    .feature-title {
      font-size: 1rem;
      font-weight: 700;
      color: #fff;
      margin-bottom: 0.5rem;
    }

    .feature-desc {
      font-family: var(--font-mono);
      font-size: 0.78rem;
      color: var(--muted);
      line-height: 1.7;
    }

    .feature-badge {
      display: inline-block;
      margin-top: 0.75rem;
      font-family: var(--font-mono);
      font-size: 0.65rem;
      padding: 0.2rem 0.6rem;
      border-radius: 2px;
      letter-spacing: 0.1em;
    }

    .badge-live { background: rgba(0,255,159,0.1); color: var(--accent2); border: 1px solid rgba(0,255,159,0.3); }
    .badge-wip { background: rgba(255,62,62,0.1); color: var(--danger); border: 1px solid rgba(255,62,62,0.3); }

    /* RELEASE SECTION */
    .release-card {
      border: 1px solid var(--border);
      background: var(--surface);
      padding: 2.5rem;
      display: grid;
      grid-template-columns: 1fr auto;
      gap: 2rem;
      align-items: center;
    }

    .release-tag {
      font-family: var(--font-mono);
      font-size: 0.7rem;
      color: var(--accent2);
      border: 1px solid rgba(0,255,159,0.3);
      background: rgba(0,255,159,0.05);
      padding: 0.3rem 0.8rem;
      display: inline-block;
      margin-bottom: 1rem;
    }

    .release-name {
      font-size: 1.75rem;
      font-weight: 800;
      color: #fff;
      margin-bottom: 0.5rem;
    }

    .release-date {
      font-family: var(--font-mono);
      font-size: 0.75rem;
      color: var(--muted);
      margin-bottom: 1.5rem;
    }

    .release-features {
      list-style: none;
      display: flex;
      flex-direction: column;
      gap: 0.4rem;
    }

    .release-features li {
      font-family: var(--font-mono);
      font-size: 0.8rem;
      color: var(--text);
      display: flex;
      align-items: center;
      gap: 0.75rem;
    }

    .release-features li::before {
      content: '✓';
      color: var(--accent2);
      font-size: 0.7rem;
    }

    /* ROADMAP */
    .roadmap {
      display: flex;
      flex-direction: column;
      gap: 0;
    }

    .roadmap-item {
      display: grid;
      grid-template-columns: 120px 1px 1fr;
      gap: 0 2rem;
      padding: 2rem 0;
    }

    .roadmap-version {
      font-family: var(--font-mono);
      font-size: 0.85rem;
      color: var(--accent);
      text-align: right;
      padding-top: 0.1rem;
    }

    .roadmap-line {
      background: var(--border);
      position: relative;
    }

    .roadmap-line::before {
      content: '';
      position: absolute;
      top: 6px;
      left: 50%;
      transform: translateX(-50%);
      width: 10px; height: 10px;
      border-radius: 50%;
      background: var(--border);
      border: 2px solid var(--muted);
    }

    .roadmap-item.done .roadmap-line::before {
      background: var(--accent2);
      border-color: var(--accent2);
      box-shadow: 0 0 8px var(--accent2);
    }

    .roadmap-item.active .roadmap-line::before {
      background: var(--accent);
      border-color: var(--accent);
      box-shadow: 0 0 12px var(--accent);
      animation: pulse 2s infinite;
    }

    .roadmap-content-title {
      font-size: 1rem;
      font-weight: 700;
      color: #fff;
      margin-bottom: 0.4rem;
    }

    .roadmap-content-desc {
      font-family: var(--font-mono);
      font-size: 0.78rem;
      color: var(--muted);
      line-height: 1.6;
    }

    /* FOOTER */
    footer {
      position: relative;
      z-index: 2;
      border-top: 1px solid var(--border);
      padding: 3rem;
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 1.5rem;
    }

    .footer-logo {
      font-family: var(--font-mono);
      font-size: 0.9rem;
      color: var(--accent);
    }

    .footer-links {
      display: flex;
      gap: 1.5rem;
    }

    .footer-links a {
      font-family: var(--font-mono);
      font-size: 0.78rem;
      color: var(--muted);
      text-decoration: none;
      transition: color 0.2s;
    }

    .footer-links a:hover { color: var(--accent); }

    .footer-copy {
      font-family: var(--font-mono);
      font-size: 0.7rem;
      color: var(--muted);
      width: 100%;
    }

    /* ANIMATIONS */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    .reveal {
      opacity: 0;
      transform: translateY(24px);
      transition: opacity 0.6s ease, transform 0.6s ease;
    }

    .reveal.visible {
      opacity: 1;
      transform: none;
    }

    /* GLITCH */
    .glitch {
      position: relative;
    }

    .glitch::before, .glitch::after {
      content: attr(data-text);
      position: absolute;
      top: 0; left: 0;
      width: 100%;
    }

    .glitch::before {
      color: var(--accent);
      animation: glitch1 4s infinite;
      clip-path: polygon(0 0, 100% 0, 100% 35%, 0 35%);
    }

    .glitch::after {
      color: var(--danger);
      animation: glitch2 4s infinite;
      clip-path: polygon(0 65%, 100% 65%, 100% 100%, 0 100%);
    }

    @keyframes glitch1 {
      0%,90%,100% { transform: none; opacity: 0; }
      92% { transform: translateX(-3px); opacity: 0.8; }
      94% { transform: translateX(3px); opacity: 0.8; }
      96% { transform: none; opacity: 0; }
    }

    @keyframes glitch2 {
      0%,90%,100% { transform: none; opacity: 0; }
      93% { transform: translateX(3px); opacity: 0.8; }
      95% { transform: translateX(-3px); opacity: 0.8; }
      97% { transform: none; opacity: 0; }
    }

    @media (max-width: 768px) {
      nav { padding: 1rem 1.5rem; }
      .nav-links { display: none; }
      .hero { padding: 5rem 1.5rem 3rem; }
      .stats-bar { grid-template-columns: repeat(2, 1fr); }
      section { padding: 4rem 1.5rem; }
      .features-grid { grid-template-columns: 1fr; }
      .release-card { grid-template-columns: 1fr; }
      footer { padding: 2rem 1.5rem; }
      .roadmap-item { grid-template-columns: 80px 1px 1fr; gap: 0 1rem; }
    }
  </style>
</head>
<body>

  <div class="cursor" id="cursor"></div>
  <div class="cursor-ring" id="cursorRing"></div>

  <!-- NAV -->
  <nav>
    <div class="nav-logo">
      <span class="bracket">[</span>SIPAR<span style="color:var(--accent2)">_</span>SECURITY<span class="bracket">]</span>
    </div>
    <ul class="nav-links">
      <li><a href="#features">Features</a></li>
      <li><a href="#release">Release</a></li>
      <li><a href="#roadmap">Roadmap</a></li>
      <li><a href="https://github.com/siparsecurity" target="_blank">GitHub</a></li>
    </ul>
    <div class="nav-status">
      <div class="status-dot"></div>
      SYSTEMS OPERATIONAL
    </div>
  </nav>

  <!-- HERO -->
  <div class="hero">
    <div class="hero-inner">
      <div class="hero-tag">OPEN SOURCE · NETWORK SECURITY · PAKISTAN 🇵🇰</div>
      <h1 class="hero-title">
        <span class="line1 glitch" data-text="NETWORK">NETWORK</span>
        <span class="line2">MONITOR</span>
      </h1>
      <p class="hero-sub">
        Real-time device tracking, event logging, and threat detection
        for <span>home users</span>, IT admins, and small businesses.
        <br/>No enterprise budget required.
      </p>
      <div class="hero-cta">
        <a href="https://github.com/siparsecurity/network-monitor" target="_blank" class="btn btn-primary">
          ⭐ View on GitHub
        </a>
        <a href="https://github.com/siparsecurity/network-monitor/releases/tag/v0.1-layer1" target="_blank" class="btn btn-ghost">
          ↓ Download v0.1
        </a>
      </div>

      <div class="terminal-wrap">
        <div class="terminal">
          <div class="terminal-header">
            <div class="dot r"></div>
            <div class="dot y"></div>
            <div class="dot g"></div>
            <span class="terminal-title">network-monitor — bash</span>
          </div>
          <div class="terminal-body">
            <div class="t-line"><span class="t-prompt">$</span><span class="t-cmd">sudo python run_soc.py</span></div>
            <div class="t-out">[+] Starting SOC System...</div>
            <div class="t-out">[+] Event Server running on http://127.0.0.1:5050</div>
            <div class="t-out">[+] IDS Running on 192.168.1.0/24</div>
            <div class="t-out t-event">[+] Initial scan complete — 4 devices found</div>
            <div class="t-out">[+] Dashboard → <span style="color:var(--accent)">http://localhost:5000</span></div>
            <div class="t-out t-event">[NEW DEVICE] 192.168.1.107 — fe:ce:a0:5a:fa:c9</div>
            <div class="t-out t-alert">[ALERT] ARP SPOOF DETECTED: 192.168.1.1</div>
            <div class="t-line"><span class="t-prompt">$</span><span class="t-cursor"></span></div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- STATS -->
  <div class="stats-bar">
    <div class="stat-item">
      <div class="stat-num">5<span>+</span></div>
      <div class="stat-label">Core Modules</div>
    </div>
    <div class="stat-item">
      <div class="stat-num">10<span>s</span></div>
      <div class="stat-label">Scan Interval</div>
    </div>
    <div class="stat-item">
      <div class="stat-num">v0<span>.1</span></div>
      <div class="stat-label">Latest Release</div>
    </div>
    <div class="stat-item">
      <div class="stat-num">100<span>%</span></div>
      <div class="stat-label">Open Source</div>
    </div>
  </div>

  <!-- FEATURES -->
  <section id="features">
    <div class="section-label reveal">01 — CAPABILITIES</div>
    <h2 class="section-title reveal">What it does</h2>
    <div class="features-grid reveal">
      <div class="feature-card">
        <span class="feature-icon">🔍</span>
        <div class="feature-title">Device Discovery</div>
        <div class="feature-desc">Detects every device on your network via ARP scanning. Captures MAC address and IP for each host.</div>
        <span class="feature-badge badge-live">LIVE</span>
      </div>
      <div class="feature-card">
        <span class="feature-icon">📡</span>
        <div class="feature-title">Real-Time Tracking</div>
        <div class="feature-desc">Continuous scans every 10 seconds. Instantly flags new connections and disconnections.</div>
        <span class="feature-badge badge-live">LIVE</span>
      </div>
      <div class="feature-card">
        <span class="feature-icon">📋</span>
        <div class="feature-title">Event Logging</div>
        <div class="feature-desc">Every network event is timestamped and logged — new devices, disconnects, and alerts.</div>
        <span class="feature-badge badge-live">LIVE</span>
      </div>
      <div class="feature-card">
        <span class="feature-icon">🖥️</span>
        <div class="feature-title">SOC Dashboard</div>
        <div class="feature-desc">Browser-based SOC-style dashboard accessible via localhost. Shows all devices, events, and risk levels.</div>
        <span class="feature-badge badge-live">LIVE</span>
      </div>
      <div class="feature-card">
        <span class="feature-icon">⚙️</span>
        <div class="feature-title">Auto Interface Detection</div>
        <div class="feature-desc">Automatically detects your active network interface and subnet. No manual configuration needed.</div>
        <span class="feature-badge badge-live">LIVE</span>
      </div>
      <div class="feature-card">
        <span class="feature-icon">🛡️</span>
        <div class="feature-title">ARP Spoof Detection</div>
        <div class="feature-desc">Monitors MAC address history per IP. Flags any IP that changes MAC — a key indicator of ARP spoofing.</div>
        <span class="feature-badge badge-wip">IN PROGRESS</span>
      </div>
    </div>
  </section>

  <!-- RELEASE -->
  <section id="release">
    <div class="section-label reveal">02 — LATEST RELEASE</div>
    <h2 class="section-title reveal">Layer 1 is live</h2>
    <div class="release-card reveal">
      <div>
        <div class="release-tag">v0.1-layer1</div>
        <div class="release-name">Initial Release</div>
        <div class="release-date">Released — June 2, 2026</div>
        <ul class="release-features">
          <li>ARP-based device discovery (MAC + IP)</li>
          <li>Real-time online/offline status tracking</li>
          <li>Timestamped event logging system</li>
          <li>SOC-style web dashboard</li>
          <li>Auto network interface detection</li>
          <li>3-process architecture (scanner, event server, dashboard)</li>
        </ul>
      </div>
      <div style="display:flex;flex-direction:column;gap:0.75rem;min-width:180px;">
        <a href="https://github.com/siparsecurity/network-monitor/releases/tag/v0.1-layer1" target="_blank" class="btn btn-primary" style="justify-content:center;">↓ Download</a>
        <a href="https://github.com/siparsecurity/network-monitor" target="_blank" class="btn btn-ghost" style="justify-content:center;">View Code</a>
      </div>
    </div>
  </section>

  <!-- ROADMAP -->
  <section id="roadmap">
    <div class="section-label reveal">03 — ROADMAP</div>
    <h2 class="section-title reveal">What's coming</h2>
    <div class="roadmap reveal">
      <div class="roadmap-item done">
        <div class="roadmap-version">v0.1</div>
        <div class="roadmap-line"></div>
        <div>
          <div class="roadmap-content-title">Layer 1 — Foundation</div>
          <div class="roadmap-content-desc">Device detection, event logging, SOC dashboard, ARP scan engine</div>
        </div>
      </div>
      <div class="roadmap-item active">
        <div class="roadmap-version">v0.2</div>
        <div class="roadmap-line"></div>
        <div>
          <div class="roadmap-content-title">Layer 2 — Detection</div>
          <div class="roadmap-content-desc">Offline detection, improved ARP spoofing, color-coded risk levels, log file saving</div>
        </div>
      </div>
      <div class="roadmap-item">
        <div class="roadmap-version">v0.3</div>
        <div class="roadmap-line"></div>
        <div>
          <div class="roadmap-content-title">Layer 3 — Alerts</div>
          <div class="roadmap-content-desc">Email/SMS alerts, device naming and tagging, export logs to CSV</div>
        </div>
      </div>
      <div class="roadmap-item">
        <div class="roadmap-version">v1.0</div>
        <div class="roadmap-line"></div>
        <div>
          <div class="roadmap-content-title">Public Release</div>
          <div class="roadmap-content-desc">Full stable release with installer, documentation, and cross-platform support</div>
        </div>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer>
    <div class="footer-logo">[SIPAR_SECURITY]</div>
    <div class="footer-links">
      <a href="https://github.com/siparsecurity" target="_blank">GitHub</a>
      <a href="https://github.com/siparsecurity/network-monitor" target="_blank">Network Monitor</a>
      <a href="https://linkedin.com/company/siparsecurity" target="_blank">LinkedIn</a>
      <a href="mailto:siparsecurity@gmail.com">Contact</a>
    </div>
    <div class="footer-copy">© 2026 Sipar Security · Built in Pakistan 🇵🇰 · MIT License</div>
  </footer>

  <script>
    // Cursor
    const cursor = document.getElementById('cursor');
    const ring = document.getElementById('cursorRing');
    document.addEventListener('mousemove', e => {
      cursor.style.left = e.clientX + 'px';
      cursor.style.top = e.clientY + 'px';
      setTimeout(() => {
        ring.style.left = e.clientX + 'px';
        ring.style.top = e.clientY + 'px';
      }, 80);
    });

    // Reveal on scroll
    const reveals = document.querySelectorAll('.reveal');
    const observer = new IntersectionObserver(entries => {
      entries.forEach((e, i) => {
        if (e.isIntersecting) {
          setTimeout(() => e.target.classList.add('visible'), i * 80);
        }
      });
    }, { threshold: 0.1 });
    reveals.forEach(r => observer.observe(r));
  </script>

</body>
</html>
