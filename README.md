<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Sipar Security</title>
  <link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@300;400;500&family=IBM+Plex+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
  <style>
    :root {
      --black: #0c0c0c;
      --white: #f5f5f0;
      --green: #00e676;
      --green-soft: rgba(0,230,118,0.08);
      --green-border: rgba(0,230,118,0.2);
      --amber: #ffb300;
      --red: #ff4444;
      --surface: #141414;
      --surface2: #1a1a1a;
      --border: #222222;
      --text: #666666;
      --text2: #999999;
      --mono: 'IBM Plex Mono', monospace;
      --sans: 'IBM Plex Sans', sans-serif;
    }

    * { margin: 0; padding: 0; box-sizing: border-box; }
    html { scroll-behavior: smooth; }

    body {
      background: var(--black);
      color: var(--white);
      font-family: var(--sans);
      line-height: 1.6;
      overflow-x: hidden;
    }

    /* NAV */
    nav {
      position: fixed;
      top: 0; left: 0; right: 0;
      z-index: 99;
      height: 56px;
      border-bottom: 1px solid var(--border);
      background: rgba(12,12,12,0.95);
      backdrop-filter: blur(10px);
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 0 2.5rem;
    }

    .nav-logo {
      font-family: var(--mono);
      font-size: 0.8rem;
      font-weight: 500;
      color: var(--white);
      letter-spacing: 0.12em;
      text-transform: uppercase;
    }

    .nav-logo em {
      color: var(--green);
      font-style: normal;
    }

    .nav-center {
      display: flex;
      gap: 2.5rem;
    }

    .nav-center a {
      font-family: var(--mono);
      font-size: 0.7rem;
      color: var(--text);
      text-decoration: none;
      letter-spacing: 0.08em;
      transition: color 0.2s;
    }

    .nav-center a:hover { color: var(--white); }

    .nav-right {
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .pulse {
      width: 6px; height: 6px;
      background: var(--green);
      border-radius: 50%;
      animation: pulse 2s ease infinite;
    }

    @keyframes pulse {
      0%,100% { opacity: 1; }
      50% { opacity: 0.3; }
    }

    .nav-status {
      font-family: var(--mono);
      font-size: 0.65rem;
      color: var(--green);
      letter-spacing: 0.1em;
    }

    /* HERO */
    .hero {
      min-height: 100vh;
      padding: 56px 0 0;
      display: grid;
      grid-template-rows: 1fr auto;
    }

    .hero-main {
      display: grid;
      grid-template-columns: 1fr 1fr;
      border-bottom: 1px solid var(--border);
    }

    .hero-left {
      padding: 5rem 4rem;
      border-right: 1px solid var(--border);
      display: flex;
      flex-direction: column;
      justify-content: center;
    }

    .label {
      font-family: var(--mono);
      font-size: 0.65rem;
      color: var(--text);
      letter-spacing: 0.2em;
      text-transform: uppercase;
      margin-bottom: 2rem;
    }

    .hero-h1 {
      font-size: clamp(3.5rem, 6vw, 6.5rem);
      font-weight: 600;
      line-height: 1;
      letter-spacing: -0.03em;
      margin-bottom: 2rem;
    }

    .hero-h1 .g { color: var(--green); }
    .hero-h1 .dim {
      color: transparent;
      -webkit-text-stroke: 1px var(--border);
    }

    .hero-p {
      font-size: 0.9rem;
      color: var(--text2);
      max-width: 380px;
      line-height: 1.8;
      margin-bottom: 2.5rem;
      font-weight: 300;
    }

    .hero-p strong { color: var(--white); font-weight: 500; }

    .btn-row { display: flex; gap: 0.75rem; flex-wrap: wrap; }

    .btn {
      font-family: var(--mono);
      font-size: 0.72rem;
      letter-spacing: 0.06em;
      padding: 0.65rem 1.4rem;
      text-decoration: none;
      transition: all 0.2s;
      display: inline-flex;
      align-items: center;
      gap: 0.4rem;
      border: 1px solid transparent;
    }

    .btn-green {
      background: var(--green);
      color: #000;
      font-weight: 500;
    }

    .btn-green:hover {
      background: transparent;
      color: var(--green);
      border-color: var(--green);
    }

    .btn-ghost {
      background: transparent;
      color: var(--text2);
      border-color: var(--border);
    }

    .btn-ghost:hover {
      color: var(--white);
      border-color: var(--text);
    }

    /* HERO RIGHT — TERMINAL */
    .hero-right {
      background: var(--surface);
      display: flex;
      flex-direction: column;
    }

    .term-bar {
      padding: 0.85rem 1.5rem;
      border-bottom: 1px solid var(--border);
      display: flex;
      align-items: center;
      gap: 0.75rem;
      background: var(--surface2);
    }

    .dots { display: flex; gap: 6px; }
    .dot { width: 10px; height: 10px; border-radius: 50%; }
    .dr { background: #ff5f57; }
    .dy { background: #febc2e; }
    .dg { background: #28c840; }

    .term-title {
      font-family: var(--mono);
      font-size: 0.68rem;
      color: var(--text);
      margin-left: auto;
    }

    .term-body {
      flex: 1;
      padding: 2rem 2rem;
      font-family: var(--mono);
      font-size: 0.78rem;
      line-height: 2;
      overflow: hidden;
    }

    .tl { display: block; }
    .tp { color: var(--green); }
    .tc { color: var(--white); }
    .td { color: #3a3a3a; padding-left: 0; }
    .tn { color: var(--green); opacity: 0.7; }
    .tw { color: var(--amber); }
    .te { color: var(--red); }
    .ti { color: #555; }

    .cur {
      display: inline-block;
      width: 7px; height: 0.9em;
      background: var(--green);
      vertical-align: text-bottom;
      animation: blink 1s step-end infinite;
    }

    @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

    /* STATS ROW */
    .stats-row {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      border-bottom: 1px solid var(--border);
    }

    .stat {
      padding: 2rem;
      border-right: 1px solid var(--border);
      position: relative;
    }

    .stat:last-child { border-right: none; }

    .stat-val {
      font-size: 2.8rem;
      font-weight: 600;
      color: var(--white);
      line-height: 1;
      letter-spacing: -0.02em;
      margin-bottom: 0.4rem;
    }

    .stat-val span { color: var(--green); }

    .stat-key {
      font-family: var(--mono);
      font-size: 0.62rem;
      color: var(--text);
      letter-spacing: 0.12em;
      text-transform: uppercase;
    }

    .stat-tag {
      position: absolute;
      top: 1rem; right: 1rem;
      font-family: var(--mono);
      font-size: 0.58rem;
      color: var(--green);
      border: 1px solid var(--green-border);
      background: var(--green-soft);
      padding: 0.15rem 0.45rem;
      letter-spacing: 0.08em;
    }

    /* SECTION */
    .section {
      max-width: 1200px;
      margin: 0 auto;
      padding: 5rem 4rem;
    }

    .section-head {
      display: flex;
      align-items: center;
      gap: 1.5rem;
      margin-bottom: 3rem;
      padding-bottom: 1.5rem;
      border-bottom: 1px solid var(--border);
    }

    .section-num {
      font-family: var(--mono);
      font-size: 0.65rem;
      color: var(--text);
      letter-spacing: 0.15em;
    }

    .section-title {
      font-size: 1.4rem;
      font-weight: 600;
      color: var(--white);
      letter-spacing: -0.01em;
    }

    /* VERSIONS */
    .versions { display: flex; flex-direction: column; gap: 1px; background: var(--border); }

    .vrow {
      background: var(--black);
      display: grid;
      grid-template-columns: 120px 1fr auto;
      gap: 0 3rem;
      padding: 2rem;
      align-items: start;
      transition: background 0.2s;
      border-left: 2px solid transparent;
    }

    .vrow:hover { background: var(--surface); }
    .vrow.v-done { border-left-color: var(--green); }
    .vrow.v-active { border-left-color: var(--amber); background: var(--surface); }
    .vrow.v-soon { border-left-color: var(--border); }

    .vrow-ver {
      font-family: var(--mono);
      font-size: 0.72rem;
      color: var(--text);
      padding-top: 0.2rem;
      letter-spacing: 0.08em;
    }

    .vrow-name {
      font-size: 1rem;
      font-weight: 600;
      color: var(--white);
      margin-bottom: 0.4rem;
      letter-spacing: -0.01em;
    }

    .vrow-desc {
      font-family: var(--mono);
      font-size: 0.72rem;
      color: var(--text);
      line-height: 1.7;
      margin-bottom: 0.75rem;
    }

    .tags { display: flex; flex-wrap: wrap; gap: 0.4rem; }

    .tag {
      font-family: var(--mono);
      font-size: 0.62rem;
      padding: 0.2rem 0.55rem;
      border: 1px solid var(--border);
      color: var(--text);
      letter-spacing: 0.04em;
    }

    .tag.green { border-color: var(--green-border); color: var(--green); background: var(--green-soft); }
    .tag.amber { border-color: rgba(255,179,0,0.25); color: var(--amber); background: rgba(255,179,0,0.06); }

    .vrow-badge {
      font-family: var(--mono);
      font-size: 0.62rem;
      padding: 0.25rem 0.7rem;
      letter-spacing: 0.08em;
      white-space: nowrap;
      align-self: start;
    }

    .badge-done { border: 1px solid var(--green-border); color: var(--green); background: var(--green-soft); }
    .badge-active { border: 1px solid rgba(255,179,0,0.3); color: var(--amber); background: rgba(255,179,0,0.06); }
    .badge-soon { border: 1px solid var(--border); color: var(--text); }

    /* FEATURES */
    .features-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1px;
      background: var(--border);
    }

    .fcard {
      background: var(--black);
      padding: 2rem;
      transition: background 0.2s;
    }

    .fcard:hover { background: var(--surface); }

    .fcard-n {
      font-family: var(--mono);
      font-size: 0.6rem;
      color: #2a2a2a;
      margin-bottom: 1.25rem;
      letter-spacing: 0.1em;
    }

    .fcard-title {
      font-size: 0.9rem;
      font-weight: 600;
      color: var(--white);
      margin-bottom: 0.5rem;
    }

    .fcard-desc {
      font-family: var(--mono);
      font-size: 0.7rem;
      color: var(--text);
      line-height: 1.75;
    }

    .fcard-badge {
      margin-top: 1rem;
      font-family: var(--mono);
      font-size: 0.6rem;
      padding: 0.18rem 0.5rem;
      display: inline-block;
      letter-spacing: 0.08em;
    }

    /* FOUNDER */
    .founder-section {
      border-top: 1px solid var(--border);
      border-bottom: 1px solid var(--border);
    }

    .founder-inner {
      max-width: 1200px;
      margin: 0 auto;
      padding: 4rem;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 4rem;
      align-items: center;
    }

    .founder-label {
      font-family: var(--mono);
      font-size: 0.65rem;
      color: var(--text);
      letter-spacing: 0.15em;
      text-transform: uppercase;
      margin-bottom: 1.5rem;
    }

    .founder-name {
      font-size: 2rem;
      font-weight: 600;
      color: var(--white);
      letter-spacing: -0.02em;
      margin-bottom: 1rem;
    }

    .founder-bio {
      font-size: 0.875rem;
      color: var(--text2);
      line-height: 1.85;
      font-weight: 300;
    }

    .founder-bio strong { color: var(--white); font-weight: 500; }

    .founder-stats {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1px;
      background: var(--border);
    }

    .fstat {
      background: var(--surface);
      padding: 1.5rem;
    }

    .fstat-val {
      font-size: 1.75rem;
      font-weight: 600;
      color: var(--white);
      letter-spacing: -0.02em;
      margin-bottom: 0.3rem;
    }

    .fstat-val span { color: var(--green); }

    .fstat-key {
      font-family: var(--mono);
      font-size: 0.62rem;
      color: var(--text);
      letter-spacing: 0.1em;
      text-transform: uppercase;
    }

    /* FOOTER */
    footer {
      border-top: 1px solid var(--border);
      display: grid;
      grid-template-columns: 2fr 1fr 1fr;
    }

    .fcol {
      padding: 3rem 2.5rem;
      border-right: 1px solid var(--border);
    }

    .fcol:last-child { border-right: none; }

    .fcol-label {
      font-family: var(--mono);
      font-size: 0.6rem;
      color: var(--text);
      letter-spacing: 0.2em;
      text-transform: uppercase;
      margin-bottom: 1.25rem;
    }

    .footer-logo {
      font-size: 1.75rem;
      font-weight: 600;
      color: var(--white);
      letter-spacing: -0.02em;
      margin-bottom: 0.75rem;
    }

    .footer-logo em { color: var(--green); font-style: normal; }

    .footer-tagline {
      font-family: var(--mono);
      font-size: 0.7rem;
      color: var(--text);
      line-height: 1.8;
      max-width: 280px;
    }

    .footer-copy {
      font-family: var(--mono);
      font-size: 0.62rem;
      color: #333;
      margin-top: 2rem;
    }

    .flinks { list-style: none; display: flex; flex-direction: column; gap: 0.65rem; }

    .flinks a {
      font-family: var(--mono);
      font-size: 0.7rem;
      color: var(--text);
      text-decoration: none;
      display: flex;
      align-items: center;
      gap: 0.5rem;
      transition: color 0.15s;
    }

    .flinks a:hover { color: var(--green); }
    .flinks a::before { content: '→'; font-size: 0.6rem; color: var(--green); }

    /* REVEAL */
    .r {
      opacity: 0;
      transform: translateY(12px);
      transition: opacity 0.5s ease, transform 0.5s ease;
    }
    .r.show { opacity: 1; transform: none; }

    @media (max-width: 900px) {
      .hero-main { grid-template-columns: 1fr; }
      .hero-right { display: none; }
      .stats-row { grid-template-columns: repeat(2,1fr); }
      .section { padding: 3rem 1.5rem; }
      .features-grid { grid-template-columns: 1fr; }
      .founder-inner { grid-template-columns: 1fr; gap: 2rem; }
      footer { grid-template-columns: 1fr; }
      .fcol { border-right: none; border-bottom: 1px solid var(--border); }
      .vrow { grid-template-columns: 1fr; gap: 0.5rem; }
      .nav-center { display: none; }
    }
  </style>
</head>
<body>

  <!-- NAV -->
  <nav>
    <div class="nav-logo">SIPAR<em>.</em>SECURITY</div>
    <div class="nav-center">
      <a href="#versions">Versions</a>
      <a href="#capabilities">Capabilities</a>
      <a href="#founder">Founder</a>
      <a href="https://github.com/siparsecurity" target="_blank">GitHub</a>
    </div>
    <div class="nav-right">
      <div class="pulse"></div>
      <div class="nav-status">V2.0 LIVE</div>
    </div>
  </nav>

  <!-- HERO -->
  <div class="hero">
    <div class="hero-main">
      <div class="hero-left">
        <div class="label">Open Source · Network Security · Pakistan 🇵🇰</div>
        <h1 class="hero-h1">
          SIPAR<br/>
          <span class="g">NETWORK</span><br/>
          <span class="dim">MONITOR</span>
        </h1>
        <p class="hero-p">
          Real-time device intelligence for <strong>home users</strong>,
          IT admins, and small businesses. Know exactly what is on your
          network — every device, every event, every threat.
        </p>
        <div class="btn-row">
          <a href="https://github.com/siparsecurity/network-monitor-v2" target="_blank" class="btn btn-green">⭐ View on GitHub</a>
          <a href="https://github.com/siparsecurity/network-monitor-v2/releases" target="_blank" class="btn btn-ghost">↓ All Releases</a>
        </div>
      </div>

      <div class="hero-right">
        <div class="term-bar">
          <div class="dots">
            <div class="dot dr"></div>
            <div class="dot dy"></div>
            <div class="dot dg"></div>
          </div>
          <div class="term-title">sipar — run_soc.py — bash</div>
        </div>
        <div class="term-body">
          <span class="tl"><span class="tp">root@kali</span><span class="ti"> ~ </span><span class="tc">sudo python3 run_soc.py</span></span>
          <span class="tl td"> </span>
          <span class="tl"><span class="tn">[+]</span><span class="tc"> Starting Sipar Security SOC...</span></span>
          <span class="tl"><span class="tn">[+]</span><span class="tc"> Event Server → 127.0.0.1:5050</span></span>
          <span class="tl"><span class="tn">[+]</span><span class="tc"> IDS scanning 192.168.1.0/24</span></span>
          <span class="tl"><span class="tn">[+]</span><span class="tc"> Scan interval: 7s · Timeout: 1s</span></span>
          <span class="tl td"> </span>
          <span class="tl"><span class="tn">[DEVICE]</span><span class="tc"> 192.168.1.1 → a4:c3:f0:12:88:de</span></span>
          <span class="tl"><span class="tn">[DEVICE]</span><span class="tc"> 192.168.1.105 → 2e:bc:72:7c:5a:d1</span></span>
          <span class="tl"><span class="tn">[DEVICE]</span><span class="tc"> 192.168.1.110 → fe:ce:a0:5a:fa:c9</span></span>
          <span class="tl td"> </span>
          <span class="tl"><span class="tw">[NEW]</span><span class="tc"> 192.168.1.201 → 4e:f1:00:37:7e:ec · risk: 5</span></span>
          <span class="tl"><span class="te">[ALERT]</span><span class="tc"> ARP_SPOOF → 192.168.1.1 · risk: 20</span></span>
          <span class="tl"><span class="tw">[OFFLINE]</span><span class="tc"> 192.168.1.110 · 3 missed scans</span></span>
          <span class="tl td"> </span>
          <span class="tl"><span class="tn">[SOC]</span><span class="tc"> Dashboard → </span><span style="color:#00b0ff">http://localhost:5000</span></span>
          <span class="tl td"> </span>
          <span class="tl"><span class="tp">root@kali</span><span class="ti"> ~ </span><span class="cur"></span></span>
        </div>
      </div>
    </div>

    <!-- STATS -->
    <div class="stats-row">
      <div class="stat">
        <div class="stat-tag">LIVE</div>
        <div class="stat-val">7<span>s</span></div>
        <div class="stat-key">Scan Interval</div>
      </div>
      <div class="stat">
        <div class="stat-val">v2<span>.0</span></div>
        <div class="stat-key">Latest Version</div>
      </div>
      <div class="stat">
        <div class="stat-val">100<span>%</span></div>
        <div class="stat-key">Open Source</div>
      </div>
      <div class="stat">
        <div class="stat-val">0<span>$</span></div>
        <div class="stat-key">Cost to Use</div>
      </div>
    </div>
  </div>

  <!-- VERSIONS -->
  <div class="section r" id="versions">
    <div class="section-head">
      <div class="section-num">01</div>
      <div class="section-title">Release History</div>
    </div>
    <div class="versions">

      <div class="vrow v-done">
        <div class="vrow-ver">v0.1 — 2026</div>
        <div>
          <div class="vrow-name">Version 1.0 — Foundation</div>
          <div class="vrow-desc">First working release. ARP scan engine, event architecture, and SOC dashboard.</div>
          <div class="tags">
            <span class="tag green">ARP Scan Engine</span>
            <span class="tag green">Event Server</span>
            <span class="tag green">SOC Dashboard</span>
            <span class="tag green">Auto Interface Detection</span>
          </div>
        </div>
        <div class="vrow-badge badge-done">RELEASED</div>
      </div>

      <div class="vrow v-active">
        <div class="vrow-ver">v0.2 — 2026</div>
        <div>
          <div class="vrow-name">Version 2.0 — Device Intelligence</div>
          <div class="vrow-desc">Major upgrade. Device schema, persistent state, offline detection, hardened ARP spoof engine, full dark SOC UI.</div>
          <div class="tags">
            <span class="tag amber">Device Schema</span>
            <span class="tag amber">Offline Detection</span>
            <span class="tag amber">ARP Spoof Cooldown</span>
            <span class="tag amber">MAC Randomization Handling</span>
            <span class="tag amber">Online/Offline Badges</span>
            <span class="tag amber">/stats API</span>
            <span class="tag amber">5 Stat Cards</span>
            <span class="tag amber">Filtered Alerts</span>
          </div>
        </div>
        <div class="vrow-badge badge-done">RELEASED</div>
      </div>

      <div class="vrow v-soon">
        <div class="vrow-ver">v0.3 — Soon</div>
        <div>
          <div class="vrow-name">Version 3.0 — Alerts</div>
          <div class="vrow-desc">Email and SMS alerts, device tagging, CSV export, port scan detection.</div>
          <div class="tags">
            <span class="tag">Email/SMS Alerts</span>
            <span class="tag">Device Tagging</span>
            <span class="tag">CSV Export</span>
            <span class="tag">Port Scan Detection</span>
          </div>
        </div>
        <div class="vrow-badge badge-soon">PLANNED</div>
      </div>

      <div class="vrow v-soon">
        <div class="vrow-ver">v1.0 — 2026</div>
        <div>
          <div class="vrow-name">Version 1.0 — Public Release</div>
          <div class="vrow-desc">Full stable release with installer, documentation, and cross-platform support.</div>
          <div class="tags">
            <span class="tag">Installer</span>
            <span class="tag">Full Docs</span>
            <span class="tag">Cross-Platform</span>
            <span class="tag">Auto-Start</span>
          </div>
        </div>
        <div class="vrow-badge badge-soon">2026</div>
      </div>

    </div>
  </div>

  <!-- CAPABILITIES -->
  <div class="section r" id="capabilities">
    <div class="section-head">
      <div class="section-num">02</div>
      <div class="section-title">Capabilities</div>
    </div>
    <div class="features-grid">
      <div class="fcard">
        <div class="fcard-n">001</div>
        <div class="fcard-title">Device Discovery</div>
        <div class="fcard-desc">ARP-based scanning captures every device on your network — MAC address, IP, first seen, last seen, and cumulative risk score.</div>
        <span class="fcard-badge badge-done">LIVE</span>
      </div>
      <div class="fcard">
        <div class="fcard-n">002</div>
        <div class="fcard-title">Real-Time Tracking</div>
        <div class="fcard-desc">Continuous 7-second scans. Online and offline status updates instantly. Every state change is logged with a timestamp.</div>
        <span class="fcard-badge badge-done">LIVE</span>
      </div>
      <div class="fcard">
        <div class="fcard-n">003</div>
        <div class="fcard-title">Offline Detection</div>
        <div class="fcard-desc">DEVICE_OFFLINE fires after 3 consecutive missed scans — avoiding false positives from slow ARP responses or brief disconnections.</div>
        <span class="fcard-badge badge-done">v2.0</span>
      </div>
      <div class="fcard">
        <div class="fcard-n">004</div>
        <div class="fcard-title">ARP Spoof Detection</div>
        <div class="fcard-desc">MAC history tracking with cooldown timer and 60-second randomization window. No false positives from modern phones.</div>
        <span class="fcard-badge badge-done">v2.0</span>
      </div>
      <div class="fcard">
        <div class="fcard-n">005</div>
        <div class="fcard-title">SOC Dashboard</div>
        <div class="fcard-desc">Full dark SOC interface. 5 stat cards, filtered alerts panel, online/offline badges, risk color coding. Refreshes every 5 seconds.</div>
        <span class="fcard-badge badge-done">LIVE</span>
      </div>
      <div class="fcard">
        <div class="fcard-n">006</div>
        <div class="fcard-title">Persistent Logging</div>
        <div class="fcard-desc">All events saved to disk as JSONL. Full device state reconstructed on every restart. Zero data loss between sessions.</div>
        <span class="fcard-badge badge-done">v2.0</span>
      </div>
    </div>
  </div>

  <!-- FOUNDER -->
  <div class="founder-section r" id="founder">
    <div class="founder-inner">
      <div>
        <div class="founder-label">Founder</div>
        <div class="founder-name">Sayed Muhammad Subayyal</div>
        <p class="founder-bio">
          17-year-old ethical hacker and security researcher from
          <strong>Peshawar, Pakistan</strong>. Founder of Sipar Security.
          Currently studying at <strong>Islamia College Peshawar</strong>
          while actively building open-source cybersecurity tools.<br/><br/>
          Reported verified vulnerabilities to organizations including
          <strong>NASA</strong> through responsible disclosure.
          Published researcher — among the top 1% of authors
          published under 18 globally. Teaching an ethical hacking
          course on Kali Linux.
        </p>
      </div>
      <div class="founder-stats">
        <div class="fstat">
          <div class="fstat-val">17<span>yrs</span></div>
          <div class="fstat-key">Age</div>
        </div>
        <div class="fstat">
          <div class="fstat-val">2<span>+</span></div>
          <div class="fstat-key">Tools Released</div>
        </div>
        <div class="fstat">
          <div class="fstat-val">1<span>%</span></div>
          <div class="fstat-key">Research Author Under 18</div>
        </div>
        <div class="fstat">
          <div class="fstat-val">PK<span> 🇵🇰</span></div>
          <div class="fstat-key">Pakistan</div>
        </div>
      </div>
    </div>
  </div>

  <!-- FOOTER -->
  <footer>
    <div class="fcol">
      <div class="fcol-label">Company</div>
      <div class="footer-logo">SIPAR<em>.</em>SECURITY</div>
      <div class="footer-tagline">Open-source network security tools built in Pakistan. Real visibility for everyone — no enterprise budget required.</div>
      <div class="footer-copy">© 2026 Sipar Security · MIT License · Built in Pakistan 🇵🇰</div>
    </div>
    <div class="fcol">
      <div class="fcol-label">Projects</div>
      <ul class="flinks">
        <li><a href="https://github.com/siparsecurity/network-monitor" target="_blank">Network Monitor v1.0</a></li>
        <li><a href="https://github.com/siparsecurity/network-monitor-v2" target="_blank">Network Monitor v2.0</a></li>
        <li><a href="https://github.com/siparsecurity/network-monitor-v2/releases" target="_blank">All Releases</a></li>
        <li><a href="https://github.com/siparsecurity" target="_blank">GitHub Organization</a></li>
      </ul>
    </div>
    <div class="fcol">
      <div class="fcol-label">Contact</div>
      <ul class="flinks">
        <li><a href="mailto:siparsecurity@gmail.com">siparsecurity@gmail.com</a></li>
        <li><a href="https://linkedin.com/company/siparsecurity" target="_blank">LinkedIn</a></li>
        <li><a href="https://x.com/SiparSecurity" target="_blank">X / Twitter</a></li>
        <li><a href="https://github.com/siparsecurity" target="_blank">GitHub</a></li>
      </ul>
    </div>
  </footer>

  <script>
    const els = document.querySelectorAll('.r');
    const obs = new IntersectionObserver(entries => {
      entries.forEach((e, i) => {
        if (e.isIntersecting) setTimeout(() => e.target.classList.add('show'), i * 80);
      });
    }, { threshold: 0.06 });
    els.forEach(e => obs.observe(e));
  </script>

</body>
</html>
