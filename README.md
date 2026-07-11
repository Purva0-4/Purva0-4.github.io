[index.html](https://github.com/user-attachments/files/29932031/index.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Purva Patel — Cyber Security Portfolio</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@400;500;600;700&family=IBM+Plex+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0F1417;
    --panel: #161D21;
    --panel-border: #232C31;
    --text: #E8EDF0;
    --text-muted: #8B98A0;
    --text-dim: #566067;
    --accent: #E8A33D;
    --accent-dim: #6b5027;
    --info: #4FA8C9;
    --sev-critical: #D9534F;
    --sev-high: #E8A33D;
    --sev-medium: #4FA8C9;
    --sev-low: #6B9B6E;
    --mono: 'IBM Plex Mono', monospace;
    --sans: 'IBM Plex Sans', sans-serif;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--sans);
    line-height: 1.6;
  }

  @media (prefers-reduced-motion: reduce) {
    * { animation-duration: 0.01ms !important; animation-iteration-count: 1 !important; transition-duration: 0.01ms !important; }
  }

  a { color: inherit; }

  /* ---------- NAV ---------- */
  .statusbar {
    position: sticky;
    top: 0;
    z-index: 50;
    background: rgba(15,20,23,0.92);
    backdrop-filter: blur(8px);
    border-bottom: 1px solid var(--panel-border);
  }
  .statusbar-inner {
    max-width: 980px;
    margin: 0 auto;
    padding: 14px 24px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-family: var(--mono);
    font-size: 13px;
  }
  .statusbar-brand {
    display: flex;
    align-items: center;
    gap: 8px;
    color: var(--text);
    font-weight: 600;
    letter-spacing: 0.02em;
  }
  .status-dot {
    width: 7px; height: 7px; border-radius: 50%;
    background: var(--sev-low);
    box-shadow: 0 0 6px var(--sev-low);
  }
  .statusbar-links {
    display: flex;
    gap: 22px;
  }
  .statusbar-links a {
    text-decoration: none;
    color: var(--text-muted);
    transition: color 0.15s ease;
  }
  .statusbar-links a:hover, .statusbar-links a:focus-visible { color: var(--accent); }

  @media (max-width: 640px) {
    .statusbar-links { gap: 14px; font-size: 12px; }
  }

  /* ---------- HERO ---------- */
  .hero {
    max-width: 980px;
    margin: 0 auto;
    padding: 90px 24px 70px;
  }
  .boot-log {
    font-family: var(--mono);
    font-size: 13px;
    color: var(--text-dim);
    margin-bottom: 36px;
    min-height: 132px;
  }
  .boot-log .line { opacity: 0; animation: fadeIn 0.3s ease forwards; white-space: pre-wrap; }
  .boot-log .ok { color: var(--sev-low); }
  .boot-log .tag { color: var(--info); }
  @keyframes fadeIn { to { opacity: 1; } }

  .hero-name {
    font-family: var(--sans);
    font-weight: 700;
    font-size: clamp(2.2rem, 6vw, 3.4rem);
    letter-spacing: -0.02em;
    line-height: 1.05;
    opacity: 0;
    animation: revealUp 0.5s ease forwards;
    animation-delay: 2.4s;
  }
  .hero-role {
    font-family: var(--mono);
    color: var(--accent);
    font-size: 15px;
    margin-top: 14px;
    opacity: 0;
    animation: revealUp 0.5s ease forwards;
    animation-delay: 2.65s;
  }
  .hero-desc {
    margin-top: 22px;
    max-width: 620px;
    color: var(--text-muted);
    font-size: 16px;
    opacity: 0;
    animation: revealUp 0.5s ease forwards;
    animation-delay: 2.85s;
  }
  @keyframes revealUp {
    from { opacity: 0; transform: translateY(8px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .hero-links {
    margin-top: 30px;
    display: flex;
    gap: 14px;
    flex-wrap: wrap;
    opacity: 0;
    animation: revealUp 0.5s ease forwards;
    animation-delay: 3.05s;
  }
  .btn {
    font-family: var(--mono);
    font-size: 13px;
    padding: 10px 18px;
    border-radius: 3px;
    text-decoration: none;
    border: 1px solid var(--panel-border);
    transition: border-color 0.15s ease, color 0.15s ease, background 0.15s ease;
  }
  .btn-primary {
    background: var(--accent);
    color: #1a1305;
    border-color: var(--accent);
    font-weight: 600;
  }
  .btn-primary:hover { background: #f0b155; }
  .btn-ghost { color: var(--text-muted); }
  .btn-ghost:hover { color: var(--text); border-color: var(--text-dim); }

  /* ---------- SECTION SHELL ---------- */
  section.block {
    max-width: 980px;
    margin: 0 auto;
    padding: 60px 24px;
    border-top: 1px solid var(--panel-border);
  }
  .block-head {
    display: flex;
    align-items: baseline;
    gap: 12px;
    margin-bottom: 30px;
  }
  .block-tag {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--text-dim);
    letter-spacing: 0.08em;
  }
  .block-title {
    font-family: var(--sans);
    font-weight: 700;
    font-size: 1.5rem;
    letter-spacing: -0.01em;
  }

  /* ---------- ABOUT ---------- */
  .about-text { color: var(--text-muted); max-width: 680px; font-size: 15.5px; }
  .about-text p + p { margin-top: 14px; }
  .about-text strong { color: var(--text); font-weight: 600; }

  /* ---------- TIMELINE (log entries) ---------- */
  .log-entry {
    display: grid;
    grid-template-columns: 130px 1fr;
    gap: 20px;
    padding: 16px 0;
    border-bottom: 1px solid var(--panel-border);
  }
  .log-entry:first-child { padding-top: 0; }
  .log-entry:last-child { border-bottom: none; }
  .log-time {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--text-dim);
    padding-top: 3px;
  }
  .log-org { font-weight: 600; font-size: 15px; }
  .log-role { color: var(--accent); font-family: var(--mono); font-size: 12.5px; margin-top: 2px; }
  .log-desc { color: var(--text-muted); font-size: 14.5px; margin-top: 8px; }

  @media (max-width: 640px) {
    .log-entry { grid-template-columns: 1fr; gap: 4px; }
  }

  /* ---------- PROJECTS ---------- */
  .project-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(270px, 1fr));
    gap: 16px;
  }
  .project-card {
    background: var(--panel);
    border: 1px solid var(--panel-border);
    border-radius: 6px;
    padding: 20px;
    display: flex;
    flex-direction: column;
    gap: 10px;
    transition: border-color 0.15s ease, transform 0.15s ease;
  }
  .project-card:hover { border-color: var(--text-dim); transform: translateY(-2px); }
  .card-top { display: flex; align-items: center; justify-content: space-between; gap: 8px; }
  .sev-badge {
    font-family: var(--mono);
    font-size: 10.5px;
    font-weight: 600;
    letter-spacing: 0.04em;
    padding: 3px 8px;
    border-radius: 3px;
    text-transform: uppercase;
    white-space: nowrap;
  }
  .sev-critical { background: rgba(217,83,79,0.15); color: var(--sev-critical); }
  .sev-high { background: rgba(232,163,61,0.15); color: var(--sev-high); }
  .sev-medium { background: rgba(79,168,201,0.15); color: var(--sev-medium); }
  .sev-low { background: rgba(107,155,110,0.15); color: var(--sev-low); }

  .status-pill {
    font-family: var(--mono);
    font-size: 10.5px;
    color: var(--text-dim);
    border: 1px solid var(--panel-border);
    padding: 2px 8px;
    border-radius: 10px;
  }
  .project-title { font-weight: 600; font-size: 15.5px; }
  .project-desc { color: var(--text-muted); font-size: 13.5px; flex-grow: 1; }
  .project-stack {
    font-family: var(--mono);
    font-size: 11px;
    color: var(--text-dim);
  }
  .project-links { display: flex; gap: 14px; margin-top: 4px; }
  .project-links a {
    font-family: var(--mono);
    font-size: 12px;
    color: var(--info);
    text-decoration: none;
  }
  .project-links a:hover { text-decoration: underline; }
  .project-links .placeholder { color: var(--text-dim); }

  /* ---------- SKILLS ---------- */
  .skill-groups { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 24px; }
  .skill-group-label { font-family: var(--mono); font-size: 12px; color: var(--text-dim); margin-bottom: 10px; letter-spacing: 0.05em; }
  .skill-tags { display: flex; flex-wrap: wrap; gap: 8px; }
  .skill-tag {
    font-family: var(--mono);
    font-size: 12.5px;
    color: var(--text-muted);
    border: 1px solid var(--panel-border);
    padding: 5px 10px;
    border-radius: 3px;
  }

  /* ---------- CERTS ---------- */
  .cert-list { display: flex; flex-direction: column; gap: 10px; }
  .cert-item {
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 14.5px;
    color: var(--text-muted);
  }
  .cert-check { color: var(--sev-low); font-family: var(--mono); }

  /* ---------- CONTACT / FOOTER ---------- */
  .contact-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
    gap: 16px;
  }
  .contact-card {
    background: var(--panel);
    border: 1px solid var(--panel-border);
    border-radius: 6px;
    padding: 18px;
    text-decoration: none;
    color: var(--text);
    transition: border-color 0.15s ease;
  }
  .contact-card:hover { border-color: var(--accent); }
  .contact-label { font-family: var(--mono); font-size: 11px; color: var(--text-dim); margin-bottom: 6px; }
  .contact-value { font-weight: 600; font-size: 14.5px; word-break: break-word; }

  footer {
    max-width: 980px;
    margin: 0 auto;
    padding: 30px 24px 60px;
    font-family: var(--mono);
    font-size: 12px;
    color: var(--text-dim);
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    gap: 10px;
  }

  :focus-visible { outline: 2px solid var(--accent); outline-offset: 2px; }
</style>
</head>
<body>

<div class="statusbar">
  <div class="statusbar-inner">
    <div class="statusbar-brand"><span class="status-dot"></span>PURVA.PATEL</div>
    <div class="statusbar-links">
      <a href="#about">about</a>
      <a href="#experience">experience</a>
      <a href="#projects">projects</a>
      <a href="#skills">skills</a>
      <a href="#contact">contact</a>
    </div>
  </div>
</div>

<div class="hero">
  <div class="boot-log" id="bootLog"></div>
  <h1 class="hero-name">Purva Patel</h1>
  <div class="hero-role">Computer Science &amp; Cyber Security — BSc Hons, University of Greenwich</div>
  <p class="hero-desc">Building practical, hands-on security work — from log analysis to vulnerability assessment — to back up a CV full of internships with proof I can actually do the job.</p>
  <div class="hero-links">
    <a class="btn btn-primary" href="#projects">View projects</a>
    <a class="btn btn-ghost" href="https://github.com/YOUR-USERNAME" target="_blank" rel="noopener">GitHub ↗</a>
    <a class="btn btn-ghost" href="https://www.linkedin.com/in/purvapatel-990161243" target="_blank" rel="noopener">LinkedIn ↗</a>
  </div>
</div>

<section class="block" id="about">
  <div class="block-head">
    <span class="block-tag">01 · SUMMARY</span>
    <span class="block-title">About</span>
  </div>
  <div class="about-text">
    <p>I'm a final-year <strong>Computer Science (Cyber Security)</strong> student who has spent the last few years getting exposure across the industry — internships and structured placements at <strong>Barclays, Vodafone, Tata Consultancy Services, Heathrow, Fujitsu, and Allianz</strong> — covering everything from accessible banking design to biometric authentication and IT security operations.</p>
    <p>I'm now shifting from learning-about-security to doing-security: building labs, breaking things safely, and writing up what I find. I like taking things apart to understand them — I've assembled PCs, built home networks, and installed a security camera system from scratch.</p>
  </div>
</section>

<section class="block" id="experience">
  <div class="block-head">
    <span class="block-tag">02 · LOG</span>
    <span class="block-title">Experience</span>
  </div>

  <div class="log-entry">
    <div class="log-time">2024 — now</div>
    <div>
      <div class="log-org">Lidl GB</div>
      <div class="log-role">Customer Service Assistant</div>
      <div class="log-desc">Day-to-day operations across a 15+ person team — POS systems, inventory, prioritisation under time pressure.</div>
    </div>
  </div>

  <div class="log-entry">
    <div class="log-time">Jul 2024</div>
    <div>
      <div class="log-org">Allianz</div>
      <div class="log-role">Insurance Work Experience</div>
      <div class="log-desc">Underwriting, claims processing and risk analysis; exposure to data-driven pricing models.</div>
    </div>
  </div>

  <div class="log-entry">
    <div class="log-time">Jul – Aug 2023</div>
    <div>
      <div class="log-org">Heathrow</div>
      <div class="log-role">Cyber Security Intern</div>
      <div class="log-desc">Network security dashboard monitoring, biometric authentication exposure, incident response drills, GDPR/ISO 27001 awareness.</div>
    </div>
  </div>

  <div class="log-entry">
    <div class="log-time">Mar – Apr 2023</div>
    <div>
      <div class="log-org">Vodafone</div>
      <div class="log-role">Technology in Business Intern</div>
      <div class="log-desc">UX evaluation of app interfaces, product innovation, go-to-market strategy for telecom features.</div>
    </div>
  </div>

  <div class="log-entry">
    <div class="log-time">Jul 2022</div>
    <div>
      <div class="log-org">Fujitsu</div>
      <div class="log-role">Technology &amp; Innovation Intern</div>
      <div class="log-desc">Researched AI, quantum computing and sustainable IT; presented on AI in cybersecurity.</div>
    </div>
  </div>

  <div class="log-entry">
    <div class="log-time">Jun – Jul 2022</div>
    <div>
      <div class="log-org">Barclays</div>
      <div class="log-role">Technology Solutions Intern</div>
      <div class="log-desc">Led a project on accessible banking — screen-reader support, contrast, voice navigation prototype. Presented to senior management.</div>
    </div>
  </div>

  <div class="log-entry">
    <div class="log-time">Jun 2022</div>
    <div>
      <div class="log-org">Tata Consultancy Services</div>
      <div class="log-role">Cyber Security Intern</div>
      <div class="log-desc">Threat identification, network security and encryption fundamentals; vulnerability scanning in a controlled environment.</div>
    </div>
  </div>
</section>

<section class="block" id="projects">
  <div class="block-head">
    <span class="block-tag">03 · BUILD</span>
    <span class="block-title">Projects</span>
  </div>
  <div class="project-grid">

    <div class="project-card">
      <div class="card-top">
        <span class="sev-badge sev-high">Flagship</span>
        <span class="status-pill">in progress</span>
      </div>
      <div class="project-title">Home SOC — Log Analysis Lab</div>
      <div class="project-desc">A small virtual SOC: simulated attacks (brute force, malicious process execution) fed into a SIEM, with detections and an incident write-up.</div>
      <div class="project-stack">Splunk Free / ELK · Atomic Red Team · VirtualBox</div>
      <div class="project-links">
        <a href="#" class="placeholder">write-up (coming soon)</a>
        <a href="#" class="placeholder">repo (coming soon)</a>
      </div>
    </div>

    <div class="project-card">
      <div class="card-top">
        <span class="sev-badge sev-high">High</span>
        <span class="status-pill">planned</span>
      </div>
      <div class="project-title">Vulnerability Assessment Report</div>
      <div class="project-desc">Nmap + OpenVAS scan of a deliberately vulnerable host, written up as a real client-style report with CVSS scoring and remediation steps.</div>
      <div class="project-stack">Nmap · OpenVAS · Metasploitable2</div>
      <div class="project-links">
        <a href="#" class="placeholder">write-up (coming soon)</a>
      </div>
    </div>

    <div class="project-card">
      <div class="card-top">
        <span class="sev-badge sev-medium">Medium</span>
        <span class="status-pill">planned</span>
      </div>
      <div class="project-title">Web App Security Write-ups</div>
      <div class="project-desc">Working through PortSwigger's Web Security Academy — SQLi, XSS, and broken auth labs documented with screenshots and root-cause fixes.</div>
      <div class="project-stack">Burp Suite · OWASP Juice Shop</div>
      <div class="project-links">
        <a href="#" class="placeholder">write-up (coming soon)</a>
      </div>
    </div>

    <div class="project-card">
      <div class="card-top">
        <span class="sev-badge sev-medium">Medium</span>
        <span class="status-pill">planned</span>
      </div>
      <div class="project-title">Security Tooling in Python</div>
      <div class="project-desc">A small utility — likely a suspicious-login log parser or a breach/password checker against the HaveIBeenPwned API.</div>
      <div class="project-stack">Python</div>
      <div class="project-links">
        <a href="#" class="placeholder">repo (coming soon)</a>
      </div>
    </div>

    <div class="project-card">
      <div class="card-top">
        <span class="sev-badge sev-low">Low</span>
        <span class="status-pill">in progress</span>
      </div>
      <div class="project-title">Home Network Build</div>
      <div class="project-desc">Documenting the network I've already built — segmentation, firewall rules, and the security camera system, with a proper network diagram.</div>
      <div class="project-stack">pfSense · VLANs · Raspberry Pi</div>
      <div class="project-links">
        <a href="#" class="placeholder">write-up (coming soon)</a>
      </div>
    </div>

    <div class="project-card">
      <div class="card-top">
        <span class="sev-badge sev-low">Low</span>
        <span class="status-pill">ongoing</span>
      </div>
      <div class="project-title">TryHackMe Write-ups</div>
      <div class="project-desc">Rolling collection of room walkthroughs from the Pre Security and Jr Penetration Tester paths.</div>
      <div class="project-stack">TryHackMe</div>
      <div class="project-links">
        <a href="#" class="placeholder">write-ups (coming soon)</a>
      </div>
    </div>

  </div>
</section>

<section class="block" id="skills">
  <div class="block-head">
    <span class="block-tag">04 · SCAN RESULT</span>
    <span class="block-title">Skills</span>
  </div>
  <div class="skill-groups">
    <div>
      <div class="skill-group-label">SECURITY</div>
      <div class="skill-tags">
        <span class="skill-tag">Log Analysis</span>
        <span class="skill-tag">Web Security</span>
        <span class="skill-tag">Vulnerability Scanning</span>
        <span class="skill-tag">Network Fundamentals</span>
        <span class="skill-tag">GDPR / ISO 27001 awareness</span>
      </div>
    </div>
    <div>
      <div class="skill-group-label">TECHNICAL</div>
      <div class="skill-tags">
        <span class="skill-tag">Python</span>
        <span class="skill-tag">Data Visualisation Tools</span>
        <span class="skill-tag">PC Build &amp; Home Networking</span>
      </div>
    </div>
    <div>
      <div class="skill-group-label">PEOPLE</div>
      <div class="skill-tags">
        <span class="skill-tag">Communication</span>
        <span class="skill-tag">Leadership</span>
        <span class="skill-tag">Team Collaboration</span>
      </div>
    </div>
  </div>
</section>

<section class="block" id="certifications">
  <div class="block-head">
    <span class="block-tag">05 · VERIFIED</span>
    <span class="block-title">Certifications</span>
  </div>
  <div class="cert-list">
    <div class="cert-item"><span class="cert-check">[✓]</span> Cybersecurity Job Simulation — Tata Consultancy Services (Forage)</div>
    <div class="cert-item"><span class="cert-check">[✓]</span> Shields Up: Cybersecurity Job Simulation (Forage)</div>
    <div class="cert-item"><span class="cert-check">[✓]</span> Cyber Job Simulation — Deloitte Australia (Forage)</div>
    <div class="cert-item"><span class="cert-check">[✓]</span> Software Engineering Job Simulation (Forage)</div>
  </div>
</section>

<section class="block" id="contact">
  <div class="block-head">
    <span class="block-tag">06 · CONNECT</span>
    <span class="block-title">Contact</span>
  </div>
  <div class="contact-grid">
    <a class="contact-card" href="mailto:32purvapatel@gmail.com">
      <div class="contact-label">EMAIL</div>
      <div class="contact-value">32purvapatel@gmail.com</div>
    </a>
    <a class="contact-card" href="https://www.linkedin.com/in/purvapatel-990161243" target="_blank" rel="noopener">
      <div class="contact-label">LINKEDIN</div>
      <div class="contact-value">/in/purvapatel</div>
    </a>
    <a class="contact-card" href="https://github.com/YOUR-USERNAME" target="_blank" rel="noopener">
      <div class="contact-label">GITHUB</div>
      <div class="contact-value">@YOUR-USERNAME</div>
    </a>
  </div>
</section>

<footer>
  <span>© 2026 Purva Patel</span>
  <span>Built for the next role in cyber security</span>
</footer>

<script>
  const bootLines = [
    { text: '$ whoami', delay: 0 },
    { text: 'purva.patel', delay: 250, cls: 'tag' },
    { text: '$ security-scan --profile', delay: 550 },
    { text: '[ok] BSc Computer Science (Cyber Security) — verified', delay: 900, cls: 'ok' },
    { text: '[ok] 7 internships indexed — Barclays, Vodafone, TCS, Heathrow, Fujitsu, Allianz', delay: 1300, cls: 'ok' },
    { text: '[..] loading projects module', delay: 1750 },
    { text: '$ access granted', delay: 2150, cls: 'ok' },
  ];

  const container = document.getElementById('bootLog');
  bootLines.forEach(line => {
    const el = document.createElement('div');
    el.className = 'line' + (line.cls ? ' ' + line.cls : '');
    el.style.animationDelay = (line.delay / 1000) + 's';
    el.textContent = line.text;
    container.appendChild(el);
  });
</script>

</body>
</html>
