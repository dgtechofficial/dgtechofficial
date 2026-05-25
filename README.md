
<style>
  @import url('https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;700;800&display=swap');

  * { box-sizing: border-box; margin: 0; padding: 0; }

  .profile-root {
    font-family: 'Syne', sans-serif;
    background: #0a0e1a;
    color: #e2e8f0;
    padding: 2rem 1.5rem;
    min-height: 100vh;
    position: relative;
    overflow: hidden;
  }

  .grid-bg {
    position: fixed; inset: 0; pointer-events: none; z-index: 0;
    background-image:
      linear-gradient(rgba(0,242,254,0.04) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,242,254,0.04) 1px, transparent 1px);
    background-size: 40px 40px;
  }

  .content { position: relative; z-index: 1; max-width: 680px; margin: 0 auto; }

  .header { text-align: center; padding: 1.5rem 0 2rem; }

  .avatar-ring {
    width: 90px; height: 90px; border-radius: 50%;
    border: 2px solid #00f2fe;
    display: flex; align-items: center; justify-content: center;
    margin: 0 auto 1rem;
    position: relative;
    background: linear-gradient(135deg, #0a0e1a, #111827);
    box-shadow: 0 0 0 4px rgba(0,242,254,0.08), inset 0 0 20px rgba(0,242,254,0.05);
  }

  .avatar-inner {
    font-family: 'Space Mono', monospace;
    font-size: 22px; font-weight: 700;
    color: #00f2fe;
    letter-spacing: -1px;
  }

  .status-dot {
    position: absolute; bottom: 4px; right: 4px;
    width: 14px; height: 14px; border-radius: 50%;
    background: #22c55e;
    border: 2px solid #0a0e1a;
    animation: pulse-dot 2s infinite;
  }

  @keyframes pulse-dot {
    0%, 100% { box-shadow: 0 0 0 0 rgba(34,197,94,0.4); }
    50% { box-shadow: 0 0 0 6px rgba(34,197,94,0); }
  }

  .name {
    font-size: 28px; font-weight: 800;
    color: #ffffff;
    letter-spacing: -0.5px;
    margin-bottom: 4px;
  }

  .handle {
    font-family: 'Space Mono', monospace;
    font-size: 13px; color: #00f2fe;
    margin-bottom: 12px;
  }

  .tagline {
    font-size: 14px; color: #94a3b8;
    max-width: 360px; margin: 0 auto 1.25rem;
    line-height: 1.6;
  }

  .badge-row {
    display: flex; gap: 8px; justify-content: center; flex-wrap: wrap;
    margin-bottom: 1.25rem;
  }

  .badge {
    font-family: 'Space Mono', monospace;
    font-size: 11px; padding: 4px 10px;
    border-radius: 100px;
    border: 1px solid;
    letter-spacing: 0.3px;
  }

  .badge-cyan { border-color: rgba(0,242,254,0.4); color: #00f2fe; background: rgba(0,242,254,0.07); }
  .badge-green { border-color: rgba(34,197,94,0.4); color: #22c55e; background: rgba(34,197,94,0.07); }
  .badge-purple { border-color: rgba(139,92,246,0.4); color: #a78bfa; background: rgba(139,92,246,0.07); }

  .section { margin-bottom: 1.75rem; }

  .section-label {
    font-family: 'Space Mono', monospace;
    font-size: 11px; color: #00f2fe;
    letter-spacing: 2px; text-transform: uppercase;
    margin-bottom: 1rem;
    display: flex; align-items: center; gap: 8px;
  }

  .section-label::after {
    content: '';
    flex: 1; height: 1px;
    background: linear-gradient(to right, rgba(0,242,254,0.2), transparent);
  }

  .about-grid {
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 8px;
  }

  .about-item {
    background: rgba(255,255,255,0.03);
    border: 1px solid rgba(255,255,255,0.07);
    border-radius: 10px;
    padding: 12px 14px;
    display: flex; align-items: flex-start; gap: 10px;
  }

  .about-icon { font-size: 16px; margin-top: 1px; flex-shrink: 0; }
  .about-label { font-size: 11px; color: #64748b; margin-bottom: 2px; font-family: 'Space Mono', monospace; }
  .about-value { font-size: 13px; color: #cbd5e1; line-height: 1.4; }

  .stack-section { }

  .stack-category { margin-bottom: 1rem; }
  .stack-cat-label {
    font-size: 12px; color: #64748b;
    font-family: 'Space Mono', monospace;
    margin-bottom: 8px;
  }

  .pill-group { display: flex; flex-wrap: wrap; gap: 6px; }

  .pill {
    font-family: 'Space Mono', monospace;
    font-size: 11px; padding: 5px 11px;
    border-radius: 6px;
    border: 1px solid rgba(255,255,255,0.1);
    background: rgba(255,255,255,0.04);
    color: #94a3b8;
    transition: all 0.15s ease;
    cursor: default;
    display: flex; align-items: center; gap: 5px;
  }

  .pill:hover {
    border-color: rgba(0,242,254,0.35);
    color: #e2e8f0;
    background: rgba(0,242,254,0.07);
  }

  .pill-dot { width: 5px; height: 5px; border-radius: 50%; flex-shrink: 0; }

  .stats-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 8px; }

  .stat-card {
    background: rgba(255,255,255,0.03);
    border: 1px solid rgba(255,255,255,0.07);
    border-radius: 10px;
    padding: 14px 12px;
    text-align: center;
  }

  .stat-number {
    font-family: 'Space Mono', monospace;
    font-size: 22px; font-weight: 700;
    color: #00f2fe;
    margin-bottom: 2px;
  }

  .stat-label { font-size: 11px; color: #64748b; }

  .links-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 8px; }

  .link-card {
    background: rgba(255,255,255,0.03);
    border: 1px solid rgba(255,255,255,0.07);
    border-radius: 10px;
    padding: 12px 14px;
    display: flex; align-items: center; gap: 10px;
    text-decoration: none;
    color: inherit;
    transition: all 0.15s ease;
    cursor: pointer;
  }

  .link-card:hover {
    border-color: rgba(0,242,254,0.35);
    background: rgba(0,242,254,0.05);
  }

  .link-icon { font-size: 18px; flex-shrink: 0; }
  .link-platform { font-size: 11px; color: #64748b; font-family: 'Space Mono', monospace; }
  .link-handle { font-size: 13px; color: #cbd5e1; }

  .footer {
    text-align: center;
    padding-top: 1.5rem;
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    color: #334155;
    border-top: 1px solid rgba(255,255,255,0.05);
  }

  .views-badge {
    display: inline-flex; align-items: center; gap: 6px;
    background: rgba(0,242,254,0.07);
    border: 1px solid rgba(0,242,254,0.2);
    border-radius: 100px;
    padding: 5px 12px;
    font-family: 'Space Mono', monospace;
    font-size: 11px; color: #00f2fe;
    margin-bottom: 1rem;
  }

  .views-dot { width: 6px; height: 6px; border-radius: 50%; background: #00f2fe; animation: pulse-dot 2s infinite; }

  .cursor-blink {
    display: inline-block;
    width: 2px; height: 1em;
    background: #00f2fe;
    animation: blink 1s step-end infinite;
    vertical-align: text-bottom;
    margin-left: 2px;
  }

  @keyframes blink { 50% { opacity: 0; } }
</style>

<div class="profile-root">
  <div class="grid-bg"></div>
  <div class="content">

    <div class="header">
      <div class="views-badge"><span class="views-dot"></span>open to work</div>
      <div class="avatar-ring">
        <span class="avatar-inner">DG</span>
        <span class="status-dot"></span>
      </div>
      <div class="name">DGTECH Official<span class="cursor-blink"></span></div>
      <div class="handle">@dgtechofficial</div>
      <div class="tagline">Building impactful digital experiences — clean code, sleek interfaces, cutting-edge tech.</div>
      <div class="badge-row">
        <span class="badge badge-cyan">Full Stack Dev</span>
        <span class="badge badge-green">Open Source</span>
        <span class="badge badge-purple">AI Integration</span>
      </div>
    </div>

    <div class="section">
      <div class="section-label">About</div>
      <div class="about-grid">
        <div class="about-item">
          <span class="about-icon">🔭</span>
          <div>
            <div class="about-label">Currently</div>
            <div class="about-value">Scalable web apps & open-source tools</div>
          </div>
        </div>
        <div class="about-item">
          <span class="about-icon">🌱</span>
          <div>
            <div class="about-label">Learning</div>
            <div class="about-value">Advanced System Architecture & AI Integration</div>
          </div>
        </div>
        <div class="about-item">
          <span class="about-icon">💬</span>
          <div>
            <div class="about-label">Ask me about</div>
            <div class="about-value">Web Dev, UI/UX, Automation</div>
          </div>
        </div>
        <div class="about-item">
          <span class="about-icon">⚡</span>
          <div>
            <div class="about-label">Fun fact</div>
            <div class="about-value">Codes best when the sun sets & caffeine kicks in</div>
          </div>
        </div>
      </div>
    </div>

    <div class="section">
      <div class="section-label">Tech Stack</div>
      <div class="stack-section">

        <div class="stack-category">
          <div class="stack-cat-label">Frontend</div>
          <div class="pill-group">
            <span class="pill"><span class="pill-dot" style="background:#f7df1e"></span>JavaScript</span>
            <span class="pill"><span class="pill-dot" style="background:#e34f26"></span>HTML5</span>
            <span class="pill"><span class="pill-dot" style="background:#1572b6"></span>CSS3</span>
            <span class="pill"><span class="pill-dot" style="background:#38b2ac"></span>Tailwind</span>
            <span class="pill"><span class="pill-dot" style="background:#61dafb"></span>React</span>
            <span class="pill"><span class="pill-dot" style="background:#ffffff"></span>Next.js</span>
            <span class="pill"><span class="pill-dot" style="background:#4fc08d"></span>Vue.js</span>
            <span class="pill"><span class="pill-dot" style="background:#0769ad"></span>jQuery</span>
          </div>
        </div>

        <div class="stack-category" style="margin-top:12px">
          <div class="stack-cat-label">Backend & APIs</div>
          <div class="pill-group">
            <span class="pill"><span class="pill-dot" style="background:#6da55f"></span>Node.js</span>
            <span class="pill"><span class="pill-dot" style="background:#404d59"></span>Express.js</span>
            <span class="pill"><span class="pill-dot" style="background:#777bb4"></span>PHP</span>
            <span class="pill"><span class="pill-dot" style="background:#0052cc"></span>REST APIs</span>
          </div>
        </div>

        <div class="stack-category" style="margin-top:12px">
          <div class="stack-cat-label">Mobile & Systems</div>
          <div class="pill-group">
            <span class="pill"><span class="pill-dot" style="background:#7f52ff"></span>Kotlin</span>
            <span class="pill"><span class="pill-dot" style="background:#ed8b00"></span>Java</span>
          </div>
        </div>

        <div class="stack-category" style="margin-top:12px">
          <div class="stack-cat-label">Databases</div>
          <div class="pill-group">
            <span class="pill"><span class="pill-dot" style="background:#316192"></span>PostgreSQL</span>
            <span class="pill"><span class="pill-dot" style="background:#003545"></span>MariaDB</span>
            <span class="pill"><span class="pill-dot" style="background:#07405e"></span>SQLite</span>
          </div>
        </div>

      </div>
    </div>

    <div class="section">
      <div class="section-label">GitHub Stats</div>
      <div class="stats-grid">
        <div class="stat-card">
          <div class="stat-number">∞</div>
          <div class="stat-label">commits</div>
        </div>
        <div class="stat-card">
          <div class="stat-number">⬆️</div>
          <div class="stat-label">streak</div>
        </div>
        <div class="stat-card">
          <div class="stat-number">JS</div>
          <div class="stat-label">top language</div>
        </div>
      </div>
      <p style="font-family:'Space Mono',monospace;font-size:11px;color:#475569;text-align:center;margin-top:10px;">
        → Pin real stats via github-readme-stats in your actual README
      </p>
    </div>

    <div class="section">
      <div class="section-label">Connect</div>
      <div class="links-grid">
        <div class="link-card">
          <i class="ti ti-world link-icon" style="color:#00f2fe" aria-hidden="true"></i>
          <div>
            <div class="link-platform">Website</div>
            <div class="link-handle">your-website.com</div>
          </div>
        </div>
        <div class="link-card">
          <i class="ti ti-brand-linkedin link-icon" style="color:#0077b5" aria-hidden="true"></i>
          <div>
            <div class="link-platform">LinkedIn</div>
            <div class="link-handle">your-username</div>
          </div>
        </div>
        <div class="link-card">
          <i class="ti ti-brand-twitter link-icon" style="color:#1da1f2" aria-hidden="true"></i>
          <div>
            <div class="link-platform">Twitter / X</div>
            <div class="link-handle">your-username</div>
          </div>
        </div>
        <div class="link-card">
          <i class="ti ti-mail link-icon" style="color:#ea4335" aria-hidden="true"></i>
          <div>
            <div class="link-platform">Email</div>
            <div class="link-handle">your-email@example.com</div>
          </div>
        </div>
      </div>
    </div>

    <div class="footer">
      <div>profile views tracked via komarev.com/ghpvc</div>
    </div>

  </div>
</div>
