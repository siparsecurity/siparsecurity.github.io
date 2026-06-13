
<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Sipar Security — Network Security Tools</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=IBM+Plex+Mono:wght@400;500&display=swap" rel="stylesheet">
  <style>
    :root {
      --black: #0a0a0a;
      --white: #ffffff;
      --off: #f5f5f3;
      --text: #555;
      --light: #999;
      --border: #e8e8e8;
      --green: #16a34a;
      --green-bg: #f0fdf4;
      --green-bd: #bbf7d0;
      --amber: #b45309;
      --amber-bg: #fffbeb;
      --amber-bd: #fde68a;
      --red: #dc2626;
      --mono: 'IBM Plex Mono', monospace;
      --sans: 'Inter', sans-serif;
    }

    * { margin: 0; padding: 0; box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body {
      font-family: var(--sans);
      background: var(--white);
      color: var(--black);
      -webkit-font-smoothing: antialiased;
    }

    /* NAV */
    nav {
      position: sticky; top: 0; z-index: 99;
      background: rgba(255,255,255,0.96);
      backdrop-filter: blur(8px);
      border-bottom: 1px solid var(--border);
      height: 62px;
      display: flex; align-items: center;
      justify-content: space-between;
      padding: 0 2.5rem;
    }
    .nav-logo {
      font-family: var(--mono);
      font-size: 0.82rem; font-weight: 500;
      color: var(--black); text-decoration: none;
      letter-spacing: 0.06em;
    }
    .nav-links { display: flex; gap: 2rem; list-style: none; }
    .nav-links a {
      font-size: 0.84rem; color: var(--text);
      text-decoration: none; transition: color 0.15s;
    }
    .nav-links a:hover { color: var(--black); }
    .nav-btn {
      font-size: 0.82rem; font-weight: 600;
      background: var(--black); color: #fff;
      padding: 0.5rem 1.25rem;
      text-decoration: none; transition: opacity 0.15s;
    }
    .nav-btn:hover { opacity: 0.8; }

    /* HERO */
    .hero {
      padding: 7rem 2rem 6rem;
      text-align: center;
      max-width: 820px; margin: 0 auto;
    }
    .hero-badge {
      display: inline-flex; align-items: center; gap: 0.5rem;
      font-family: var(--mono); font-size: 0.7rem;
      color: var(--green); background: var(--green-bg);
      border: 1px solid var(--green-bd);
      padding: 0.3rem 0.85rem; margin-bottom: 2rem;
      letter-spacing: 0.04em;
    }
    .hero-badge::before {
      content: ''; width: 6px; height: 6px;
      background: var(--green); border-radius: 50%;
      animation: blink 2s ease infinite;
    }
    @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0.3} }

    .hero h1 {
      font-size: clamp(2.4rem, 6vw, 4rem);
      font-weight: 700; line-height: 1.1;
      letter-spacing: -0.03em; color: var(--black);
      margin-bottom: 1.5rem;
    }
    .hero h1 em { font-style: normal; color: var(--green); }

    .hero p {
      font-size: 1.05rem; color: var(--text);
      line-height: 1.8; font-weight: 300;
      max-width: 520px; margin: 0 auto 2.75rem;
    }

    .hero-btns { display: flex; gap: 0.75rem; justify-content: center; flex-wrap: wrap; }
    .btn {
      font-size: 0.88rem; font-weight: 500;
      padding: 0.75rem 1.6rem; text-decoration: none;
      display: inline-flex; align-items: center; gap: 0.4rem;
      transition: all 0.15s;
    }
    .btn-black { background: var(--black); color: #fff; }
    .btn-black:hover { opacity: 0.85; }
    .btn-border { border: 1.5px solid var(--border); color: var(--text); background: #fff; }
    .btn-border:hover { border-color: #aaa; color: var(--black); }

    /* TICKER */
    .ticker {
      border-top: 1px solid var(--border);
      border-bottom: 1px solid var(--border);
      background: var(--black); color: #fff;
      padding: 0.85rem 0; overflow: hidden;
    }
    .ticker-inner {
      display: flex; gap: 4rem;
      white-space: nowrap;
      animation: ticker 18s linear infinite;
      font-family: var(--mono); font-size: 0.72rem;
      color: #888; letter-spacing: 0.08em;
    }
    .ticker-inner span { color: var(--green); }
    @keyframes ticker { 0%{transform:translateX(0)} 100%{transform:translateX(-50%)} }

    /* STATS */
    .stats {
      display: grid; grid-template-columns: repeat(4,1fr);
      border-bottom: 1px solid var(--border);
    }
    .stat {
      padding: 2.75rem 2rem; text-align: center;
      border-right: 1px solid var(--border);
    }
    .stat:last-child { border-right: none; }
    .stat-n {
      font-size: 2.4rem; font-weight: 700;
      color: var(--black); letter-spacing: -0.02em;
      line-height: 1; margin-bottom: 0.4rem;
    }
    .stat-n em { font-style: normal; color: var(--green); }
    .stat-l { font-size: 0.78rem; color: var(--light); }

    /* SECTION */
    .sec { max-width: 960px; margin: 0 auto; padding: 5.5rem 2rem; }
    .sec-sub {
      font-family: var(--mono); font-size: 0.68rem;
      color: var(--light); letter-spacing: 0.14em;
      text-transform: uppercase; margin-bottom: 0.6rem;
    }
    .sec-title {
      font-size: clamp(1.5rem, 3vw, 2rem);
      font-weight: 700; letter-spacing: -0.02em;
      color: var(--black); margin-bottom: 0.85rem;
    }
    .sec-desc {
      font-size: 0.9rem; color: var(--text);
      line-height: 1.8; font-weight: 300;
      max-width: 520px; margin-bottom: 3rem;
    }

    /* VERSIONS */
    .versions { border: 1px solid var(--border); border-radius: 6px; overflow: hidden; }
    .vrow {
      display: grid; grid-template-columns: 110px 1fr auto;
      gap: 0 2.5rem; padding: 2rem 2.5rem;
      border-bottom: 1px solid var(--border);
      align-items: start; transition: background 0.15s;
    }
    .vrow:last-child { border-bottom: none; }
    .vrow:hover { background: var(--off); }
    .vrow.current { background: #fafffe; border-left: 3px solid var(--green); }
    .v-ver { font-family: var(--mono); font-size: 0.7rem; color: var(--light); padding-top: 0.2rem; }
    .v-name { font-size: 0.95rem; font-weight: 700; color: var(--black); margin-bottom: 0.3rem; }
    .v-desc { font-size: 0.82rem; color: var(--text); line-height: 1.65; margin-bottom: 0.85rem; font-weight: 300; }
    .v-tags { display: flex; flex-wrap: wrap; gap: 0.35rem; }
    .vtag {
      font-family: var(--mono); font-size: 0.6rem;
      padding: 0.18rem 0.55rem; border-radius: 3px;
    }
    .vt-g { background: var(--green-bg); color: var(--green); border: 1px solid var(--green-bd); }
    .vt-a { background: var(--amber-bg); color: var(--amber); border: 1px solid var(--amber-bd); }
    .vt-n { background: var(--off); color: var(--light); border: 1px solid var(--border); }
    .v-badge {
      font-family: var(--mono); font-size: 0.62rem;
      padding: 0.25rem 0.7rem; border-radius: 3px;
      font-weight: 500; white-space: nowrap; align-self: start;
    }
    .vb-g { background: var(--green-bg); color: var(--green); border: 1px solid var(--green-bd); }
    .vb-a { background: var(--amber-bg); color: var(--amber); border: 1px solid var(--amber-bd); }
    .vb-n { background: var(--off); color: var(--light); border: 1px solid var(--border); }

    /* FEATURES */
    .fgrid {
      display: grid; grid-template-columns: repeat(3,1fr);
      gap: 1px; background: var(--border);
      border: 1px solid var(--border); border-radius: 6px; overflow: hidden;
    }
    .fcard {
      background: #fff; padding: 2rem;
      transition: background 0.15s;
    }
    .fcard:hover { background: var(--off); }
    .fcard-n { font-family: var(--mono); font-size: 0.6rem; color: #ddd; margin-bottom: 1rem; }
    .fcard-t { font-size: 0.9rem; font-weight: 700; color: var(--black); margin-bottom: 0.5rem; }
    .fcard-d { font-size: 0.8rem; color: var(--text); line-height: 1.7; font-weight: 300; }
    .fcard-v { margin-top: 1rem; font-family: var(--mono); font-size: 0.6rem; color: var(--light); }

    /* PLATFORM */
    .platform-table {
      width: 100%; border-collapse: collapse;
      border: 1px solid var(--border); border-radius: 6px; overflow: hidden;
    }
    .platform-table th {
      background: var(--black); color: #fff;
      font-family: var(--mono); font-size: 0.68rem;
      letter-spacing: 0.08em; padding: 1rem 1.5rem;
      text-align: left; font-weight: 500;
    }
    .platform-table td {
      padding: 1rem 1.5rem; font-size: 0.84rem;
      color: var(--text); border-bottom: 1px solid var(--border);
    }
    .platform-table tr:last-child td { border-bottom: none; }
    .platform-table tr:hover td { background: var(--off); }
    .yes { color: var(--green); font-weight: 600; }
    .no { color: var(--red); }
    .partial { color: var(--amber); font-weight: 500; }

    /* FOUNDER */
    .founder-wrap {
      background: var(--off);
      border-top: 1px solid var(--border);
      border-bottom: 1px solid var(--border);
    }
    .founder-inner {
      max-width: 960px; margin: 0 auto;
      padding: 5.5rem 2rem;
      display: grid; grid-template-columns: 1.2fr 1fr;
      gap: 5rem; align-items: start;
    }
    .founder-sub { font-family: var(--mono); font-size: 0.68rem; color: var(--light); letter-spacing: 0.14em; text-transform: uppercase; margin-bottom: 1rem; }
    .founder-name { font-size: 1.5rem; font-weight: 700; color: var(--black); letter-spacing: -0.02em; margin-bottom: 0.25rem; }
    .founder-role { font-size: 0.82rem; color: var(--light); margin-bottom: 1.75rem; }
    .founder-bio { font-size: 0.86rem; color: var(--text); line-height: 1.9; font-weight: 300; margin-bottom: 1.75rem; }
    .founder-paper {
      background: #fff; border: 1px solid var(--border);
      border-left: 3px solid var(--black);
      padding: 1rem 1.25rem; margin-bottom: 1.75rem;
    }
    .paper-sub { font-family: var(--mono); font-size: 0.6rem; color: var(--light); letter-spacing: 0.1em; text-transform: uppercase; margin-bottom: 0.4rem; }
    .paper-t { font-size: 0.82rem; font-weight: 500; color: var(--black); line-height: 1.5; margin-bottom: 0.25rem; }
    .paper-j { font-size: 0.75rem; color: var(--light); }
    .tags { display: flex; flex-wrap: wrap; gap: 0.4rem; }
    .itag { font-family: var(--mono); font-size: 0.6rem; padding: 0.2rem 0.6rem; background: #fff; border: 1px solid var(--border); color: var(--text); border-radius: 3px; }

    .fstats { display: grid; grid-template-columns: 1fr 1fr; gap: 1px; background: var(--border); border: 1px solid var(--border); border-radius: 6px; overflow: hidden; }
    .fstat { background: #fff; padding: 1.75rem; }
    .fstat-n { font-size: 1.8rem; font-weight: 700; color: var(--black); letter-spacing: -0.02em; margin-bottom: 0.25rem; }
    .fstat-l { font-size: 0.75rem; color: var(--light); }

    /* CTA BAND */
    .cta-band {
      background: var(--black); color: #fff;
      padding: 5rem 2rem; text-align: center;
    }
    .cta-band h2 {
      font-size: clamp(1.6rem, 4vw, 2.4rem);
      font-weight: 700; letter-spacing: -0.02em;
      margin-bottom: 1rem; max-width: 560px;
      margin-left: auto; margin-right: auto;
    }
    .cta-band p {
      font-size: 0.9rem; color: #777;
      line-height: 1.8; font-weight: 300;
      max-width: 420px; margin: 0 auto 2.5rem;
    }
    .cta-btn {
      display: inline-block; background: #fff;
      color: var(--black); font-size: 0.9rem;
      font-weight: 700; padding: 0.85rem 2.25rem;
      text-decoration: none; transition: opacity 0.15s;
    }
    .cta-btn:hover { opacity: 0.9; }
    .cta-sub { display: block; margin-top: 1rem; font-family: var(--mono); font-size: 0.65rem; color: #444; }

    /* FOOTER */
    footer { border-top: 1px solid var(--border); }
    .footer-inner {
      max-width: 960px; margin: 0 auto;
      padding: 3rem 2rem;
      display: grid; grid-template-columns: 2fr 1fr 1fr;
      gap: 3rem;
    }
    .footer-logo { font-family: var(--mono); font-size: 0.82rem; font-weight: 500; color: var(--black); margin-bottom: 0.75rem; }
    .footer-tag { font-size: 0.82rem; color: var(--text); line-height: 1.7; font-weight: 300; max-width: 240px; margin-bottom: 1.5rem; }
    .footer-copy { font-size: 0.72rem; color: var(--light); }
    .footer-h { font-size: 0.8rem; font-weight: 600; color: var(--black); margin-bottom: 1rem; }
    .footer-links { list-style: none; display: flex; flex-direction: column; gap: 0.6rem; }
    .footer-links a { font-size: 0.82rem; color: var(--text); text-decoration: none; transition: color 0.15s; }
    .footer-links a:hover { color: var(--black); }

    /* REVEAL */
    .r { opacity: 0; transform: translateY(10px); transition: opacity 0.45s ease, transform 0.45s ease; }
    .r.on { opacity: 1; transform: none; }

    /* RESPONSIVE */
    @media (max-width: 800px) {
      nav { padding: 0 1.25rem; }
      .nav-links { display: none; }
      .hero { padding: 5rem 1.25rem 4rem; }
      .stats { grid-template-columns: repeat(2,1fr); }
      .stat:nth-child(2) { border-right: none; }
      .stat:nth-child(3) { border-top: 1px solid var(--border); }
      .stat:nth-child(4) { border-right: none; border-top: 1px solid var(--border); }
      .sec { padding: 3.5rem 1.25rem; }
      .vrow { grid-template-columns: 1fr; gap: 0.5rem; }
      .fgrid { grid-template-columns: 1fr 1fr; }
      .founder-inner { grid-template-columns: 1fr; gap: 2.5rem; padding: 3.5rem 1.25rem; }
      .footer-inner { grid-template-columns: 1fr; gap: 2rem; padding: 2.5rem 1.25rem; }
      .cta-band { padding: 3.5rem 1.25rem; }
    }
    @media (max-width: 500px) {
      .hero h1 { font-size: 2rem; }
      .hero-btns { flex-direction: column; align-items: center; }
      .btn { width: 100%; max-width: 280px; justify-content: center; }
      .fgrid { grid-template-columns: 1fr; }
      .platform-table th, .platform-table td { padding: 0.75rem 1rem; }
    }
  </style>
</head>
<body>

<!-- NAV -->
<nav>
  <a href="/" class="nav-logo">SIPAR SECURITY</a>
  <ul class="nav-links">
    <li><a href="#versions">Versions</a></li>
    <li><a href="#capabilities">Capabilities</a></li>
    <li><a href="#founder">About</a></li>
    <li><a href="/services.html">Services</a></li>
  </ul>
  <a href="https://github.com/siparsecurity/network-monitor-v3" target="_blank" class="nav-btn">View on GitHub →</a>
</nav>

<!-- HERO -->
<div class="hero r">
  <div class="hero-badge">v3.0 Released · Open Source · Free Forever</div>
  <h1>Know <em>exactly</em> what is happening on your network.</h1>
  <p>Sipar Security builds open-source network intrusion detection tools for home users, IT admins, and small businesses. Real-time. Free. Built in Pakistan.</p>
  <div class="hero-btns">
    <a href="https://github.com/siparsecurity/network-monitor-v3" target="_blank" class="btn btn-black">⭐ Get the Tool Free</a>
    <a href="/services.html" class="btn btn-border">Our Services →</a>
  </div>
</div>

<!-- TICKER -->
<div class="ticker">
  <div class="ticker-inner">
    <span>NEW DEVICE DETECTED</span> · 192.168.1.201 ·
    <span>ARP SPOOF — HIGH CONFIDENCE</span> · 192.168.1.1 ·
    <span>PORT SCAN DETECTED</span> · 192.168.1.45 ·
    <span>ROGUE DEVICE FLAGGED</span> · 192.168.1.88 ·
    <span>THREAT LEVEL: CRITICAL</span> · 192.168.1.3 ·
    <span>DEVICE OFFLINE</span> · 192.168.1.110 ·
    <span>RISK DECAY</span> · 192.168.1.7 ·
    <!-- duplicate for seamless loop -->
    <span>NEW DEVICE DETECTED</span> · 192.168.1.201 ·
    <span>ARP SPOOF — HIGH CONFIDENCE</span> · 192.168.1.1 ·
    <span>PORT SCAN DETECTED</span> · 192.168.1.45 ·
    <span>ROGUE DEVICE FLAGGED</span> · 192.168.1.88 ·
    <span>THREAT LEVEL: CRITICAL</span> · 192.168.1.3 ·
    <span>DEVICE OFFLINE</span> · 192.168.1.110 ·
    <span>RISK DECAY</span> · 192.168.1.7 ·
  </div>
</div>

<!-- STATS -->
<div class="stats r">
  <div class="stat">
    <div class="stat-n">3<em>.0</em></div>
    <div class="stat-l">Latest Version</div>
  </div>
  <div class="stat">
    <div class="stat-n">7<em>s</em></div>
    <div class="stat-l">Scan Interval</div>
  </div>
  <div class="stat">
    <div class="stat-n">100<em>%</em></div>
    <div class="stat-l">Open Source</div>
  </div>
  <div class="stat">
    <div class="stat-n">0<em>$</em></div>
    <div class="stat-l">Cost to Use</div>
  </div>
</div>

<!-- VERSIONS -->
<div class="sec r" id="versions">
  <div class="sec-sub">Release History</div>
  <div class="sec-title">Three versions. Each one better.</div>
  <div class="sec-desc">Every version is publicly available. Download any version from GitHub.</div>

  <div class="versions">

    <div class="vrow">
      <div class="v-ver">v1.0 — 2026</div>
      <div>
        <div class="v-name">Version 1.0 — Foundation</div>
        <div class="v-desc">First public release. ARP scan engine, event server, persistent logging, SOC dashboard, and auto interface detection.</div>
        <div class="v-tags">
          <span class="vtag vt-g">ARP Scanning</span>
          <span class="vtag vt-g">SOC Dashboard</span>
          <span class="vtag vt-g">Event Server</span>
          <span class="vtag vt-g">Persistent Logging</span>
        </div>
      </div>
      <div class="v-badge vb-g">Released</div>
    </div>

    <div class="vrow">
      <div class="v-ver">v2.0 — 2026</div>
      <div>
        <div class="v-name">Version 2.0 — Device Intelligence</div>
        <div class="v-desc">Device schema with first/last seen, offline detection after 3 missed scans, ARP spoof cooldown, MAC randomization handling, and upgraded dashboard.</div>
        <div class="v-tags">
          <span class="vtag vt-g">Device Schema</span>
          <span class="vtag vt-g">Offline Detection</span>
          <span class="vtag vt-g">ARP Spoof Cooldown</span>
          <span class="vtag vt-g">MAC Randomization Handling</span>
          <span class="vtag vt-g">/stats API</span>
        </div>
      </div>
      <div class="v-badge vb-g">Released</div>
    </div>

    <div class="vrow current">
      <div class="v-ver">v3.0 — 2026</div>
      <div>
        <div class="v-name">Version 3.0 — Attack Detection</div>
        <div class="v-desc">Full attack detection engine. Confidence-scored ARP spoof, duplicate MAC detection, port scan detection, rogue device flagging, threat levels, risk decay, and cross-platform support for Linux, Windows, and Android.</div>
        <div class="v-tags">
          <span class="vtag vt-g">ARP Spoof Confidence Scoring</span>
          <span class="vtag vt-g">Duplicate MAC Detection</span>
          <span class="vtag vt-g">Port Scan Detection</span>
          <span class="vtag vt-g">Rogue Device Detection</span>
          <span class="vtag vt-g">LOW/MEDIUM/HIGH/CRITICAL</span>
          <span class="vtag vt-g">Risk Decay</span>
          <span class="vtag vt-g">Linux · Windows · Android</span>
        </div>
      </div>
      <div class="v-badge vb-g">Latest</div>
    </div>

  </div>
</div>

<!-- CAPABILITIES -->
<div class="sec r" id="capabilities" style="padding-top:0;">
  <div class="sec-sub">Capabilities</div>
  <div class="sec-title">What it detects. What it shows. What it stops.</div>
  <div class="sec-desc">All features available in Version 3.0.</div>

  <div class="fgrid">
    <div class="fcard">
      <div class="fcard-n">001</div>
      <div class="fcard-t">Device Discovery</div>
      <div class="fcard-d">ARP-based scanning finds every device — MAC, IP, first seen, last seen, cumulative risk score. Nothing stays hidden.</div>
      <div class="fcard-v">v1.0 +</div>
    </div>
    <div class="fcard">
      <div class="fcard-n">002</div>
      <div class="fcard-t">Real-Time Tracking</div>
      <div class="fcard-d">7-second scan cycles. Online and offline status updates the moment something changes. Every event timestamped.</div>
      <div class="fcard-v">v1.0 +</div>
    </div>
    <div class="fcard">
      <div class="fcard-n">003</div>
      <div class="fcard-t">ARP Spoof Detection</div>
      <div class="fcard-d">Confidence-scored detection — LOW, MEDIUM, HIGH. Cooldown timer prevents spam. 60-second MAC randomization window eliminates false positives.</div>
      <div class="fcard-v">v3.0</div>
    </div>
    <div class="fcard">
      <div class="fcard-n">004</div>
      <div class="fcard-t">Port Scan Detection</div>
      <div class="fcard-d">Background thread watches for one IP probing multiple ports rapidly. Five distinct ports in 10 seconds triggers an alert.</div>
      <div class="fcard-v">v3.0</div>
    </div>
    <div class="fcard">
      <div class="fcard-n">005</div>
      <div class="fcard-t">Duplicate MAC Detection</div>
      <div class="fcard-d">Same MAC address on two different IPs simultaneously — instantly flagged. A signature pattern of spoofing and impersonation attacks.</div>
      <div class="fcard-v">v3.0</div>
    </div>
    <div class="fcard">
      <div class="fcard-n">006</div>
      <div class="fcard-t">Rogue Device Detection</div>
      <div class="fcard-d">Establishes a trusted baseline on first scan. Any device that joins after that baseline is flagged as unknown immediately.</div>
      <div class="fcard-v">v3.0</div>
    </div>
    <div class="fcard">
      <div class="fcard-n">007</div>
      <div class="fcard-t">Threat Level System</div>
      <div class="fcard-d">Every device scored LOW, MEDIUM, HIGH, or CRITICAL based on real activity. Risk decays automatically when a device stays clean.</div>
      <div class="fcard-v">v3.0</div>
    </div>
    <div class="fcard">
      <div class="fcard-n">008</div>
      <div class="fcard-t">SOC Dashboard</div>
      <div class="fcard-d">6 stat cards, threat badges, filtered alert panel, risk reset button, color-coded events. Accessible from any browser on the same network.</div>
      <div class="fcard-v">v1.0 +</div>
    </div>
    <div class="fcard">
      <div class="fcard-n">009</div>
      <div class="fcard-t">Persistent Logging</div>
      <div class="fcard-d">Every event saved to disk as JSONL. Full device state rebuilt on every restart. Zero data loss between sessions.</div>
      <div class="fcard-v">v2.0 +</div>
    </div>
  </div>
</div>

<!-- PLATFORM -->
<div class="sec r" style="padding-top:0;">
  <div class="sec-sub">Platform Support</div>
  <div class="sec-title">Runs everywhere.</div>
  <div class="sec-desc">One command to install. One command to run. Dashboard accessible from any browser on the same network — phone, tablet, laptop.</div>

  <table class="platform-table">
    <thead>
      <tr>
        <th>Platform</th>
        <th>Run the Tool</th>
        <th>View Dashboard</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Kali Linux</td>
        <td class="yes">✓ Full support</td>
        <td class="yes">✓</td>
      </tr>
      <tr>
        <td>Ubuntu / Debian</td>
        <td class="yes">✓ Full support</td>
        <td class="yes">✓</td>
      </tr>
      <tr>
        <td>Windows 10 / 11</td>
        <td class="partial">✓ Requires Npcap</td>
        <td class="yes">✓</td>
      </tr>
      <tr>
        <td>Termux — Rooted Android</td>
        <td class="yes">✓ Full support</td>
        <td class="yes">✓</td>
      </tr>
      <tr>
        <td>Termux — Not Rooted</td>
        <td class="no">✗ Root required for scanning</td>
        <td class="yes">✓ Browser only</td>
      </tr>
      <tr>
        <td>Any phone / tablet browser</td>
        <td class="no">✗</td>
        <td class="yes">✓ Same WiFi, no setup</td>
      </tr>
    </tbody>
  </table>
</div>

<!-- FOUNDER -->
<div class="founder-wrap r" id="founder">
  <div class="founder-inner">
    <div>
      <div class="founder-sub">Founder</div>
      <div class="founder-name">Sayed Muhammad Subayyal</div>
      <div class="founder-role">Cybersecurity Researcher · Penetration Tester · Founder, Sipar Security</div>
      <p class="founder-bio">
        Cybersecurity researcher and penetration tester focused on network security,
        wireless security, vulnerability assessment, and open-source security tool
        development. Works with Linux environments, particularly Kali Linux, applying
        structured methodologies for security testing and defensive assessments.<br/><br/>
        Actively contributes to the cybersecurity community through vulnerability
        disclosure, open-source development, and academic research. Currently
        studying at Islamia College Peshawar.
      </p>
      <div class="founder-paper">
        <div class="paper-sub">Published Research · 2026</div>
        <div class="paper-t">Simulating and Mitigating Rogue Access Point Attacks in Wi-Fi Networks Using Open-Source Tools</div>
        <div class="paper-j">Journal of Soft Computing and Artificial Intelligence</div>
      </div>
      <div class="tags">
        <span class="itag">Network Security</span>
        <span class="itag">Penetration Testing</span>
        <span class="itag">Wireless Security</span>
        <span class="itag">Ethical Hacking</span>
        <span class="itag">Kali Linux</span>
        <span class="itag">Python</span>
        <span class="itag">Open-Source Tools</span>
        <span class="itag">Vulnerability Assessment</span>
        <span class="itag">Defensive Security</span>
      </div>
    </div>
    <div>
      <div class="fstats">
        <div class="fstat">
          <div class="fstat-n">17</div>
          <div class="fstat-l">Years old</div>
        </div>
        <div class="fstat">
          <div class="fstat-n">3</div>
          <div class="fstat-l">Versions released</div>
        </div>
        <div class="fstat">
          <div class="fstat-n">1</div>
          <div class="fstat-l">Published paper</div>
        </div>
        <div class="fstat">
          <div class="fstat-n">PK 🇵🇰</div>
          <div class="fstat-l">Pakistan</div>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- CTA -->
<div class="cta-band r">
  <h2>Need help securing your network?</h2>
  <p>We offer professional network security audits, penetration testing, and monitoring setup. First consultation is free.</p>
  <a href="/services.html" class="cta-btn">See Our Services →</a>
  <span class="cta-sub">Or email us directly — siparsecurity@gmail.com</span>
</div>

<!-- FOOTER -->
<footer>
  <div class="footer-inner">
    <div>
      <div class="footer-logo">SIPAR SECURITY</div>
      <p class="footer-tag">Open-source network security tools built in Pakistan. Free for everyone — no enterprise budget required.</p>
      <div class="footer-copy">© 2026 Sipar Security · MIT License · Pakistan 🇵🇰</div>
    </div>
    <div>
      <div class="footer-h">Projects</div>
      <ul class="footer-links">
        <li><a href="https://github.com/siparsecurity/network-monitor-v3" target="_blank">Network Monitor v3.0</a></li>
        <li><a href="https://github.com/siparsecurity/network-monitor-v2" target="_blank">Network Monitor v2.0</a></li>
        <li><a href="https://github.com/siparsecurity/network-monitor" target="_blank">Network Monitor v1.0</a></li>
        <li><a href="https://github.com/siparsecurity" target="_blank">GitHub Organization</a></li>
      </ul>
    </div>
    <div>
      <div class="footer-h">Contact</div>
      <ul class="footer-links">
        <li><a href="mailto:siparsecurity@gmail.com">siparsecurity@gmail.com</a></li>
        <li><a href="/services.html">Services</a></li>
        <li><a href="https://linkedin.com/company/siparsecurity" target="_blank">LinkedIn</a></li>
        <li><a href="https://x.com/SiparSecurity" target="_blank">X / Twitter</a></li>
      </ul>
    </div>
  </div>
</footer>

<script>
  const els = document.querySelectorAll('.r');
  const obs = new IntersectionObserver(entries => {
    entries.forEach((e,i) => {
      if(e.isIntersecting) setTimeout(()=>e.target.classList.add('on'), i*60);
    });
  }, {threshold:0.05});
  els.forEach(e=>obs.observe(e));
</script>

</body>
</html>
