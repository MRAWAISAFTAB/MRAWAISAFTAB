<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Awais Aftab — Portfolio</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=SF+Pro+Display:wght@300;400;500;600;700&family=Nunito:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #f2f2f7;
    --card: rgba(255,255,255,0.82);
    --card-solid: #ffffff;
    --glass: rgba(255,255,255,0.55);
    --glass-border: rgba(255,255,255,0.75);
    --text: #1c1c1e;
    --text2: #48484a;
    --text3: #8e8e93;
    --accent: #007aff;
    --accent2: #5856d6;
    --green: #34c759;
    --orange: #ff9500;
    --pink: #ff2d55;
    --teal: #30b0c7;
    --tab-bg: rgba(255,255,255,0.72);
    --shadow: 0 8px 32px rgba(0,0,0,0.10), 0 2px 8px rgba(0,0,0,0.07);
    --shadow-sm: 0 2px 12px rgba(0,0,0,0.08);
    --radius: 16px;
    --radius-lg: 24px;
    --radius-xl: 32px;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }

  body {
    font-family: 'Nunito', -apple-system, sans-serif;
    background: var(--bg);
    color: var(--text);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* ── WALLPAPER BG ── */
  body::before {
    content: '';
    position: fixed; inset: 0; z-index: 0;
    background:
      radial-gradient(ellipse 80% 60% at 20% 10%, rgba(123,97,255,0.18) 0%, transparent 60%),
      radial-gradient(ellipse 60% 50% at 80% 20%, rgba(0,122,255,0.15) 0%, transparent 55%),
      radial-gradient(ellipse 70% 60% at 60% 90%, rgba(52,199,89,0.12) 0%, transparent 60%),
      radial-gradient(ellipse 50% 40% at 10% 80%, rgba(255,45,85,0.10) 0%, transparent 50%),
      linear-gradient(160deg, #e8eaf6 0%, #f3e5f5 30%, #e3f2fd 60%, #f1f8e9 100%);
    pointer-events: none;
  }

  .phone-wrap {
    display: flex;
    justify-content: center;
    align-items: flex-start;
    min-height: 100vh;
    padding: 40px 20px 120px;
    position: relative; z-index: 1;
  }

  /* ── PHONE FRAME ── */
  .phone {
    width: 393px;
    max-width: 100%;
    position: relative;
  }

  /* ── STATUS BAR ── */
  .statusbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 14px 24px 8px;
    font-size: 13px;
    font-weight: 600;
    color: var(--text);
    letter-spacing: 0.01em;
  }
  .statusbar-right { display: flex; gap: 6px; align-items: center; }
  .status-icon { width: 16px; height: 10px; }

  /* ── SCREENS ── */
  .screen { display: none; animation: fadeSlideUp 0.38s cubic-bezier(0.32,0.72,0,1) both; }
  .screen.active { display: block; }
  @keyframes fadeSlideUp {
    from { opacity: 0; transform: translateY(18px) scale(0.98); }
    to   { opacity: 1; transform: translateY(0) scale(1); }
  }

  /* ── PROFILE HEADER ── */
  .profile-header {
    margin: 0 16px 20px;
    background: var(--card);
    backdrop-filter: blur(30px) saturate(1.8);
    -webkit-backdrop-filter: blur(30px) saturate(1.8);
    border-radius: var(--radius-xl);
    border: 1px solid var(--glass-border);
    box-shadow: var(--shadow);
    padding: 32px 24px 24px;
    text-align: center;
    position: relative;
    overflow: hidden;
  }
  .profile-header::before {
    content: '';
    position: absolute; top: 0; left: 0; right: 0; height: 3px;
    background: linear-gradient(90deg, #007aff, #5856d6, #ff2d55, #ff9500, #34c759);
    border-radius: var(--radius-xl) var(--radius-xl) 0 0;
  }

  .avatar-ring {
    width: 90px; height: 90px;
    margin: 0 auto 16px;
    border-radius: 50%;
    padding: 3px;
    background: linear-gradient(135deg, #007aff 0%, #5856d6 50%, #ff2d55 100%);
    box-shadow: 0 4px 20px rgba(88,86,214,0.35);
  }
  .avatar-inner {
    width: 100%; height: 100%;
    border-radius: 50%;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    display: flex; align-items: center; justify-content: center;
    font-size: 32px; font-weight: 800; color: #fff;
    letter-spacing: -1px;
    border: 3px solid white;
  }

  .profile-name {
    font-size: 24px; font-weight: 800; color: var(--text);
    letter-spacing: -0.5px; margin-bottom: 4px;
  }
  .profile-role {
    font-size: 14px; color: var(--text3); font-weight: 500; margin-bottom: 16px;
  }

  .profile-pills {
    display: flex; flex-wrap: wrap; gap: 8px; justify-content: center; margin-bottom: 20px;
  }
  .pill {
    padding: 5px 13px; border-radius: 100px; font-size: 12px; font-weight: 600;
    letter-spacing: 0.02em;
  }
  .pill-blue  { background: rgba(0,122,255,0.12); color: #0055d5; }
  .pill-purple{ background: rgba(88,86,214,0.12); color: #3a38a0; }
  .pill-green { background: rgba(52,199,89,0.12); color: #1a7a36; }

  .profile-stats {
    display: grid; grid-template-columns: 1fr 1fr 1fr;
    gap: 1px; background: rgba(0,0,0,0.07); border-radius: 14px; overflow: hidden;
    margin-top: 4px;
  }
  .stat-cell {
    background: rgba(255,255,255,0.7); backdrop-filter: blur(10px);
    padding: 14px 8px; text-align: center;
  }
  .stat-num { font-size: 22px; font-weight: 800; color: var(--text); letter-spacing: -0.5px; }
  .stat-label { font-size: 11px; color: var(--text3); font-weight: 500; margin-top: 2px; }

  /* ── CARD ── */
  .card {
    margin: 0 16px 14px;
    background: var(--card);
    backdrop-filter: blur(30px) saturate(1.8);
    -webkit-backdrop-filter: blur(30px) saturate(1.8);
    border-radius: var(--radius-lg);
    border: 1px solid var(--glass-border);
    box-shadow: var(--shadow-sm);
    overflow: hidden;
  }
  .card-header {
    display: flex; align-items: center; gap: 10px;
    padding: 16px 18px 12px;
    border-bottom: 0.5px solid rgba(0,0,0,0.07);
  }
  .card-icon {
    width: 32px; height: 32px; border-radius: 8px;
    display: flex; align-items: center; justify-content: center;
    font-size: 16px; flex-shrink: 0;
  }
  .icon-blue   { background: linear-gradient(135deg,#007aff,#0055d5); }
  .icon-purple { background: linear-gradient(135deg,#5856d6,#3634a3); }
  .icon-green  { background: linear-gradient(135deg,#34c759,#248a3d); }
  .icon-orange { background: linear-gradient(135deg,#ff9500,#c93400); }
  .icon-pink   { background: linear-gradient(135deg,#ff2d55,#c3003a); }
  .icon-teal   { background: linear-gradient(135deg,#30b0c7,#0071a4); }
  .card-icon svg { width: 17px; height: 17px; fill: white; }

  .card-title { font-size: 15px; font-weight: 700; color: var(--text); }
  .card-subtitle { font-size: 12px; color: var(--text3); font-weight: 500; }

  /* ── SKILL CHIPS ── */
  .chip-grid { display: flex; flex-wrap: wrap; gap: 8px; padding: 14px 18px 18px; }
  .chip {
    padding: 6px 14px; border-radius: 100px; font-size: 13px; font-weight: 600;
    background: rgba(0,0,0,0.05); color: var(--text2);
    transition: transform 0.15s, background 0.15s;
    cursor: default; user-select: none;
  }
  .chip:hover { transform: scale(1.06); background: rgba(0,122,255,0.1); color: #0055d5; }
  .chip.active-chip { background: rgba(0,122,255,0.13); color: #0055d5; }

  /* ── LIST ROWS ── */
  .list-row {
    display: flex; align-items: center; gap: 14px;
    padding: 13px 18px;
    border-bottom: 0.5px solid rgba(0,0,0,0.06);
    transition: background 0.15s;
    cursor: default;
  }
  .list-row:last-child { border-bottom: none; }
  .list-row:hover { background: rgba(0,0,0,0.02); }
  .list-row-icon {
    width: 36px; height: 36px; border-radius: 9px; flex-shrink: 0;
    display: flex; align-items: center; justify-content: center; font-size: 18px;
  }
  .list-row-text { flex: 1; min-width: 0; }
  .list-row-title { font-size: 14px; font-weight: 600; color: var(--text); }
  .list-row-desc { font-size: 12px; color: var(--text3); margin-top: 1px; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
  .list-row-badge {
    font-size: 11px; font-weight: 700; padding: 3px 9px;
    border-radius: 100px; flex-shrink: 0;
  }
  .badge-green  { background: rgba(52,199,89,0.15); color: #1a7a36; }
  .badge-blue   { background: rgba(0,122,255,0.12); color: #0055d5; }
  .badge-orange { background: rgba(255,149,0,0.15); color: #a04300; }
  .badge-purple { background: rgba(88,86,214,0.12); color: #3a38a0; }

  /* ── CHEVRON ── */
  .chevron { color: var(--text3); font-size: 14px; opacity: 0.5; }

  /* ── ABOUT TAB ── */
  .about-block { padding: 16px 18px; }
  .about-text {
    font-size: 14px; line-height: 1.75; color: var(--text2);
    font-weight: 500;
  }
  .about-highlight { color: var(--accent); font-weight: 700; }

  /* ── TIMELINE ── */
  .timeline { padding: 12px 18px 18px; }
  .timeline-item { display: flex; gap: 14px; margin-bottom: 18px; }
  .timeline-item:last-child { margin-bottom: 0; }
  .timeline-dot-col { display: flex; flex-direction: column; align-items: center; }
  .timeline-dot {
    width: 12px; height: 12px; border-radius: 50%; flex-shrink: 0; margin-top: 3px;
  }
  .timeline-line { width: 1.5px; flex: 1; background: rgba(0,0,0,0.1); margin-top: 4px; }
  .timeline-content { flex: 1; padding-bottom: 4px; }
  .timeline-title { font-size: 14px; font-weight: 700; color: var(--text); }
  .timeline-date { font-size: 11px; color: var(--text3); font-weight: 500; margin-bottom: 4px; }
  .timeline-desc { font-size: 13px; color: var(--text2); line-height: 1.5; }

  /* ── SKILL BARS ── */
  .skill-bar-wrap { padding: 6px 18px 18px; }
  .skill-bar-row { margin-bottom: 14px; }
  .skill-bar-top { display: flex; justify-content: space-between; margin-bottom: 6px; }
  .skill-bar-name { font-size: 13px; font-weight: 600; color: var(--text); }
  .skill-bar-pct  { font-size: 12px; font-weight: 600; color: var(--text3); }
  .skill-bar-track {
    height: 6px; border-radius: 100px; background: rgba(0,0,0,0.07); overflow: hidden;
  }
  .skill-bar-fill {
    height: 100%; border-radius: 100px;
    transform-origin: left;
    animation: barGrow 1s cubic-bezier(0.32,0.72,0,1) both;
  }
  @keyframes barGrow {
    from { transform: scaleX(0); }
    to   { transform: scaleX(1); }
  }

  /* ── CONTACT ── */
  .contact-btn {
    display: flex; align-items: center; gap: 14px;
    margin: 0 16px 12px;
    background: var(--card);
    backdrop-filter: blur(30px);
    -webkit-backdrop-filter: blur(30px);
    border-radius: var(--radius-lg);
    border: 1px solid var(--glass-border);
    box-shadow: var(--shadow-sm);
    padding: 16px 18px;
    text-decoration: none; color: inherit;
    transition: transform 0.18s cubic-bezier(0.32,0.72,0,1), box-shadow 0.18s;
    cursor: pointer;
  }
  .contact-btn:hover { transform: scale(1.02); box-shadow: var(--shadow); }
  .contact-btn:active { transform: scale(0.97); }
  .contact-btn-icon {
    width: 44px; height: 44px; border-radius: 12px;
    display: flex; align-items: center; justify-content: center; font-size: 22px; flex-shrink: 0;
  }
  .contact-btn-text .contact-btn-title { font-size: 15px; font-weight: 700; color: var(--text); }
  .contact-btn-text .contact-btn-sub { font-size: 12px; color: var(--text3); font-weight: 500; }
  .contact-btn-arrow { margin-left: auto; color: var(--text3); font-size: 18px; }

  /* ── REPO CARDS ── */
  .repo-card {
    margin: 0 16px 12px;
    background: var(--card);
    backdrop-filter: blur(30px);
    -webkit-backdrop-filter: blur(30px);
    border-radius: var(--radius-lg);
    border: 1px solid var(--glass-border);
    box-shadow: var(--shadow-sm);
    padding: 18px;
    transition: transform 0.18s, box-shadow 0.18s;
    cursor: pointer;
  }
  .repo-card:hover { transform: translateY(-2px); box-shadow: var(--shadow); }
  .repo-card:active { transform: scale(0.98); }
  .repo-name { font-size: 15px; font-weight: 800; color: var(--accent); margin-bottom: 5px; }
  .repo-desc { font-size: 13px; color: var(--text2); line-height: 1.5; margin-bottom: 12px; }
  .repo-meta { display: flex; gap: 14px; align-items: center; }
  .repo-lang { display: flex; align-items: center; gap: 5px; font-size: 12px; color: var(--text3); font-weight: 500; }
  .lang-dot { width: 10px; height: 10px; border-radius: 50%; }
  .repo-stars { font-size: 12px; color: var(--text3); font-weight: 500; }
  .repo-tag {
    margin-left: auto; font-size: 11px; font-weight: 700;
    padding: 3px 9px; border-radius: 100px;
  }

  /* ── TAB BAR ── */
  .tabbar {
    position: fixed; bottom: 0; left: 50%; transform: translateX(-50%);
    width: 393px; max-width: 100%;
    background: rgba(255,255,255,0.75);
    backdrop-filter: blur(40px) saturate(2);
    -webkit-backdrop-filter: blur(40px) saturate(2);
    border-top: 0.5px solid rgba(0,0,0,0.1);
    display: flex; justify-content: space-around;
    padding: 10px 0 28px;
    z-index: 100;
    box-shadow: 0 -4px 24px rgba(0,0,0,0.08);
  }
  .tab-btn {
    display: flex; flex-direction: column; align-items: center; gap: 4px;
    background: none; border: none; cursor: pointer; padding: 4px 18px;
    transition: transform 0.15s;
    -webkit-tap-highlight-color: transparent;
  }
  .tab-btn:active { transform: scale(0.88); }
  .tab-icon {
    width: 26px; height: 26px; border-radius: 7px;
    display: flex; align-items: center; justify-content: center;
    font-size: 18px; transition: all 0.2s cubic-bezier(0.32,0.72,0,1);
  }
  .tab-label { font-size: 10px; font-weight: 600; color: var(--text3); transition: color 0.2s; letter-spacing: 0.01em; }
  .tab-btn.active .tab-icon { transform: scale(1.1); }
  .tab-btn.active .tab-label { color: var(--accent); }

  /* ── SECTION LABEL ── */
  .section-label {
    font-size: 12px; font-weight: 700; color: var(--text3);
    text-transform: uppercase; letter-spacing: 0.08em;
    padding: 0 32px 8px;
  }

  /* ── AI BADGE ── */
  .ai-badge {
    display: inline-flex; align-items: center; gap: 6px;
    padding: 6px 14px; border-radius: 100px;
    background: linear-gradient(135deg, rgba(88,86,214,0.13), rgba(0,122,255,0.10));
    border: 1px solid rgba(88,86,214,0.2);
    font-size: 12px; font-weight: 700; color: #3a38a0;
    margin: 0 18px 14px;
  }
  .ai-pulse {
    width: 8px; height: 8px; border-radius: 50%; background: #5856d6;
    animation: pulse 2s ease-in-out infinite;
  }
  @keyframes pulse {
    0%,100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.5; transform: scale(0.8); }
  }

  /* ── PAGE TITLE ── */
  .page-title {
    font-size: 28px; font-weight: 800; color: var(--text);
    padding: 8px 20px 18px; letter-spacing: -0.5px;
  }

  /* scrollbar */
  ::-webkit-scrollbar { display: none; }
</style>
</head>
<body>

<div class="phone-wrap">
<div class="phone">

  <!-- Status Bar -->
  <div class="statusbar">
    <span id="clock">9:41</span>
    <div class="statusbar-right">
      <span style="font-size:12px;">●●●●</span>
      <span style="font-size:12px;">WiFi</span>
      <span style="font-size:12px;">🔋</span>
    </div>
  </div>

  <!-- ══════════ HOME SCREEN ══════════ -->
  <div class="screen active" id="screen-home">

    <div class="profile-header">
      <div class="avatar-ring">
        <div class="avatar-inner">AA</div>
      </div>
      <div class="profile-name">Awais Aftab</div>
      <div class="profile-role">Full Stack Developer · He/Him · 🇵🇰</div>
      <div class="profile-pills">
        <span class="pill pill-blue">React</span>
        <span class="pill pill-purple">Node.js</span>
        <span class="pill pill-green">Gen AI</span>
        <span class="pill pill-blue">Next.js</span>
        <span class="pill pill-purple">Python</span>
      </div>
      <div class="profile-stats">
        <div class="stat-cell">
          <div class="stat-num">35</div>
          <div class="stat-label">Repos</div>
        </div>
        <div class="stat-cell">
          <div class="stat-num">2+</div>
          <div class="stat-label">Years</div>
        </div>
        <div class="stat-cell">
          <div class="stat-num">∞</div>
          <div class="stat-label">Ideas</div>
        </div>
      </div>
    </div>

    <div class="ai-badge"><div class="ai-pulse"></div> Currently learning Generative AI</div>

    <div class="section-label">Quick look</div>

    <div class="card">
      <div class="list-row">
        <div class="list-row-icon" style="background:rgba(0,122,255,0.1); font-size:20px;">💼</div>
        <div class="list-row-text">
          <div class="list-row-title">Full Stack Developer</div>
          <div class="list-row-desc">Building web apps end-to-end</div>
        </div>
        <span class="list-row-badge badge-green">Open to work</span>
      </div>
      <div class="list-row">
        <div class="list-row-icon" style="background:rgba(88,86,214,0.1); font-size:20px;">🤖</div>
        <div class="list-row-text">
          <div class="list-row-title">Generative AI</div>
          <div class="list-row-desc">LLMs, prompts & AI-powered apps</div>
        </div>
        <span class="list-row-badge badge-purple">Learning</span>
      </div>
      <div class="list-row">
        <div class="list-row-icon" style="background:rgba(52,199,89,0.1); font-size:20px;">🌐</div>
        <div class="list-row-text">
          <div class="list-row-title">Open Source</div>
          <div class="list-row-desc">Collaborate · Contribute · Ship</div>
        </div>
        <span class="list-row-badge badge-blue">Active</span>
      </div>
      <div class="list-row">
        <div class="list-row-icon" style="background:rgba(255,149,0,0.1); font-size:20px;">📍</div>
        <div class="list-row-text">
          <div class="list-row-title">Pakistan</div>
          <div class="list-row-desc">aacreator57@gmail.com</div>
        </div>
        <span class="chevron">›</span>
      </div>
    </div>

  </div>

  <!-- ══════════ SKILLS SCREEN ══════════ -->
  <div class="screen" id="screen-skills">
    <div class="page-title">Skills</div>

    <div class="card">
      <div class="card-header">
        <div class="card-icon icon-blue">
          <svg viewBox="0 0 24 24"><path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/></svg>
        </div>
        <div>
          <div class="card-title">Proficiency</div>
          <div class="card-subtitle">How deep the roots go</div>
        </div>
      </div>
      <div class="skill-bar-wrap">
        <div class="skill-bar-row">
          <div class="skill-bar-top"><span class="skill-bar-name">React / Next.js</span><span class="skill-bar-pct">88%</span></div>
          <div class="skill-bar-track"><div class="skill-bar-fill" style="width:88%;background:linear-gradient(90deg,#007aff,#5ac8fa);animation-delay:0.1s"></div></div>
        </div>
        <div class="skill-bar-row">
          <div class="skill-bar-top"><span class="skill-bar-name">Node.js / Express</span><span class="skill-bar-pct">82%</span></div>
          <div class="skill-bar-track"><div class="skill-bar-fill" style="width:82%;background:linear-gradient(90deg,#34c759,#30b0c7);animation-delay:0.2s"></div></div>
        </div>
        <div class="skill-bar-row">
          <div class="skill-bar-top"><span class="skill-bar-name">TypeScript</span><span class="skill-bar-pct">78%</span></div>
          <div class="skill-bar-track"><div class="skill-bar-fill" style="width:78%;background:linear-gradient(90deg,#5856d6,#af52de);animation-delay:0.3s"></div></div>
        </div>
        <div class="skill-bar-row">
          <div class="skill-bar-top"><span class="skill-bar-name">Python</span><span class="skill-bar-pct">72%</span></div>
          <div class="skill-bar-track"><div class="skill-bar-fill" style="width:72%;background:linear-gradient(90deg,#ff9500,#ff6b00);animation-delay:0.4s"></div></div>
        </div>
        <div class="skill-bar-row">
          <div class="skill-bar-top"><span class="skill-bar-name">MongoDB / PostgreSQL</span><span class="skill-bar-pct">75%</span></div>
          <div class="skill-bar-track"><div class="skill-bar-fill" style="width:75%;background:linear-gradient(90deg,#ff2d55,#ff6b81);animation-delay:0.5s"></div></div>
        </div>
        <div class="skill-bar-row">
          <div class="skill-bar-top"><span class="skill-bar-name">Generative AI / LLMs</span><span class="skill-bar-pct">60%</span></div>
          <div class="skill-bar-track"><div class="skill-bar-fill" style="width:60%;background:linear-gradient(90deg,#af52de,#007aff);animation-delay:0.6s"></div></div>
        </div>
      </div>
    </div>

    <div class="section-label">All technologies</div>

    <div class="card">
      <div class="card-header">
        <div class="card-icon icon-purple"><svg viewBox="0 0 24 24"><rect x="2" y="3" width="20" height="14" rx="2"/><path d="M8 21h8M12 17v4"/></svg></div>
        <div><div class="card-title">Frontend</div></div>
      </div>
      <div class="chip-grid">
        <span class="chip">React</span><span class="chip">Next.js</span><span class="chip">TypeScript</span>
        <span class="chip">Tailwind CSS</span><span class="chip">HTML5</span><span class="chip">CSS3</span>
        <span class="chip">JavaScript</span><span class="chip">Framer Motion</span>
      </div>
    </div>

    <div class="card">
      <div class="card-header">
        <div class="card-icon icon-green"><svg viewBox="0 0 24 24"><path d="M5 12H19M12 5l7 7-7 7"/></svg></div>
        <div><div class="card-title">Backend & DB</div></div>
      </div>
      <div class="chip-grid">
        <span class="chip">Node.js</span><span class="chip">Express.js</span><span class="chip">Python</span>
        <span class="chip">MongoDB</span><span class="chip">PostgreSQL</span><span class="chip">Firebase</span>
        <span class="chip">REST APIs</span>
      </div>
    </div>

    <div class="card">
      <div class="card-header">
        <div class="card-icon icon-pink"><svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="3"/><path d="M12 2v4M12 18v4M4.93 4.93l2.83 2.83M16.24 16.24l2.83 2.83M2 12h4M18 12h4M4.93 19.07l2.83-2.83M16.24 7.76l2.83-2.83"/></svg></div>
        <div><div class="card-title">AI & Tools</div></div>
      </div>
      <div class="chip-grid">
        <span class="chip">OpenAI API</span><span class="chip">LangChain</span><span class="chip">Prompt Eng.</span>
        <span class="chip">Git</span><span class="chip">GitHub</span><span class="chip">VS Code</span>
        <span class="chip">Postman</span><span class="chip">Docker</span>
      </div>
    </div>
  </div>

  <!-- ══════════ PROJECTS SCREEN ══════════ -->
  <div class="screen" id="screen-projects">
    <div class="page-title">Projects</div>

    <div class="section-label">Repositories</div>

    <div class="repo-card" onclick="window.open('https://github.com/MRAWAISAFTAB','_blank')">
      <div class="repo-name">⚡ MRAWAISAFTAB</div>
      <div class="repo-desc">My GitHub profile README — config files and profile customisation for @MRAWAISAFTAB</div>
      <div class="repo-meta">
        <div class="repo-lang"><div class="lang-dot" style="background:#e34c26"></div> HTML</div>
        <div class="repo-stars">★ 1</div>
        <span class="repo-tag badge-blue">Public</span>
      </div>
    </div>

    <div class="repo-card" onclick="window.open('https://github.com/MRAWAISAFTAB/weather-app-oss','_blank')">
      <div class="repo-name">🌦 weather-app-oss</div>
      <div class="repo-desc">Open-source Weather App with OSS compliance docs, templates, and guidance. Forked &amp; enhanced.</div>
      <div class="repo-meta">
        <div class="repo-lang"><div class="lang-dot" style="background:#f1e05a"></div> JavaScript</div>
        <div class="repo-stars">★ 1</div>
        <span class="repo-tag badge-green">OSS</span>
      </div>
    </div>

    <div class="repo-card">
      <div class="repo-name">🤖 AI Chat Interface</div>
      <div class="repo-desc">Full-stack AI-powered chat app using OpenAI API, React and Node.js backend with streaming responses.</div>
      <div class="repo-meta">
        <div class="repo-lang"><div class="lang-dot" style="background:#3178c6"></div> TypeScript</div>
        <div class="repo-stars">★ —</div>
        <span class="repo-tag badge-purple">In Progress</span>
      </div>
    </div>

    <div class="repo-card">
      <div class="repo-name">📊 Dev Portfolio v2</div>
      <div class="repo-desc">Next.js portfolio with smooth animations, dark mode, and dynamic project showcase powered by GitHub API.</div>
      <div class="repo-meta">
        <div class="repo-lang"><div class="lang-dot" style="background:#3178c6"></div> TypeScript</div>
        <div class="repo-stars">★ —</div>
        <span class="repo-tag badge-orange">Coming Soon</span>
      </div>
    </div>

    <div class="section-label" style="margin-top:6px;">Currently building</div>
    <div class="card">
      <div class="list-row">
        <div class="list-row-icon" style="background:rgba(88,86,214,0.12);font-size:20px;">🧠</div>
        <div class="list-row-text">
          <div class="list-row-title">LLM-powered full stack app</div>
          <div class="list-row-desc">React + FastAPI + OpenAI streaming</div>
        </div>
        <span class="list-row-badge badge-purple">Active</span>
      </div>
      <div class="list-row">
        <div class="list-row-icon" style="background:rgba(52,199,89,0.12);font-size:20px;">🌐</div>
        <div class="list-row-text">
          <div class="list-row-title">SaaS boilerplate</div>
          <div class="list-row-desc">Next.js · Stripe · Supabase · Auth</div>
        </div>
        <span class="list-row-badge badge-green">Building</span>
      </div>
    </div>
  </div>

  <!-- ══════════ ABOUT SCREEN ══════════ -->
  <div class="screen" id="screen-about">
    <div class="page-title">About</div>

    <div class="card">
      <div class="card-header">
        <div class="card-icon icon-orange"><svg viewBox="0 0 24 24"><path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"/><circle cx="12" cy="7" r="4"/></svg></div>
        <div><div class="card-title">Who I am</div></div>
      </div>
      <div class="about-block">
        <p class="about-text">
          Hey! I'm <span class="about-highlight">Awais</span> — a Full Stack Developer from <span class="about-highlight">Pakistan 🇵🇰</span> who loves turning ideas into real, working products.
          <br><br>
          I'm currently going deep on <span class="about-highlight">Generative AI</span> — learning how LLMs work under the hood, building AI-integrated applications, and exploring prompt engineering as a craft.
          <br><br>
          When I'm not coding, I'm thinking about what to build next. I believe the best developers are also <span class="about-highlight">great product thinkers</span> — and I'm working hard to be both.
        </p>
      </div>
    </div>

    <div class="section-label">Journey</div>

    <div class="card">
      <div class="timeline">
        <div class="timeline-item">
          <div class="timeline-dot-col">
            <div class="timeline-dot" style="background:#007aff"></div>
            <div class="timeline-line"></div>
          </div>
          <div class="timeline-content">
            <div class="timeline-date">2025 — Now</div>
            <div class="timeline-title">Generative AI Explorer</div>
            <div class="timeline-desc">Diving into LLMs, prompt engineering, LangChain, and building AI-powered apps from scratch.</div>
          </div>
        </div>
        <div class="timeline-item">
          <div class="timeline-dot-col">
            <div class="timeline-dot" style="background:#5856d6"></div>
            <div class="timeline-line"></div>
          </div>
          <div class="timeline-content">
            <div class="timeline-date">2023 — 2025</div>
            <div class="timeline-title">Full Stack Developer</div>
            <div class="timeline-desc">Built production web apps with React, Next.js, Node.js and MongoDB. Shipped real products.</div>
          </div>
        </div>
        <div class="timeline-item">
          <div class="timeline-dot-col">
            <div class="timeline-dot" style="background:#34c759"></div>
          </div>
          <div class="timeline-content">
            <div class="timeline-date">2022 — 2023</div>
            <div class="timeline-title">Started Coding</div>
            <div class="timeline-desc">Fell in love with the web. HTML → CSS → JS → React → never looked back.</div>
          </div>
        </div>
      </div>
    </div>

    <div class="section-label">Contact</div>

    <a class="contact-btn" href="mailto:aacreator57@gmail.com">
      <div class="contact-btn-icon" style="background:linear-gradient(135deg,#007aff,#0055d5);">📧</div>
      <div class="contact-btn-text">
        <div class="contact-btn-title">Email me</div>
        <div class="contact-btn-sub">aacreator57@gmail.com</div>
      </div>
      <div class="contact-btn-arrow">›</div>
    </a>

    <a class="contact-btn" href="https://github.com/MRAWAISAFTAB" target="_blank">
      <div class="contact-btn-icon" style="background:linear-gradient(135deg,#1c1c1e,#48484a);">🐙</div>
      <div class="contact-btn-text">
        <div class="contact-btn-title">GitHub</div>
        <div class="contact-btn-sub">github.com/MRAWAISAFTAB</div>
      </div>
      <div class="contact-btn-arrow">›</div>
    </a>

    <a class="contact-btn" href="https://linkedin.com/in/MRAWAISAFTAB" target="_blank">
      <div class="contact-btn-icon" style="background:linear-gradient(135deg,#0077b5,#005885);">💼</div>
      <div class="contact-btn-text">
        <div class="contact-btn-title">LinkedIn</div>
        <div class="contact-btn-sub">linkedin.com/in/MRAWAISAFTAB</div>
      </div>
      <div class="contact-btn-arrow">›</div>
    </a>

    <div style="height:10px"></div>
  </div>

  <!-- ══════════ TAB BAR ══════════ -->
  <div class="tabbar">
    <button class="tab-btn active" onclick="switchTab('home',this)">
      <div class="tab-icon">🏠</div>
      <span class="tab-label">Profile</span>
    </button>
    <button class="tab-btn" onclick="switchTab('skills',this)">
      <div class="tab-icon">⚡</div>
      <span class="tab-label">Skills</span>
    </button>
    <button class="tab-btn" onclick="switchTab('projects',this)">
      <div class="tab-icon">🗂️</div>
      <span class="tab-label">Projects</span>
    </button>
    <button class="tab-btn" onclick="switchTab('about',this)">
      <div class="tab-icon">👤</div>
      <span class="tab-label">About</span>
    </button>
  </div>

</div>
</div>

<script>
  function switchTab(id, btn) {
    document.querySelectorAll('.screen').forEach(s => s.classList.remove('active'));
    document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
    document.getElementById('screen-' + id).classList.add('active');
    btn.classList.add('active');
    window.scrollTo({top: 0, behavior: 'smooth'});
  }

  function updateClock() {
    const now = new Date();
    const h = now.getHours().toString().padStart(2,'0');
    const m = now.getMinutes().toString().padStart(2,'0');
    document.getElementById('clock').textContent = h + ':' + m;
  }
  updateClock();
  setInterval(updateClock, 1000);
</script>
</body>
</html>
