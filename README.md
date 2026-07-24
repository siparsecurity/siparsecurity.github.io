<html lang="en">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Sipar Security — Cybersecurity Tools & Services</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=IBM+Plex+Mono:wght@400;500&display=swap" rel="stylesheet">
  <style>
    :root {
      --black: #0a0a0a; --white: #ffffff; --off: #f5f5f3; --text: #555; --light: #999; --border: #e8e8e8;
      --green: #16a34a; --green-bg: #f0fdf4; --green-bd: #bbf7d0;
      --amber: #b45309; --amber-bg: #fffbeb; --amber-bd: #fde68a;
      --red: #dc2626; --mono: 'IBM Plex Mono', monospace; --sans: 'Inter', sans-serif;
    }
    * { margin: 0; padding: 0; box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body { font-family: var(--sans); background: var(--white); color: var(--black); -webkit-font-smoothing: antialiased; }
    nav { position: sticky; top: 0; z-index: 99; background: rgba(255,255,255,0.96); backdrop-filter: blur(8px); border-bottom: 1px solid var(--border); height: 62px; display: flex; align-items: center; justify-content: space-between; padding: 0 2.5rem; }
    .nav-logo { font-family: var(--mono); font-size: 0.82rem; font-weight: 500; color: var(--black); text-decoration: none; letter-spacing: 0.06em; }
    .nav-links { display: flex; gap: 2rem; list-style: none; }
    .nav-links a { font-size: 0.84rem; color: var(--text); text-decoration: none; transition: color 0.15s; }
    .nav-links a:hover { color: var(--black); }
    .nav-btn { font-size: 0.82rem; font-weight: 600; background: var(--black); color: #fff; padding: 0.5rem 1.25rem; text-decoration: none; transition: opacity 0.15s; }
    .nav-btn:hover { opacity: 0.8; }
    .hero { padding: 7rem 2rem 6rem; text-align: center; max-width: 820px; margin: 0 auto; }
    .hero-badge { display: inline-flex; align-items: center; gap: 0.5rem; font-family: var(--mono); font-size: 0.7rem; color: var(--green); background: var(--green-bg); border: 1px solid var(--green-bd); padding: 0.3rem 0.85rem; margin-bottom: 2rem; letter-spacing: 0.04em; }
    .hero-badge::before { content: ''; width: 6px; height: 6px; background: var(--green); border-radius: 50%; animation: blink 2s ease infinite; }
    @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0.3} }
    .hero h1 { font-size: clamp(2.4rem, 6vw, 4rem); font-weight: 700; line-height: 1.1; letter-spacing: -0.03em; color: var(--black); margin-bottom: 1.5rem; }
    .hero h1 em { font-style: normal; color: var(--green); }
    .hero p { font-size: 1.05rem; color: var(--text); line-height: 1.8; font-weight: 300; max-width: 520px; margin: 0 auto 2.75rem; }
    .hero-btns { display: flex; gap: 0.75rem; justify-content: center; flex-wrap: wrap; }
    .btn { font-size: 0.88rem; font-weight: 500; padding: 0.75rem 1.6rem; text-decoration: none; display: inline-flex; align-items: center; gap: 0.4rem; transition: all 0.15s; }
    .btn-black { background: var(--black); color: #fff; }
    .btn-black:hover { opacity: 0.85; }
    .btn-border { border: 1.5px solid var(--border); color: var(--text); background: #fff; }
    .btn-border:hover { border-color: #aaa; color: var(--black); }
    .ticker { border-top: 1px solid var(--border); border-bottom: 1px solid var(--border); background: var(--black); color: #fff; padding: 0.85rem 0; overflow: hidden; }
    .ticker-inner { display: flex; gap: 4rem; white-space: nowrap; animation: ticker 22s linear infinite; font-family: var(--mono); font-size: 0.72rem; color: #888; letter-spacing: 0.08em; }
    .ticker-inner span { color: var(--green); }
    @keyframes ticker { 0%{transform:translateX(0)} 100%{transform:translateX(-50%)} }
    .stats { display: grid; grid-template-columns: repeat(4,1fr); border-bottom: 1px solid var(--border); }
    .stat { padding: 2.75rem 2rem; text-align: center; border-right: 1px solid var(--border); }
    .stat:last-child { border-right: none; }
    .stat-n { font-size: 2.4rem; font-weight: 700; color: var(--black); letter-spacing: -0.02em; line-height: 1; margin-bottom: 0.4rem; }
    .stat-n em { font-style: normal; color: var(--green); }
    .stat-l { font-size: 0.78rem; color: var(--light); }
    .sec { max-width: 960px; margin: 0 auto; padding: 5.5rem 2rem; }
    .sec-sub { font-family: var(--mono); font-size: 0.68rem; color: var(--light); letter-spacing: 0.14em; text-transform: uppercase; margin-bottom: 0.6rem; }
    .sec-title { font-size: clamp(1.5rem, 3vw, 2rem); font-weight: 700; letter-spacing: -0.02em; color: var(--black); margin-bottom: 0.85rem; }
    .sec-desc { font-size: 0.9rem; color: var(--text); line-height: 1.8; font-weight: 300; max-width: 520px; margin-bottom: 3rem; }
    .tools-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1px; background: var(--border); border: 1px solid var(--border); border-radius: 6px; overflow: hidden; margin-bottom: 1.5rem; }
    .tool-card { background: #fff; padding: 2rem; transition: background 0.15s; position: relative; }
    .tool-card:hover { background: var(--off); }
    .tool-card.active-tool { background: #fafffe; border-left: 3px solid var(--green); }
    .tool-card-label { font-family: var(--mono); font-size: 0.62rem; color: var(--light); letter-spacing: 0.12em; text-transform: uppercase; margin-bottom: 0.75rem; display: flex; align-items: center; justify-content: space-between; }
    .tool-card-name { font-size: 1.05rem; font-weight: 700; color: var(--black); margin-bottom: 0.4rem; }
    .tool-card-desc { font-size: 0.82rem; color: var(--text); line-height: 1.65; font-weight: 300; margin-bottom: 1rem; }
    .tool-versions { display: flex; gap: 0.35rem; flex-wrap: wrap; margin-bottom: 1rem; }
    .tool-ver { font-family: var(--mono); font-size: 0.6rem; padding: 0.18rem 0.55rem; border-radius: 3px; }
    .tv-released { background: var(--green-bg); color: var(--green); border: 1px solid var(--green-bd); }
    .tv-dev { background: var(--amber-bg); color: var(--amber); border: 1px solid var(--amber-bd); }
    .tool-link { font-family: var(--mono); font-size: 0.7rem; color: var(--green); text-decoration: none; display: inline-flex; align-items: center; gap: 0.3rem; margin-right: 1rem; }
    .tool-link:hover { text-decoration: underline; }
    .tool-status-badge { font-family: var(--mono); font-size: 0.6rem; padding: 0.2rem 0.6rem; border-radius: 3px; font-weight: 600; }
    .tsb-active { background: var(--green-bg); color: var(--green); border: 1px solid var(--green-bd); }
    .versions { border: 1px solid var(--border); border-radius: 6px; overflow: hidden; }
    .vrow { display: grid; grid-template-columns: 110px 1fr auto; gap: 0 2.5rem; padding: 2rem 2.5rem; border-bottom: 1px solid var(--border); align-items: start; transition: background 0.15s; }
    .vrow:last-child { border-bottom: none; }
    .vrow:hover { background: var(--off); }
    .vrow.current { background: #fafffe; border-left: 3px solid var(--green); }
    .v-ver { font-family: var(--mono); font-size: 0.7rem; color: var(--light); padding-top: 0.2rem; }
    .v-name { font-size: 0.95rem; font-weight: 700; color: var(--black); margin-bottom: 0.3rem; }
    .v-desc { font-size: 0.82rem; color: var(--text); line-height: 1.65; margin-bottom: 0.85rem; font-weight: 300; }
    .v-tags { display: flex; flex-wrap: wrap; gap: 0.35rem; }
    .vtag { font-family: var(--mono); font-size: 0.6rem; padding: 0.18rem 0.55rem; border-radius: 3px; }
    .vt-g { background: var(--green-bg); color: var(--green); border: 1px solid var(--green-bd); }
    .v-badge { font-family: var(--mono); font-size: 0.62rem; padding: 0.25rem 0.7rem; border-radius: 3px; font-weight: 500; white-space: nowrap; align-self: start; }
    .vb-g { background: var(--green-bg); color: var(--green); border: 1px solid var(--green-bd); }
    .fgrid { display: grid; grid-template-columns: repeat(3,1fr); gap: 1px; background: var(--border); border: 1px solid var(--border); border-radius: 6px; overflow: hidden; }
    .fcard { background: #fff; padding: 2rem; transition: background 0.15s; }
    .fcard:hover { background: var(--off); }
    .fcard-n { font-family: var(--mono); font-size: 0.6rem; color: #ddd; margin-bottom: 1rem; }
    .fcard-t { font-size: 0.9rem; font-weight: 700; color: var(--black); margin-bottom: 0.5rem; }
    .fcard-d { font-size: 0.8rem; color: var(--text); line-height: 1.7; font-weight: 300; }
    .fcard-v { margin-top: 1rem; font-family: var(--mono); font-size: 0.6rem; color: var(--light); }
    .platform-table { width: 100%; border-collapse: collapse; border: 1px solid var(--border); border-radius: 6px; overflow: hidden; }
    .platform-table th { background: var(--black); color: #fff; font-family: var(--mono); font-size: 0.68rem; letter-spacing: 0.08em; padding: 1rem 1.5rem; text-align: left; font-weight: 500; }
    .platform-table td { padding: 1rem 1.5rem; font-size: 0.84rem; color: var(--text); border-bottom: 1px solid var(--border); }
    .platform-table tr:last-child td { border-bottom: none; }
    .platform-table tr:hover td { background: var(--off); }
    .yes { color: var(--green); font-weight: 600; }
    .no { color: var(--red); }
    .partial { color: var(--amber); font-weight: 500; }
    .founder-wrap { background: var(--off); border-top: 1px solid var(--border); border-bottom: 1px solid var(--border); }
    .founder-inner { max-width: 960px; margin: 0 auto; padding: 5.5rem 2rem; display: grid; grid-template-columns: 1.2fr 1fr; gap: 5rem; align-items: start; }
    .founder-sub { font-family: var(--mono); font-size: 0.68rem; color: var(--light); letter-spacing: 0.14em; text-transform: uppercase; margin-bottom: 1rem; }
    .founder-name { font-size: 1.5rem; font-weight: 700; color: var(--black); letter-spacing: -0.02em; margin-bottom: 0.25rem; }
    .founder-role { font-size: 0.82rem; color: var(--light); margin-bottom: 1.75rem; }
    .founder-bio { font-size: 0.86rem; color: var(--text); line-height: 1.9; font-weight: 300; margin-bottom: 1.75rem; }
    .founder-paper { background: #fff; border: 1px solid var(--border); border-left: 3px solid var(--black); padding: 1rem 1.25rem; margin-bottom: 1.75rem; }
    .paper-sub { font-family: var(--mono); font-size: 0.6rem; color: var(--light); letter-spacing: 0.1em; text-transform: uppercase; margin-bottom: 0.4rem; }
    .paper-t { font-size: 0.82rem; font-weight: 500; color: var(--black); line-height: 1.5; margin-bottom: 0.25rem; }
    .paper-j { font-size: 0.75rem; color: var(--light); }
    .tags { display: flex; flex-wrap: wrap; gap: 0.4rem; }
    .itag { font-family: var(--mono); font-size: 0.6rem; padding: 0.2rem 0.6rem; background: #fff; border: 1px solid var(--border); color: var(--text); border-radius: 3px; }
    .fstats { display: grid; grid-template-columns: 1fr 1fr; gap: 1px; background: var(--border); border: 1px solid var(--border); border-radius: 6px; overflow: hidden; }
    .fstat { background: #fff; padding: 1.75rem; }
    .fstat-n { font-size: 1.8rem; font-weight: 700; color: var(--black); letter-spacing: -0.02em; margin-bottom: 0.25rem; }
    .fstat-l { font-size: 0.75rem; color: var(--light); }
    .faq-wrap { border: 1px solid var(--border); border-radius: 6px; overflow: hidden; }
    .faq-item { border-bottom: 1px solid var(--border); }
    .faq-item:last-child { border-bottom: none; }
    .faq-q { padding: 1.25rem 1.5rem; font-size: 0.9rem; font-weight: 600; color: var(--black); cursor: pointer; display: flex; justify-content: space-between; align-items: center; transition: background 0.15s; user-select: none; }
    .faq-q:hover { background: var(--off); }
    .faq-q::after { content: '+'; font-size: 1.2rem; color: var(--light); font-weight: 300; transition: transform 0.2s; }
    .faq-item.open .faq-q::after { transform: rotate(45deg); }
    .faq-a { max-height: 0; overflow: hidden; transition: max-height 0.3s ease; }
    .faq-item.open .faq-a { max-height: 300px; }
    .faq-a-inner { padding: 0 1.5rem 1.25rem; font-size: 0.85rem; color: var(--text); line-height: 1.75; font-weight: 300; }
    .cta-band { background: var(--black); color: #fff; padding: 5rem 2rem; text-align: center; }
    .cta-band h2 { font-size: clamp(1.6rem, 4vw, 2.4rem); font-weight: 700; letter-spacing: -0.02em; margin-bottom: 1rem; max-width: 560px; margin-left: auto; margin-right: auto; }
    .cta-band p { font-size: 0.9rem; color: #777; line-height: 1.8; font-weight: 300; max-width: 420px; margin: 0 auto 2.5rem; }
    .cta-btns { display: flex; gap: 0.75rem; justify-content: center; flex-wrap: wrap; }
    .cta-btn-white { display: inline-block; background: #fff; color: var(--black); font-size: 0.88rem; font-weight: 700; padding: 0.85rem 2rem; text-decoration: none; transition: opacity 0.15s; }
    .cta-btn-white:hover { opacity: 0.9; }
    .cta-btn-ghost { display: inline-block; border: 1.5px solid #333; color: #aaa; font-size: 0.88rem; font-weight: 500; padding: 0.85rem 2rem; text-decoration: none; transition: all 0.15s; }
    .cta-btn-ghost:hover { border-color: #777; color: #fff; }
    footer { border-top: 1px solid var(--border); }
    .footer-inner { max-width: 960px; margin: 0 auto; padding: 3rem 2rem; display: grid; grid-template-columns: 2fr 1fr 1fr; gap: 2.5rem; }
    .footer-logo { font-family: var(--mono); font-size: 0.82rem; font-weight: 500; color: var(--black); margin-bottom: 0.75rem; }
    .footer-tag { font-size: 0.82rem; color: var(--text); line-height: 1.7; font-weight: 300; max-width: 240px; margin-bottom: 1.5rem; }
    .footer-copy { font-size: 0.72rem; color: var(--light); }
    .footer-h { font-size: 0.8rem; font-weight: 600; color: var(--black); margin-bottom: 1rem; }
    .footer-links { list-style: none; display: flex; flex-direction: column; gap: 0.6rem; }
    .footer-links a { font-size: 0.82rem; color: var(--text); text-decoration: none; transition: color 0.15s; }
    .footer-links a:hover { color: var(--black); }
    .r { opacity: 0; transform: translateY(10px); transition: opacity 0.45s ease, transform 0.45s ease; }
    .r.on { opacity: 1; transform: none; }
    @media (max-width: 800px) {
      nav { padding: 0 1.25rem; } .nav-links { display: none; } .hero { padding: 5rem 1.25rem 4rem; }
      .stats { grid-template-columns: repeat(2,1fr); } .stat:nth-child(2) { border-right: none; }
      .stat:nth-child(3) { border-top: 1px solid var(--border); } .stat:nth-child(4) { border-right: none; border-top: 1px solid var(--border); }
      .sec { padding: 3.5rem 1.25rem; } .tools-grid { grid-template-columns: 1fr; } .vrow { grid-template-columns: 1fr; gap: 0.5rem; }
      .fgrid { grid-template-columns: 1fr 1fr; } .founder-inner { grid-template-columns: 1fr; gap: 2.5rem; padding: 3.5rem 1.25rem; }
      .footer-inner { grid-template-columns: 1fr; gap: 2rem; padding: 2.5rem 1.25rem; } .cta-band { padding: 3.5rem 1.25rem; } .cta-btns { flex-direction: column; align-items: center; }
    }
    @media (max-width: 500px) {
      .hero h1 { font-size: 2rem; } .hero-btns { flex-direction: column; align-items: center; }
      .btn { width: 100%; max-width: 280px; justify-content: center; } .fgrid { grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>

<nav>
  <a href="/" class="nav-logo">SIPAR SECURITY</a>
  <ul class="nav-links">
    <li><a href="#tools">Tools</a></li>
    <li><a href="#capabilities">Capabilities</a></li>
    <li><a href="#founder">About</a></li>
    <li><a href="#faq">FAQ</a></li>
    <li><a href="/services.html">Services</a></li>
  </ul>
  <a href="https://github.com/siparsecurity" target="_blank" class="nav-btn">GitHub →</a>
</nav>

<div class="hero r">
  <div class="hero-badge">Actively Building · Open Source · Pakistan 🇵🇰</div>
  <h1>Cybersecurity tools and services <em>built for everyone.</em></h1>
  <p>Sipar Security develops open-source security tools, provides professional security services, and conducts applied security research — built for real-world use, not enterprise budgets.</p>
  <div class="hero-btns">
    <a href="https://github.com/siparsecurity" target="_blank" class="btn btn-black">⭐ View All Tools</a>
    <a href="/services.html" class="btn btn-border">Our Services →</a>
  </div>
</div>

<div class="ticker">
  <div class="ticker-inner">
    <span>NEW DEVICE DETECTED</span> · 192.168.1.201 ·
    <span>ARP SPOOF — HIGH CONFIDENCE</span> · 192.168.1.1 ·
    <span>PORT SCAN DETECTED</span> · 192.168.1.45 ·
    <span>ROGUE DEVICE FLAGGED</span> · 192.168.1.88 ·
    <span>THREAT LEVEL: CRITICAL</span> · 192.168.1.3 ·
    <span>SUBDOMAIN FOUND</span> · api.target.com ·
    <span>ZONE TRANSFER REFUSED</span> · ns1.target.com ·
    <span>CNAME TAKEOVER — VULNERABLE</span> · blog.target.com → github.io ·
    <span>GHOSTCLAIM</span> · FINGERPRINT MATCHED · GitHub Pages ·
    <span>POTENTIALLY VULNERABLE</span> · shop.target.com → myshopify.com ·
    <span>NEW DEVICE DETECTED</span> · 192.168.1.201 ·
    <span>ARP SPOOF — HIGH CONFIDENCE</span> · 192.168.1.1 ·
    <span>PORT SCAN DETECTED</span> · 192.168.1.45 ·
    <span>ROGUE DEVICE FLAGGED</span> · 192.168.1.88 ·
    <span>THREAT LEVEL: CRITICAL</span> · 192.168.1.3 ·
    <span>SUBDOMAIN FOUND</span> · api.target.com ·
    <span>ZONE TRANSFER REFUSED</span> · ns1.target.com ·
    <span>CNAME TAKEOVER — VULNERABLE</span> · blog.target.com → github.io ·
    <span>GHOSTCLAIM</span> · FINGERPRINT MATCHED · GitHub Pages ·
    <span>POTENTIALLY VULNERABLE</span> · shop.target.com → myshopify.com ·
  </div>
</div>

<div class="stats r">
  <div class="stat"><div class="stat-n">3<em>+</em></div><div class="stat-l">Tools Released</div></div>
  <div class="stat"><div class="stat-n">100<em>%</em></div><div class="stat-l">Open Source</div></div>
  <div class="stat"><div class="stat-n">0<em>$</em></div><div class="stat-l">Cost to Use</div></div>
  <div class="stat"><div class="stat-n">PK<em> 🇵🇰</em></div><div class="stat-l">Built in Pakistan</div></div>
</div>

<div class="sec r" id="tools">
  <div class="sec-sub">Our Tools</div>
  <div class="sec-title">What we are building</div>
  <div class="sec-desc">All tools are free, open-source, and available on GitHub. Pro versions are available directly for advanced features.</div>

  <div class="tools-grid">
    <div class="tool-card active-tool">
      <div class="tool-card-label"><span>Tool 01 · Network Security</span><span class="tool-status-badge tsb-active">Active</span></div>
      <div class="tool-card-name">Sipar Network Monitor</div>
      <div class="tool-card-desc">A Python-based network intrusion detection system. Detects every device, tracks online/offline status, flags ARP spoofing, port scans, rogue devices, and scores threats in real time.</div>
      <div class="tool-versions">
        <span class="tool-ver tv-released">v1.0 Released</span>
        <span class="tool-ver tv-released">v2.0 Released</span>
        <span class="tool-ver tv-released">v3.0 Released</span>
      </div>
      <a href="https://github.com/siparsecurity/network-monitor-v3" target="_blank" class="tool-link">View on GitHub →</a>
    </div>

    <div class="tool-card active-tool">
      <div class="tool-card-label"><span>Tool 02 · Offensive Security</span><span class="tool-status-badge tsb-active">Active</span></div>
      <div class="tool-card-name">ShadowMap</div>
      <div class="tool-card-desc">A web reconnaissance framework built for bug bounty hunters and penetration testers. Automates subdomain enumeration, DNS recon, technology fingerprinting, and port scanning into a single command — now fully open source with improved detection accuracy.</div>
      <div class="tool-versions">
        <span class="tool-ver tv-released">v1.0 Released</span>
        <span class="tool-ver tv-released">Fully Open Source</span>
      </div>
      <a href="https://github.com/siparsecurity/shadowmap" target="_blank" class="tool-link">View on GitHub →</a>
    </div>

    <div class="tool-card active-tool">
      <div class="tool-card-label"><span>Tool 03 · Offensive Security</span><span class="tool-status-badge tsb-active">New</span></div>
      <div class="tool-card-name">GhostClaim</div>
      <div class="tool-card-desc">A subdomain takeover detection tool for penetration testers and bug bounty hunters. Enumerates subdomains, follows full CNAME chains, and fingerprints HTTP responses against known vulnerable services.</div>
      <div class="tool-versions">
        <span class="tool-ver tv-released">v1.0 Free Released</span>
        <span class="tool-ver tv-dev">Pro Available</span>
      </div>
      <a href="https://github.com/siparsecurity/ghostclaim" target="_blank" class="tool-link">Free →</a>
      <a href="https://github.com/siparsecurity/ghostclaim-pro" target="_blank" class="tool-link">Pro →</a>
    </div>
  </div>

  <div style="border:1px solid var(--green-bd);background:var(--green-bg);border-radius:6px;padding:1.25rem 1.5rem;display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:1rem;margin-bottom:1.5rem;">
    <div>
      <div style="font-size:0.92rem;font-weight:700;color:var(--black);margin-bottom:0.25rem;">Want the Pro version?</div>
      <div style="font-size:0.8rem;color:var(--text);font-weight:300;">GhostClaim Pro adds 30+ service fingerprints, stealth modes, JSON export, and professional report generation.</div>
    </div>
    <a href="/services.html" class="btn btn-black" style="white-space:nowrap;">Get Pro →</a>
  </div>

  <div style="font-size:0.78rem;color:var(--light);font-family:var(--mono);">
    Follow us on <a href="https://github.com/siparsecurity" target="_blank" style="color:var(--green);text-decoration:none;">GitHub</a> to stay updated on new releases.
  </div>
</div>

<div class="sec r" id="versions" style="padding-top:0;">
  <div class="sec-sub">Network Monitor — Release History</div>
  <div class="sec-title">Three versions. Each one better.</div>
  <div class="sec-desc">Every version is publicly available. Download any version from GitHub.</div>
  <div class="versions">
    <div class="vrow">
      <div class="v-ver">v1.0 — 2026</div>
      <div>
        <div class="v-name">Version 1.0 — Foundation</div>
        <div class="v-desc">First public release. ARP scan engine, event server, persistent logging, SOC dashboard, and auto interface detection.</div>
        <div class="v-tags">
          <span class="vtag vt-g">ARP Scanning</span><span class="vtag vt-g">SOC Dashboard</span><span class="vtag vt-g">Event Server</span><span class="vtag vt-g">Persistent Logging</span>
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
          <span class="vtag vt-g">Device Schema</span><span class="vtag vt-g">Offline Detection</span><span class="vtag vt-g">ARP Spoof Cooldown</span><span class="vtag vt-g">MAC Randomization Handling</span><span class="vtag vt-g">/stats API</span>
        </div>
      </div>
      <div class="v-badge vb-g">Released</div>
    </div>
    <div class="vrow current">
      <div class="v-ver">v3.0 — 2026</div>
      <div>
        <div class="v-name">Version 3.0 — Attack Detection</div>
        <div class="v-desc">Full attack detection engine. Confidence-scored ARP spoof, duplicate MAC detection, port scan detection, rogue device flagging, threat levels, risk decay, and cross-platform support.</div>
        <div class="v-tags">
          <span class="vtag vt-g">ARP Spoof Confidence Scoring</span><span class="vtag vt-g">Duplicate MAC Detection</span><span class="vtag vt-g">Port Scan Detection</span><span class="vtag vt-g">Rogue Device Detection</span><span class="vtag vt-g">LOW/MEDIUM/HIGH/CRITICAL</span><span class="vtag vt-g">Linux · Windows · Android</span>
        </div>
      </div>
      <div class="v-badge vb-g">Latest</div>
    </div>
  </div>
</div>

<div class="sec r" id="capabilities" style="padding-top:0;">
  <div class="sec-sub">Capabilities</div>
  <div class="sec-title">What the Network Monitor detects.</div>
  <div class="sec-desc">All features available in Version 3.0.</div>
  <div class="fgrid">
    <div class="fcard"><div class="fcard-n">001</div><div class="fcard-t">Device Discovery</div><div class="fcard-d">ARP-based scanning finds every device — MAC, IP, first seen, last seen, cumulative risk score.</div><div class="fcard-v">v1.0 +</div></div>
    <div class="fcard"><div class="fcard-n">002</div><div class="fcard-t">Real-Time Tracking</div><div class="fcard-d">7-second scan cycles. Online and offline status updates the moment something changes.</div><div class="fcard-v">v1.0 +</div></div>
    <div class="fcard"><div class="fcard-n">003</div><div class="fcard-t">ARP Spoof Detection</div><div class="fcard-d">Confidence-scored — LOW, MEDIUM, HIGH. Cooldown timer and 60-second MAC randomization window.</div><div class="fcard-v">v3.0</div></div>
    <div class="fcard"><div class="fcard-n">004</div><div class="fcard-t">Port Scan Detection</div><div class="fcard-d">Background thread watches for one IP probing multiple ports rapidly. Five ports in 10 seconds triggers alert.</div><div class="fcard-v">v3.0</div></div>
    <div class="fcard"><div class="fcard-n">005</div><div class="fcard-t">Duplicate MAC Detection</div><div class="fcard-d">Same MAC address on two different IPs simultaneously — instantly flagged.</div><div class="fcard-v">v3.0</div></div>
    <div class="fcard"><div class="fcard-n">006</div><div class="fcard-t">Rogue Device Detection</div><div class="fcard-d">Trusted baseline on first scan. Any device joining after is flagged as unknown immediately.</div><div class="fcard-v">v3.0</div></div>
    <div class="fcard"><div class="fcard-n">007</div><div class="fcard-t">Threat Level System</div><div class="fcard-d">Every device scored LOW, MEDIUM, HIGH, or CRITICAL. Risk decays when device stays clean.</div><div class="fcard-v">v3.0</div></div>
    <div class="fcard"><div class="fcard-n">008</div><div class="fcard-t">SOC Dashboard</div><div class="fcard-d">6 stat cards, threat badges, filtered alert panel, risk reset button. Accessible from any browser on same network.</div><div class="fcard-v">v1.0 +</div></div>
    <div class="fcard"><div class="fcard-n">009</div><div class="fcard-t">Persistent Logging</div><div class="fcard-d">All events saved to disk as JSONL. Full device state rebuilt on every restart. Zero data loss.</div><div class="fcard-v">v2.0 +</div></div>
  </div>
</div>

<div class="sec r" style="padding-top:0;">
  <div class="sec-sub">Platform Support</div>
  <div class="sec-title">Runs everywhere.</div>
  <div class="sec-desc">One command to install. Dashboard accessible from any browser on the same network.</div>
  <table class="platform-table">
    <thead><tr><th>Platform</th><th>Run the Tool</th><th>View Dashboard</th></tr></thead>
    <tbody>
      <tr><td>Kali Linux</td><td class="yes">✓ Full support</td><td class="yes">✓</td></tr>
      <tr><td>Ubuntu / Debian</td><td class="yes">✓ Full support</td><td class="yes">✓</td></tr>
      <tr><td>Windows 10 / 11</td><td class="partial">✓ Requires Npcap</td><td class="yes">✓</td></tr>
      <tr><td>Termux — Rooted Android</td><td class="yes">✓ Full support</td><td class="yes">✓</td></tr>
      <tr><td>Termux — Not Rooted</td><td class="no">✗ Root required</td><td class="yes">✓ Browser only</td></tr>
      <tr><td>Any phone / tablet browser</td><td class="no">✗</td><td class="yes">✓ Same WiFi, no setup</td></tr>
    </tbody>
  </table>
</div>

<div class="founder-wrap r" id="founder">
  <div class="founder-inner">
    <div>
      <div class="founder-sub">Founder</div>
      <div class="founder-name">Sayed Muhammad Subayyal</div>
      <div class="founder-role">Cybersecurity Researcher · Penetration Tester · Founder, Sipar Security</div>
      <p class="founder-bio">Cybersecurity researcher and penetration tester focused on network security, wireless security, vulnerability assessment, and open-source security tool development. Works with Linux environments, particularly Kali Linux, applying structured methodologies for security testing and defensive assessments. Actively contributes to the cybersecurity community through vulnerability disclosure, open-source development, and academic research. Currently studying at Islamia College Peshawar.</p>
      <div class="founder-paper">
        <div class="paper-sub">Published Research · 2026</div>
        <div class="paper-t">Simulating and Mitigating Rogue Access Point Attacks in Wi-Fi Networks Using Open-Source Tools</div>
        <div class="paper-j">Journal of Soft Computing and Artificial Intelligence</div>
      </div>
      <div class="tags">
        <span class="itag">Network Security</span><span class="itag">Penetration Testing</span><span class="itag">Wireless Security</span><span class="itag">Ethical Hacking</span><span class="itag">Kali Linux</span><span class="itag">Python</span><span class="itag">Open-Source Tools</span><span class="itag">Vulnerability Assessment</span><span class="itag">Bug Bounty</span><span class="itag">Subdomain Takeover</span>
      </div>
    </div>
    <div>
      <div class="fstats">
        <div class="fstat"><div class="fstat-n">17</div><div class="fstat-l">Years old</div></div>
        <div class="fstat"><div class="fstat-n">3+</div><div class="fstat-l">Tools released</div></div>
        <div class="fstat"><div class="fstat-n">1</div><div class="fstat-l">Published paper</div></div>
        <div class="fstat"><div class="fstat-n">PK 🇵🇰</div><div class="fstat-l">Pakistan</div></div>
      </div>
    </div>
  </div>
</div>

<div class="sec r" id="faq">
  <div class="sec-sub">FAQ</div>
  <div class="sec-title">Common questions</div>
  <div class="sec-desc">Answers to what people ask most often about our tools and services.</div>
  <div class="faq-wrap">
    <div class="faq-item">
      <div class="faq-q">Are your tools really free?</div>
      <div class="faq-a"><div class="faq-a-inner">Yes — completely free. All tools are open-source and published on GitHub under the MIT License. You can download, use, and modify them at no cost. A Pro version with advanced features is available separately for GhostClaim.</div></div>
    </div>
    <div class="faq-item">
      <div class="faq-q">What is subdomain takeover and why does GhostClaim matter?</div>
      <div class="faq-a"><div class="faq-a-inner">Subdomain takeover happens when a subdomain points to an external service (like GitHub Pages or Heroku) that has been deleted or abandoned. An attacker can claim that service and take control of the subdomain. GhostClaim automates the detection of this vulnerability across all subdomains of a target domain.</div></div>
    </div>
    <div class="faq-item">
      <div class="faq-q">Can I use the Network Monitor on my home WiFi?</div>
      <div class="faq-a"><div class="faq-a-inner">Yes. The Network Monitor is specifically designed for home users, IT administrators, and small businesses. You can run it on Linux (including Kali), Windows 10/11 with Npcap, or Android via Termux if rooted. The dashboard is viewable from any browser on the same network.</div></div>
    </div>
    <div class="faq-item">
      <div class="faq-q">Is ShadowMap fully free now?</div>
      <div class="faq-a"><div class="faq-a-inner">Yes. ShadowMap was previously split into Free and Pro editions. It's now a single fully open-source release with all features included — subdomain enumeration, DNS recon, technology fingerprinting, and port scanning — along with improved detection accuracy and fewer false positives.</div></div>
    </div>
    <div class="faq-item">
      <div class="faq-q">What is the difference between Free and Pro versions?</div>
      <div class="faq-a"><div class="faq-a-inner">ShadowMap is now fully open source with no Pro split. For GhostClaim, the Free version covers core detection with 10 service fingerprints, while GhostClaim Pro adds 30+ service fingerprints, stealth modes, JSON export, and HTML/PDF report generation.</div></div>
    </div>
    <div class="faq-item">
      <div class="faq-q">How do I get a Pro version?</div>
      <div class="faq-a"><div class="faq-a-inner">Reach out to us via the contact options on our Services page. We send you the files directly — no payment platform, no license key, no internet activation required.</div></div>
    </div>
    <div class="faq-item">
      <div class="faq-q">How do I report a bug or suggest a feature?</div>
      <div class="faq-a"><div class="faq-a-inner">Open an issue on the relevant GitHub repository. We actively read and respond to issues.</div></div>
    </div>
  </div>
</div>

<div class="cta-band r">
  <h2>Ready to get started?</h2>
  <p>Get our tools free on GitHub or check out our professional security services.</p>
  <div class="cta-btns">
    <a href="https://github.com/siparsecurity" target="_blank" class="cta-btn-white">⭐ Get the Tools Free</a>
    <a href="/services.html" class="cta-btn-ghost">Our Services →</a>
  </div>
</div>

<footer>
  <div class="footer-inner">
    <div>
      <div class="footer-logo">SIPAR SECURITY</div>
      <p class="footer-tag">Open-source cybersecurity tools and professional security services. Built in Pakistan.</p>
      <div class="footer-copy">© 2026 Sipar Security · MIT License · Pakistan 🇵🇰</div>
    </div>
    <div>
      <div class="footer-h">Tools</div>
      <ul class="footer-links">
        <li><a href="https://github.com/siparsecurity/network-monitor-v3" target="_blank">Network Monitor v3.0</a></li>
        <li><a href="https://github.com/siparsecurity/shadowmap" target="_blank">ShadowMap (Open Source)</a></li>
        <li><a href="https://github.com/siparsecurity/ghostclaim" target="_blank">GhostClaim Free</a></li>
        <li><a href="https://github.com/siparsecurity/ghostclaim-pro" target="_blank">GhostClaim Pro</a></li>
      </ul>
    </div>
    <div>
      <div class="footer-h">Company</div>
      <ul class="footer-links">
        <li><a href="#founder">About</a></li>
        <li><a href="/services.html">Services</a></li>
        <li><a href="#faq">FAQ</a></li>
        <li><a href="https://github.com/siparsecurity" target="_blank">GitHub</a></li>
      </ul>
    </div>
  </div>
</footer>

<script>
  const els = document.querySelectorAll('.r');
  const obs = new IntersectionObserver(entries => {
    entries.forEach((e,i) => { if(e.isIntersecting) setTimeout(()=>e.target.classList.add('on'), i*60); });
  }, {threshold:0.05});
  els.forEach(e=>obs.observe(e));

  document.querySelectorAll('.faq-q').forEach(q => {
    q.addEventListener('click', () => {
      const item = q.parentElement;
      const isOpen = item.classList.contains('open');
      document.querySelectorAll('.faq-item').forEach(i => i.classList.remove('open'));
      if(!isOpen) item.classList.add('open');
    });
  });
</script>

</body>
</html>
