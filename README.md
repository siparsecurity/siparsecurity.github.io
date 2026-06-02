<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Sipar Security</title>
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }

    body {
      background: #0a0a0a;
      color: #e0e0e0;
      font-family: 'Segoe UI', sans-serif;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 2rem;
    }

    .badge {
      background: #1a1a2e;
      border: 1px solid #00ff9f33;
      color: #00ff9f;
      font-size: 0.75rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      padding: 0.4rem 1rem;
      border-radius: 999px;
      margin-bottom: 2rem;
    }

    h1 {
      font-size: 3rem;
      font-weight: 700;
      color: #ffffff;
      margin-bottom: 0.5rem;
      text-align: center;
    }

    h1 span { color: #00ff9f; }

    .tagline {
      font-size: 1.1rem;
      color: #888;
      text-align: center;
      max-width: 480px;
      line-height: 1.6;
      margin-bottom: 3rem;
    }

    .features {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
      justify-content: center;
      margin-bottom: 3rem;
    }

    .feature {
      background: #111;
      border: 1px solid #222;
      border-radius: 10px;
      padding: 1rem 1.25rem;
      font-size: 0.9rem;
      color: #ccc;
      width: 200px;
      text-align: center;
    }

    .feature .icon { font-size: 1.5rem; margin-bottom: 0.5rem; }

    .status {
      background: #0f2a1a;
      border: 1px solid #00ff9f44;
      border-radius: 10px;
      padding: 1rem 2rem;
      text-align: center;
      margin-bottom: 3rem;
    }

    .status p { color: #888; font-size: 0.9rem; margin-bottom: 0.25rem; }
    .status strong { color: #00ff9f; }

    .links { display: flex; gap: 1rem; flex-wrap: wrap; justify-content: center; }

    .links a {
      background: #111;
      border: 1px solid #333;
      color: #ccc;
      text-decoration: none;
      padding: 0.6rem 1.25rem;
      border-radius: 8px;
      font-size: 0.9rem;
      transition: border-color 0.2s, color 0.2s;
    }

    .links a:hover { border-color: #00ff9f; color: #00ff9f; }

    footer {
      margin-top: 4rem;
      color: #444;
      font-size: 0.8rem;
    }
  </style>
</head>
<body>

  <div class="badge">Cybersecurity Tools</div>

  <h1>Sipar <span>Security</span></h1>
  <p class="tagline">
    Open-source network monitoring tools built for home users,
    IT admins, and small businesses.
  </p>

  <div class="features">
    <div class="feature">
      <div class="icon">🔍</div>
      Device Detection
    </div>
    <div class="feature">
      <div class="icon">📡</div>
      Real-Time Tracking
    </div>
    <div class="feature">
      <div class="icon">📋</div>
      Event Logging
    </div>
    <div class="feature">
      <div class="icon">🛡️</div>
      ARP Spoofing Detection
    </div>
  </div>

  <div class="status">
    <p>First tool currently in active development</p>
    <strong>Release coming soon — follow us on GitHub</strong>
  </div>

  <div class="links">
    <a href="https://github.com/siparsecurity" target="_blank">⭐ GitHub</a>
    <a href="https://linkedin.com/company/siparsecurity" target="_blank">💼 LinkedIn</a>
    <a href="mailto:siparsecurity@gmail.com">📧 Contact</a>
  </div>

  <footer>© 2026 Sipar Security · Pakistan</footer>

</body>
</html>
