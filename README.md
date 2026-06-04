
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SIPAR SECURITY</title>

<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">

<style>
*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:'Inter',sans-serif;
}

body{
background:#050816;
color:white;
overflow-x:hidden;
}

body::before{
content:'';
position:fixed;
width:100%;
height:100%;
background:
radial-gradient(circle at 20% 20%,rgba(0,255,255,.08),transparent 35%),
radial-gradient(circle at 80% 30%,rgba(0,100,255,.08),transparent 35%),
radial-gradient(circle at 50% 80%,rgba(0,255,150,.05),transparent 40%);
z-index:-1;
}

.container{
width:90%;
max-width:1200px;
margin:auto;
}

nav{
display:flex;
justify-content:space-between;
align-items:center;
padding:25px 0;
}

.logo{
font-size:1.5rem;
font-weight:800;
letter-spacing:2px;
}

.nav-links{
display:flex;
gap:25px;
}

.nav-links a{
color:#a5b4fc;
text-decoration:none;
transition:.3s;
}

.nav-links a:hover{
color:white;
}

.hero{
padding:120px 0;
text-align:center;
}

.badge{
display:inline-block;
padding:10px 20px;
background:rgba(255,255,255,.05);
border:1px solid rgba(255,255,255,.1);
border-radius:100px;
margin-bottom:30px;
color:#67e8f9;
backdrop-filter:blur(10px);
}

.hero h1{
font-size:5rem;
font-weight:800;
line-height:1;
margin-bottom:20px;
}

.hero p{
max-width:800px;
margin:auto;
font-size:1.2rem;
color:#94a3b8;
line-height:1.8;
}

.buttons{
margin-top:40px;
display:flex;
justify-content:center;
gap:20px;
flex-wrap:wrap;
}

.btn{
padding:16px 30px;
border-radius:12px;
text-decoration:none;
font-weight:600;
transition:.3s;
}

.primary{
background:linear-gradient(135deg,#06b6d4,#2563eb);
color:white;
}

.primary:hover{
transform:translateY(-3px);
}

.secondary{
border:1px solid rgba(255,255,255,.1);
color:white;
background:rgba(255,255,255,.03);
}

.secondary:hover{
background:rgba(255,255,255,.08);
}

.section{
padding:100px 0;
}

.section-title{
font-size:3rem;
text-align:center;
margin-bottom:20px;
}

.section-subtitle{
text-align:center;
max-width:800px;
margin:auto;
color:#94a3b8;
line-height:1.8;
margin-bottom:60px;
}

.grid{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
gap:25px;
}

.card{
background:rgba(255,255,255,.04);
border:1px solid rgba(255,255,255,.08);
border-radius:20px;
padding:30px;
backdrop-filter:blur(20px);
transition:.3s;
}

.card:hover{
transform:translateY(-5px);
border-color:#06b6d4;
}

.card h3{
margin-bottom:15px;
font-size:1.2rem;
}

.card p{
color:#94a3b8;
line-height:1.7;
}

.timeline{
display:grid;
grid-template-columns:1fr 1fr;
gap:30px;
margin-top:50px;
}

.version{
background:rgba(255,255,255,.04);
padding:35px;
border-radius:20px;
border:1px solid rgba(255,255,255,.08);
}

.version h3{
font-size:2rem;
margin-bottom:15px;
}

.version ul{
margin-top:15px;
padding-left:20px;
line-height:2;
color:#cbd5e1;
}

.founder{
text-align:center;
}

.founder h2{
font-size:3rem;
margin-bottom:15px;
}

.founder p{
max-width:700px;
margin:auto;
color:#94a3b8;
line-height:1.8;
}

.socials{
display:flex;
justify-content:center;
gap:20px;
margin-top:40px;
flex-wrap:wrap;
}

.socials a{
padding:14px 24px;
border-radius:12px;
text-decoration:none;
color:white;
background:rgba(255,255,255,.04);
border:1px solid rgba(255,255,255,.08);
}

footer{
padding:50px 0;
text-align:center;
color:#64748b;
border-top:1px solid rgba(255,255,255,.08);
margin-top:100px;
}

@media(max-width:768px){

.hero h1{
font-size:3rem;
}

.timeline{
grid-template-columns:1fr;
}

.nav-links{
display:none;
}

.section-title{
font-size:2rem;
}
}
</style>
</head>

<body>

<div class="container">

<nav>
<div class="logo">SIPAR SECURITY</div>

<div class="nav-links">
<a href="#about">About</a>
<a href="#product">Product</a>
<a href="#roadmap">Roadmap</a>
<a href="#founder">Founder</a>
</div>
</nav>

<section class="hero">

<div class="badge">
🚀 VERSION 1.0 RELEASED • VERSION 2.0 IN DEVELOPMENT
</div>

<h1>
SIPAR<br>
SECURITY
</h1>

<p>
Building open-source cybersecurity tools focused on network visibility,
threat detection and SOC-inspired monitoring for researchers,
students, home labs and modern organizations.
</p>

<div class="buttons">

<a class="btn primary"
href="https://github.com/siparsecurity/network-monitor/releases/tag/v0.1-layer1">
Download v1.0
</a>

<a class="btn secondary"
href="https://github.com/siparsecurity/network-monitor">
View Source
</a>

</div>

</section>

<section id="about" class="section">

<h2 class="section-title">
About Sipar Security
</h2>

<p class="section-subtitle">
Sipar Security is an independent cybersecurity startup founded by
Sayed Muhammad Subayyal. The company focuses on practical,
open-source cybersecurity tooling, network monitoring and
threat detection solutions.
</p>

</section>

<section id="product" class="section">

<h2 class="section-title">
Sipar Network Monitor
</h2>

<p class="section-subtitle">
A lightweight network visibility and security monitoring platform
designed to provide real-time awareness of network activity and
potential security threats.
</p>

<div class="grid">

<div class="card">
<h3>Device Discovery</h3>
<p>
Automatically identify and track devices connected to the network.
</p>
</div>

<div class="card">
<h3>Threat Detection</h3>
<p>
Detect suspicious network behavior and security anomalies.
</p>
</div>

<div class="card">
<h3>SOC Dashboard</h3>
<p>
Monitor network activity through a clean and centralized dashboard.
</p>
</div>

<div class="card">
<h3>Risk Scoring</h3>
<p>
Track security events and assign risk levels to monitored devices.
</p>
</div>

<div class="card">
<h3>Event Logging</h3>
<p>
Store and analyze security events for investigation and auditing.
</p>
</div>

<div class="card">
<h3>ARP Spoof Detection</h3>
<p>
Identify ARP spoofing attempts and generate alerts.
</p>
</div>

</div>

</section>

<section id="roadmap" class="section">

<h2 class="section-title">
Roadmap
</h2>

<div class="timeline">

<div class="version">

<h3>Version 1.0</h3>

<p>
Released on GitHub
</p>

<ul>
<li>Device Discovery</li>
<li>Network Monitoring</li>
<li>Event Logging</li>
<li>SOC Dashboard</li>
<li>Risk Tracking</li>
<li>ARP Detection</li>
</ul>

</div>

<div class="version">

<h3>Version 2.0</h3>

<p>
Currently in Development
</p>

<ul>
<li>Enhanced Detection Engine</li>
<li>Improved Dashboard</li>
<li>Advanced Event Correlation</li>
<li>Performance Improvements</li>
<li>Additional Security Features</li>
<li>Expanded Monitoring Capabilities</li>
</ul>

</div>

</div>

</section>

<section id="founder" class="section founder">

<h2>
Sayed Muhammad Subayyal
</h2>

<p>
Founder of Sipar Security. Building open-source cybersecurity
tools, network monitoring platforms and threat detection
solutions designed for practical use and continuous improvement.
</p>

<div class="socials">

<a href="https://github.com/siparsecurity">
GitHub
</a>

<a href="https://www.linkedin.com/company/126573957">
LinkedIn
</a>

<a href="https://x.com/SiparSecurity">
X (Twitter)
</a>

</div>

</section>

<footer>
© 2026 SIPAR SECURITY • Built in Pakistan
</footer>

</div>

</body>
</html>
