<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Sipar Security</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&family=IBM+Plex+Mono:wght@400;500&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg: #ffffff;
      --black: #0f0f0f;
      --text: #444444;
      --text-light: #888888;
      --border: #e5e5e5;
      --surface: #f8f8f8;
      --accent: #0f0f0f;
      --green: #16a34a;
      --amber: #b45309;
      --mono: 'IBM Plex Mono', monospace;
      --sans: 'Inter', sans-serif;
    }

    * { margin: 0; padding: 0; box-sizing: border-box; }
    html { scroll-behavior: smooth; }

    body {
      background: var(--bg);
      color: var(--black);
      font-family: var(--sans);
      line-height: 1.6;
      -webkit-font-smoothing: antialiased;
    }

    /* NAV */
    nav {
      position: sticky;
      top: 0;
      z-index: 99;
      background: #fff;
      border-bottom: 1px solid var(--border);
      padding: 0 2rem;
      height: 60px;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .nav-logo {
      font-family: var(--mono);
      font-size: 0.85rem;
      font-weight: 500;
      color: var(--black);
      letter-spacing: 0.05em;
      text-decoration: none;
    }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 2rem;
      list-style: none;
    }

    .nav-links a {
      font-size: 0.85rem;
      color: var(--text);
      text-decoration: none;
      transition: color 0.15s;
    }

    .nav-links a:hover { color: var(--black); }

    .nav-cta {
      font-size: 0.82rem;
      font-weight: 500;
      background: var(--black);
      color: #fff;
      padding: 0.5rem 1.1rem;
      text-decoration: none;
      transition: opacity 0.15s;
    }

    .nav-cta:hover { opacity: 0.85; }

    /* HERO */
    .hero {
      max-width: 760px;
      margin: 0 auto;
      padding: 6rem 2rem 5rem;
      text-align: center;
    }

    .hero-tag {
      display: inline-block;
      font-family: var(--mono);
      font-size: 0.72rem;
      color: var(--green);
      background: #f0fdf4;
      border: 1px solid #bbf7d0;
      padding: 0.3rem 0.8rem;
      margin-bottom: 2rem;
      letter-spacing: 0.05em;
    }

    .hero h1 {
      font-size: clamp(2.2rem, 5vw, 3.5rem);
      font-weight: 600;
      color: var(--black);
      line-height: 1.15;
      letter-spacing: -0.02em;
      margin-bottom: 1.5rem;
    }

    .hero p {
      font-size: 1rem;
      color: var(--text);
      max-width: 520px;
      margin: 0 auto 2.5rem;
      line-height: 1.75;
      font-weight: 300;
    }

    .hero-actions {
      display: flex;
      gap: 0.75rem;
      justify-content: center;
      flex-wrap: wrap;
    }

    .btn {
      font-size: 0.85rem;
      font-weight: 500;
      padding: 0.65rem 1.4rem;
      text-decoration: none;
      transition: all 0.15s;
      display: inline-flex;
      align-items: center;
      gap: 0.4rem;
    }

    .btn-dark {
      background: var(--black);
      color: #fff;
    }

    .btn-dark:hover { opacity: 0.85; }

    .btn-light {
      background: transparent;
      color: var(--text);
      border: 1px solid var(--border);
    }

    .btn-light:hover {
      border-color: #aaa;
      color: var(--black);
    }

    /* DIVIDER */
    .divider {
      border: none;
      border-top: 1px solid var(--border);
      margin: 0;
    }

    /* STATS */
    .stats {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      border-bottom: 1px solid var(--border);
    }

    .stat {
      padding: 2.5rem 2rem;
      border-right: 1px solid var(--border);
      text-align: center;
    }

    .stat:last-child { border-right: none; }

    .stat-val {
      font-size: 2rem;
      font-weight: 600;
      color: var(--black);
      letter-spacing: -0.02em;
      margin-bottom: 0.3rem;
    }

    .stat-label {
      font-size: 0.78rem;
      color: var(--text-light);
      font-weight: 400;
    }

    /* SECTIONS */
    .section {
      max-width: 900px;
      margin: 0 auto;
      padding: 5rem 2rem;
    }

    .section-label {
      font-family: var(--mono);
      font-size: 0.68rem;
      color: var(--text-light);
      letter-spacing: 0.12em;
      text-transform: uppercase;
      margin-bottom: 0.75rem;
    }

    .section-title {
      font-size: 1.6rem;
      font-weight: 600;
      color: var(--black);
      letter-spacing: -0.02em;
      margin-bottom: 1rem;
    }

    .section-desc {
      font-size: 0.9rem;
      color: var(--text);
      max-width: 540px;
      line-height: 1.75;
      font-weight: 300;
      margin-bottom: 3rem;
    }

    /* VERSIONS TABLE */
    .versions {
      border: 1px solid var(--border);
      border-radius: 4px;
      overflow: hidden;
    }

    .version-row {
      display: grid;
      grid-template-columns: 100px 1fr auto;
      gap: 0 2rem;
      padding: 1.75rem 2rem;
      border-bottom: 1px solid var(--border);
      align-items: start;
      transition: background 0.15s;
    }

    .version-row:last-child { border-bottom: none; }
    .version-row:hover { background: var(--surface); }

    .v-tag {
      font-family: var(--mono);
      font-size: 0.72rem;
      color: var(--text-light);
      padding-top: 0.15rem;
    }

    .v-name {
      font-size: 0.92rem;
      font-weight: 600;
      color: var(--black);
      margin-bottom: 0.3rem;
    }

    .v-desc {
      font-size: 0.82rem;
      color: var(--text);
      line-height: 1.6;
      margin-bottom: 0.75rem;
    }

    .v-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 0.35rem;
    }

    .vtag {
      font-family: var(--mono);
      font-size: 0.62rem;
      padding: 0.18rem 0.5rem;
      border-radius: 2px;
      letter-spacing: 0.02em;
    }

    .vtag-released { background: #f0fdf4; color: var(--green); border: 1px solid #bbf7d0; }
    .vtag-dev { background: #fffbeb; color: var(--amber); border: 1px solid #fde68a; }
    .vtag-plain { background: var(--surface); color: var(--text-light); border: 1px solid var(--border); }

    .status-badge {
      font-family: var(--mono);
      font-size: 0.65rem;
      padding: 0.25rem 0.65rem;
      border-radius: 2px;
      white-space: nowrap;
      align-self: start;
      font-weight: 500;
    }

    .status-released { background: #f0fdf4; color: var(--green); border: 1px solid #bbf7d0; }
    .status-dev { background: #fffbeb; color: var(--amber); border: 1px solid #fde68a; }
    .status-planned { background: var(--surface); color: var(--text-light); border: 1px solid var(--border); }

    /* FEATURES */
    .features {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1px;
      background: var(--border);
      border: 1px solid var(--border);
      border-radius: 4px;
      overflow: hidden;
    }

    .feature {
      background: #fff;
      padding: 1.75rem;
      transition: background 0.15s;
    }

    .feature:hover { background: var(--surface); }

    .feature-num {
      font-family: var(--mono);
      font-size: 0.62rem;
      color: #ccc;
      margin-bottom: 1rem;
    }

    .feature-title {
      font-size: 0.88rem;
      font-weight: 600;
      color: var(--black);
      margin-bottom: 0.5rem;
    }

    .feature-desc {
      font-size: 0.8rem;
      color: var(--text);
      line-height: 1.7;
    }

    .feature-ver {
      margin-top: 1rem;
      font-family: var(--mono);
      font-size: 0.62rem;
      color: var(--text-light);
    }

    /* FOUNDER */
    .founder-wrap {
      background: var(--surface);
      border-top: 1px solid var(--border);
      border-bottom: 1px solid var(--border);
    }

    .founder-inner {
      max-width: 900px;
      margin: 0 auto;
      padding: 5rem 2rem;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 4rem;
      align-items: start;
    }

    .founder-label {
      font-family: var(--mono);
      font-size: 0.68rem;
      color: var(--text-light);
      letter-spacing: 0.12em;
      text-transform: uppercase;
      margin-bottom: 1rem;
    }

    .founder-name {
      font-size: 1.4rem;
      font-weight: 600;
      color: var(--black);
      letter-spacing: -0.02em;
      margin-bottom: 0.3rem;
    }

    .founder-role {
      font-size: 0.82rem;
      color: var(--text-light);
      margin-bottom: 1.5rem;
    }

    .founder-bio {
      font-size: 0.85rem;
      color: var(--text);
      line-height: 1.85;
      font-weight: 300;
      margin-bottom: 1.5rem;
    }

    .founder-paper {
      background: #fff;
      border: 1px solid var(--border);
      border-left: 3px solid var(--black);
      padding: 1rem 1.25rem;
      margin-bottom: 1.5rem;
    }

    .paper-label {
      font-family: var(--mono);
      font-size: 0.62rem;
      color: var(--text-light);
      letter-spacing: 0.1em;
      text-transform: uppercase;
      margin-bottom: 0.4rem;
    }

    .paper-title {
      font-size: 0.82rem;
      color: var(--black);
      line-height: 1.5;
      font-weight: 500;
      margin-bottom: 0.3rem;
    }

    .paper-journal {
      font-size: 0.75rem;
      color: var(--text-light);
    }

    .interests {
      display: flex;
      flex-wrap: wrap;
      gap: 0.4rem;
    }

    .interest {
      font-family: var(--mono);
      font-size: 0.62rem;
      padding: 0.2rem 0.6rem;
      background: #fff;
      border: 1px solid var(--border);
      color: var(--text);
      border-radius: 2px;
    }

    .founder-right {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1px;
      background: var(--border);
      border: 1px solid var(--border);
      border-radius: 4px;
      overflow: hidden;
      align-self: start;
    }

    .fstat {
      background: #fff;
      padding: 1.5rem;
    }

    .fstat-val {
      font-size: 1.6rem;
      font-weight: 600;
      color: var(--black);
      letter-spacing: -0.02em;
      margin-bottom: 0.25rem;
    }

    .fstat-key {
      font-size: 0.75rem;
      color: var(--text-light);
    }

    /* FOOTER */
    footer {
      border-top: 1px solid var(--border);
    }

    .footer-inner {
      max-width: 900px;
      margin: 0 auto;
      padding: 3rem 2rem;
      display: grid;
      grid-template-columns: 2fr 1fr 1fr;
      gap: 3rem;
    }

    .footer-logo {
      font-family: var(--mono);
      font-size: 0.85rem;
      font-weight: 500;
      color: var(--black);
      margin-bottom: 0.75rem;
    }

    .footer-tagline {
      font-size: 0.82rem;
      color: var(--text);
      line-height: 1.7;
      font-weight: 300;
      max-width: 260px;
      margin-bottom: 1.5rem;
    }

    .footer-copy {
      font-size: 0.75rem;
      color: var(--text-light);
    }

    .footer-col-title {
      font-size: 0.8rem;
      font-weight: 600;
      color: var(--black);
      margin-bottom: 1rem;
    }

    .footer-links {
      list-style: none;
      display: flex;
      flex-direction: column;
      gap: 0.6rem;
    }

    .footer-links a {
      font-size: 0.82rem;
      color: var(--text);
      text-decoration: none;
      transition: color 0.15s;
    }

    .footer-links a:hover { color: var(--black); }

    /* REVEAL */
    .r {
      opacity: 0;
      transform: translateY(8px);
      transition: opacity 0.4s ease, transform 0.4s ease;
    }
    .r.show { opacity: 1; transform: none; }

    /* RESPONSIVE */
    @media (max-width: 768px) {
      nav { padding: 0 1.25rem; }
      .nav-links { display: none; }
      .hero { padding: 4rem 1.25rem 3rem; }
      .stats { grid-template-columns: repeat(2, 1fr); }
      .stat:nth-child(2) { border-right: none; }
      .stat:nth-child(3) { border-right: 1px solid var(--border); border-top: 1px solid var(--border); }
      .stat:nth-child(4) { border-right: none; border-top: 1px solid var(--border); }
      .section { padding: 3rem 1.25rem; }
      .version-row { grid-template-columns: 1fr; gap: 0.5rem; }
      .v-tag { padding-top: 0; }
      .features { grid-template-columns: 1fr; }
      .founder-inner { grid-template-columns: 1fr; gap: 2.5rem; padding: 3rem 1.25rem; }
      .footer-inner { grid-template-columns: 1fr; gap: 2rem; padding: 2.5rem 1.25rem; }
    }

    @media (max-width: 480px) {
      .hero h1 { font-size: 1.9rem; }
      .hero-actions { flex-direction: column; align-items: center; }
      .btn { justify-content: center; width: 100%; max-width: 280px; }
      .features { grid-template-columns: 1fr; }
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
    </ul>
    <a href="https://github.com/siparsecurity" target="_blank" class="nav-cta">GitHub →</a>
  </nav>

  <!-- HERO -->
  <div class="hero r">
    <div class="hero-tag">v2.0 Released · Open Source</div>
    <h1>Network security tools built for everyone</h1>
    <p>Sipar Security develops open-source network monitoring and intrusion detection tools for home users, IT administrators, and small businesses.</p>
    <div class="hero-actions">
      <a href="https://github.com/siparsecurity/network-monitor-v2" target="_blank" class="btn btn-dark">View on GitHub</a>
      <a href="https://github.com/siparsecurity/network-monitor-v2/releases" target="_blank" class="btn btn-light">Download</a>
    </div>
  </div>

  <hr class="divider"/>

  <!-- STATS -->
  <div class="stats r">
    <div class="stat">
      <div class="stat-val">v2.0</div>
      <div class="stat-label">Latest Release</div>
    </div>
    <div class="stat">
      <div class="stat-val">7s</div>
      <div class="stat-label">Scan Interval</div>
    </div>
    <div class="stat">
      <div class="stat-val">100%</div>
      <div class="stat-label">Open Source</div>
    </div>
    <div class="stat">
      <div class="stat-val">Free</div>
      <div class="stat-label">Always</div>
    </div>
  </div>

  <!-- VERSIONS -->
  <div class="section r" id="versions">
    <div class="section-label">Projects</div>
    <div class="section-title">Network Monitor</div>
    <div class="section-desc">A Python-based network intrusion detection system with real-time device tracking, persistent logging, and a SOC-style web dashboard.</div>

    <div class="versions">

      <div class="version-row">
        <div class="v-tag">v1.0 — 2026</div>
        <div>
          <div class="v-name">Version 1.0 — Foundation</div>
          <div class="v-desc">First public release. ARP scan engine, event server, persistent logging, and SOC dashboard.</div>
          <div class="v-tags">
            <span class="vtag vtag-released">ARP Scanning</span>
            <span class="vtag vtag-released">Event Server</span>
            <span class="vtag vtag-released">SOC Dashboard</span>
            <span class="vtag vtag-released">Auto Interface Detection</span>
            <span class="vtag vtag-released">Persistent Logging</span>
          </div>
        </div>
        <div class="status-badge status-released">Released</div>
      </div>

      <div class="version-row">
        <div class="v-tag">v2.0 — 2026</div>
        <div>
          <div class="v-name">Version 2.0 — Device Intelligence</div>
          <div class="v-desc">Device schema with first/last seen timestamps, offline detection after 3 missed scans, hardened ARP spoof engine, and upgraded SOC dashboard.</div>
          <div class="v-tags">
            <span class="vtag vtag-released">Device Schema</span>
            <span class="vtag vtag-released">Offline Detection</span>
            <span class="vtag vtag-released">ARP Spoof Cooldown</span>
            <span class="vtag vtag-released">MAC Randomization Handling</span>
            <span class="vtag vtag-released">Online/Offline Badges</span>
            <span class="vtag vtag-released">/stats API</span>
          </div>
        </div>
        <div class="status-badge status-released">Released</div>
      </div>

      <div class="version-row">
        <div class="v-tag">v3.0 — Active</div>
        <div>
          <div class="v-name">Version 3.0 — Attack Detection</div>
          <div class="v-desc">Dedicated attack detection engine with confidence-scored ARP spoof detection, duplicate MAC detection, port scan detection, threat levels, and cross-platform support for Linux, Windows, and Android.</div>
          <div class="v-tags">
            <span class="vtag vtag-dev">ARP Spoof Confidence Scoring</span>
            <span class="vtag vtag-dev">Duplicate MAC Detection</span>
            <span class="vtag vtag-dev">Port Scan Detection</span>
            <span class="vtag vtag-dev">Threat Levels</span>
            <span class="vtag vtag-dev">Risk Decay</span>
            <span class="vtag vtag-dev">Cross-Platform</span>
          </div>
        </div>
        <div class="status-badge status-dev">In Development</div>
      </div>

    </div>
  </div>

  <hr class="divider"/>

  <!-- CAPABILITIES -->
  <div class="section r" id="capabilities">
    <div class="section-label">Capabilities</div>
    <div class="section-title">What the tool does</div>
    <div class="section-desc">Current capabilities available in Version 1.0 and Version 2.0.</div>

    <div class="features">
      <div class="feature">
        <div class="feature-num">01</div>
        <div class="feature-title">Device Discovery</div>
        <div class="feature-desc">ARP-based scanning captures every device on your network — MAC address, IP, first seen, last seen, and cumulative risk score.</div>
        <div class="feature-ver">Available in v1.0</div>
      </div>
      <div class="feature">
        <div class="feature-num">02</div>
        <div class="feature-title">Real-Time Tracking</div>
        <div class="feature-desc">Continuous 7-second scans with instant online and offline status updates. Every state change logged with a timestamp.</div>
        <div class="feature-ver">Available in v1.0</div>
      </div>
      <div class="feature">
        <div class="feature-num">03</div>
        <div class="feature-title">Offline Detection</div>
        <div class="feature-desc">DEVICE_OFFLINE event fires after 3 consecutive missed scans, avoiding false positives from slow ARP responses.</div>
        <div class="feature-ver">Available in v2.0</div>
      </div>
      <div class="feature">
        <div class="feature-num">04</div>
        <div class="feature-title">ARP Spoof Detection</div>
        <div class="feature-desc">MAC history tracking with cooldown timer and 60-second MAC randomization window to eliminate false positives.</div>
        <div class="feature-ver">Available in v2.0</div>
      </div>
      <div class="feature">
        <div class="feature-num">05</div>
        <div class="feature-title">SOC Dashboard</div>
        <div class="feature-desc">Browser-based SOC interface with stat cards, filtered alerts panel, online/offline badges, and risk color coding.</div>
        <div class="feature-ver">Available in v1.0</div>
      </div>
      <div class="feature">
        <div class="feature-num">06</div>
        <div class="feature-title">Persistent Logging</div>
        <div class="feature-desc">All events saved to disk as JSONL. Full device state reconstructed from disk on every restart with no data loss.</div>
        <div class="feature-ver">Available in v2.0</div>
      </div>
    </div>
  </div>

  <!-- FOUNDER -->
  <div class="founder-wrap r" id="founder">
    <div class="founder-inner">
      <div>
        <div class="founder-label">Founder</div>
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
          <div class="paper-label">Published Research · 2026</div>
          <div class="paper-title">Simulating and Mitigating Rogue Access Point Attacks in Wi-Fi Networks Using Open-Source Tools</div>
          <div class="paper-journal">Journal of Soft Computing and Artificial Intelligence</div>
        </div>

        <div class="interests">
          <span class="interest">Network Security</span>
          <span class="interest">Penetration Testing</span>
          <span class="interest">Wireless Security</span>
          <span class="interest">Vulnerability Assessment</span>
          <span class="interest">Ethical Hacking</span>
          <span class="interest">Kali Linux</span>
          <span class="interest">Python</span>
          <span class="interest">Open-Source Tools</span>
          <span class="interest">Security Research</span>
          <span class="interest">Defensive Security</span>
        </div>
      </div>

      <div class="founder-right">
        <div class="fstat">
          <div class="fstat-val">17</div>
          <div class="fstat-key">Years old</div>
        </div>
        <div class="fstat">
          <div class="fstat-val">2</div>
          <div class="fstat-key">Tools released</div>
        </div>
        <div class="fstat">
          <div class="fstat-val">1</div>
          <div class="fstat-key">Published paper</div>
        </div>
        <div class="fstat">
          <div class="fstat-val">PK 🇵🇰</div>
          <div class="fstat-key">Pakistan</div>
        </div>
      </div>
    </div>
  </div>

  <!-- FOOTER -->
  <footer>
    <div class="footer-inner">
      <div>
        <div class="footer-logo">SIPAR SECURITY</div>
        <p class="footer-tagline">Open-source network security tools built in Pakistan. Free for everyone, no enterprise budget required.</p>
        <div class="footer-copy">© 2026 Sipar Security · MIT License · Pakistan 🇵🇰</div>
      </div>
      <div>
        <div class="footer-col-title">Projects</div>
        <ul class="footer-links">
          <li><a href="https://github.com/siparsecurity/network-monitor" target="_blank">Network Monitor v1.0</a></li>
          <li><a href="https://github.com/siparsecurity/network-monitor-v2" target="_blank">Network Monitor v2.0</a></li>
          <li><a href="https://github.com/siparsecurity/network-monitor-v2/releases" target="_blank">All Releases</a></li>
          <li><a href="https://github.com/siparsecurity" target="_blank">GitHub Organization</a></li>
        </ul>
      </div>
      <div>
        <div class="footer-col-title">Contact</div>
        <ul class="footer-links">
          <li><a href="mailto:siparsecurity@gmail.com">siparsecurity@gmail.com</a></li>
          <li><a href="https://linkedin.com/company/siparsecurity" target="_blank">LinkedIn</a></li>
          <li><a href="https://x.com/SiparSecurity" target="_blank">X / Twitter</a></li>
          <li><a href="https://github.com/siparsecurity" target="_blank">GitHub</a></li>
        </ul>
      </div>
    </div>
  </footer>

  <script>
    const els = document.querySelectorAll('.r');
    const obs = new IntersectionObserver(entries => {
      entries.forEach((e, i) => {
        if (e.isIntersecting) setTimeout(() => e.target.classList.add('show'), i * 60);
      });
    }, { threshold: 0.05 });
    els.forEach(e => obs.observe(e));
  </script>

</body>
</html>
