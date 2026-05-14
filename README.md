
<style>
@import url('https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=DM+Sans:wght@300;400;500;600&display=swap');

* { box-sizing: border-box; margin: 0; padding: 0; }

.portfolio {
  font-family: 'DM Sans', sans-serif;
  background: #0a0e1a;
  color: #e2e8f0;
  min-height: 100vh;
  padding: 0;
  position: relative;
  overflow: hidden;
}

.grid-bg {
  position: absolute; inset: 0;
  background-image:
    linear-gradient(rgba(57,255,20,0.04) 1px, transparent 1px),
    linear-gradient(90deg, rgba(57,255,20,0.04) 1px, transparent 1px);
  background-size: 32px 32px;
  pointer-events: none;
}

.scanline {
  position: absolute; inset: 0;
  background: repeating-linear-gradient(0deg, transparent, transparent 2px, rgba(0,0,0,0.03) 2px, rgba(0,0,0,0.03) 4px);
  pointer-events: none;
}

.content { position: relative; z-index: 1; padding: 36px 32px 40px; max-width: 680px; }

.header { display: flex; align-items: flex-start; gap: 20px; margin-bottom: 28px; }

.avatar-wrap { position: relative; flex-shrink: 0; }
.avatar {
  width: 72px; height: 72px; border-radius: 50%;
  background: linear-gradient(135deg, #39ff14 0%, #00d4ff 100%);
  display: flex; align-items: center; justify-content: center;
  font-family: 'Space Mono', monospace;
  font-size: 22px; font-weight: 700;
  color: #0a0e1a;
  box-shadow: 0 0 20px rgba(57,255,20,0.4), 0 0 40px rgba(57,255,20,0.15);
}
.avatar-ring {
  position: absolute; inset: -4px; border-radius: 50%;
  border: 1px solid rgba(57,255,20,0.5);
  animation: pulse-ring 3s ease-in-out infinite;
}
@keyframes pulse-ring {
  0%, 100% { transform: scale(1); opacity: 0.5; }
  50% { transform: scale(1.08); opacity: 1; }
}

.status-dot {
  position: absolute; bottom: 3px; right: 3px;
  width: 14px; height: 14px; border-radius: 50%;
  background: #39ff14;
  border: 2px solid #0a0e1a;
  box-shadow: 0 0 8px rgba(57,255,20,0.8);
}

.header-info { flex: 1; }
.name {
  font-family: 'Space Mono', monospace;
  font-size: 22px; font-weight: 700;
  color: #fff; letter-spacing: -0.5px;
  margin-bottom: 4px;
}
.name span { color: #39ff14; }

.title-tag {
  display: inline-block;
  background: rgba(57,255,20,0.1);
  border: 1px solid rgba(57,255,20,0.3);
  color: #39ff14;
  font-family: 'Space Mono', monospace;
  font-size: 11px;
  padding: 3px 10px;
  border-radius: 4px;
  margin-bottom: 8px;
  letter-spacing: 0.5px;
}

.meta { display: flex; gap: 16px; flex-wrap: wrap; }
.meta-item {
  font-size: 12px; color: #64748b;
  display: flex; align-items: center; gap: 5px;
}
.meta-item i { font-size: 13px; color: #39ff14; }

.section { margin-bottom: 24px; }
.sec-header {
  display: flex; align-items: center; gap: 10px;
  margin-bottom: 14px;
}
.sec-label {
  font-family: 'Space Mono', monospace;
  font-size: 11px; font-weight: 700;
  color: #39ff14; letter-spacing: 1.5px;
  text-transform: uppercase;
}
.sec-line { flex: 1; height: 1px; background: linear-gradient(90deg, rgba(57,255,20,0.3), transparent); }

.skills-grid { display: flex; flex-wrap: wrap; gap: 8px; }
.skill-chip {
  background: rgba(255,255,255,0.04);
  border: 1px solid rgba(255,255,255,0.1);
  color: #94a3b8;
  font-family: 'Space Mono', monospace;
  font-size: 11px;
  padding: 5px 12px;
  border-radius: 4px;
  transition: all 0.2s;
  cursor: default;
}
.skill-chip:hover {
  background: rgba(57,255,20,0.08);
  border-color: rgba(57,255,20,0.4);
  color: #39ff14;
}
.skill-chip.highlight {
  background: rgba(57,255,20,0.1);
  border-color: rgba(57,255,20,0.3);
  color: #39ff14;
}

.projects-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
.project-card {
  background: rgba(255,255,255,0.03);
  border: 1px solid rgba(255,255,255,0.08);
  border-radius: 8px;
  padding: 14px;
  transition: all 0.2s;
  cursor: default;
  position: relative; overflow: hidden;
}
.project-card::before {
  content: '';
  position: absolute; top: 0; left: 0; right: 0; height: 2px;
  opacity: 0; transition: opacity 0.2s;
}
.project-card.green::before { background: linear-gradient(90deg, #39ff14, transparent); }
.project-card.blue::before { background: linear-gradient(90deg, #00d4ff, transparent); }
.project-card.purple::before { background: linear-gradient(90deg, #a78bfa, transparent); }
.project-card.amber::before { background: linear-gradient(90deg, #f59e0b, transparent); }
.project-card:hover { border-color: rgba(57,255,20,0.2); transform: translateY(-1px); }
.project-card:hover::before { opacity: 1; }

.proj-icon {
  font-size: 18px; margin-bottom: 8px;
  display: block;
}
.proj-title {
  font-size: 13px; font-weight: 500;
  color: #e2e8f0; margin-bottom: 5px;
}
.proj-desc { font-size: 11px; color: #64748b; line-height: 1.5; margin-bottom: 10px; }
.proj-tags { display: flex; flex-wrap: wrap; gap: 4px; }
.proj-tag {
  font-family: 'Space Mono', monospace;
  font-size: 10px; color: #475569;
  background: rgba(255,255,255,0.05);
  border: 1px solid rgba(255,255,255,0.07);
  padding: 2px 7px; border-radius: 3px;
}

.sec-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
.info-card {
  background: rgba(255,255,255,0.03);
  border: 1px solid rgba(255,255,255,0.07);
  border-radius: 8px; padding: 14px;
}
.info-card-title { font-size: 13px; font-weight: 500; color: #e2e8f0; margin-bottom: 4px; }
.info-card-sub { font-size: 11px; color: #64748b; margin-bottom: 2px; }
.info-card-date { font-family: 'Space Mono', monospace; font-size: 10px; color: #39ff14; }

.cert-list { display: flex; flex-direction: column; gap: 7px; }
.cert-item {
  display: flex; align-items: center; gap: 10px;
  background: rgba(255,255,255,0.03);
  border: 1px solid rgba(255,255,255,0.07);
  border-radius: 6px; padding: 10px 14px;
}
.cert-item i { font-size: 15px; color: #39ff14; flex-shrink: 0; }
.cert-name { font-size: 12px; color: #94a3b8; }

.connect-row { display: flex; gap: 10px; flex-wrap: wrap; }
.connect-btn {
  display: flex; align-items: center; gap: 8px;
  background: rgba(255,255,255,0.04);
  border: 1px solid rgba(255,255,255,0.1);
  border-radius: 6px; padding: 9px 16px;
  text-decoration: none;
  color: #94a3b8;
  font-size: 12px; font-weight: 500;
  transition: all 0.2s;
  cursor: pointer;
}
.connect-btn i { font-size: 16px; }
.connect-btn:hover { background: rgba(57,255,20,0.08); border-color: rgba(57,255,20,0.3); color: #39ff14; }

.footer-bar {
  margin-top: 28px; padding-top: 20px;
  border-top: 1px solid rgba(255,255,255,0.06);
  display: flex; align-items: center; justify-content: space-between;
}
.footer-text { font-family: 'Space Mono', monospace; font-size: 11px; color: #334155; }
.footer-text span { color: #39ff14; }
.portfolio-link {
  font-family: 'Space Mono', monospace; font-size: 11px;
  color: #39ff14; text-decoration: none;
  border: 1px solid rgba(57,255,20,0.3);
  padding: 5px 12px; border-radius: 4px;
  transition: all 0.2s;
}
.portfolio-link:hover { background: rgba(57,255,20,0.1); }
</style>

<div class="portfolio">
  <div class="grid-bg"></div>
  <div class="scanline"></div>
  <div class="content">

    <div class="header">
      <div class="avatar-wrap">
        <div class="avatar">AO</div>
        <div class="avatar-ring"></div>
        <div class="status-dot"></div>
      </div>
      <div class="header-info">
        <div class="name">Ahmed <span>Omara</span></div>
        <div class="title-tag">Frontend &amp; Full-Stack Dev · Cybersecurity</div>
        <div class="meta">
          <span class="meta-item"><i class="ti ti-map-pin" aria-hidden="true"></i>Alexandria, Egypt</span>
          <span class="meta-item"><i class="ti ti-school" aria-hidden="true"></i>Alexandria National University</span>
          <span class="meta-item"><i class="ti ti-shield-check" aria-hidden="true"></i>BSc Cyber Security · 2022–2026</span>
        </div>
      </div>
    </div>

    <div class="section">
      <div class="sec-header">
        <span class="sec-label">Tech Stack</span>
        <div class="sec-line"></div>
      </div>
      <div class="skills-grid">
        <span class="skill-chip highlight">React</span>
        <span class="skill-chip highlight">TypeScript</span>
        <span class="skill-chip highlight">JavaScript</span>
        <span class="skill-chip">HTML · CSS</span>
        <span class="skill-chip">Tailwind CSS</span>
        <span class="skill-chip">Python</span>
        <span class="skill-chip">PHP</span>
        <span class="skill-chip">Flask</span>
        <span class="skill-chip">MySQL</span>
        <span class="skill-chip">Supabase</span>
        <span class="skill-chip">JWT · 2FA</span>
        <span class="skill-chip">Linux</span>
        <span class="skill-chip">Git · GitHub</span>
      </div>
    </div>

    <div class="section">
      <div class="sec-header">
        <span class="sec-label">Security Tools</span>
        <div class="sec-line"></div>
      </div>
      <div class="skills-grid">
        <span class="skill-chip">Wireshark</span>
        <span class="skill-chip">Nmap</span>
        <span class="skill-chip">Burp Suite</span>
        <span class="skill-chip">OWASP ZAP</span>
        <span class="skill-chip">Metasploit</span>
        <span class="skill-chip">Hydra</span>
        <span class="skill-chip">Bash</span>
      </div>
    </div>

    <div class="section">
      <div class="sec-header">
        <span class="sec-label">Featured Projects</span>
        <div class="sec-line"></div>
      </div>
      <div class="projects-grid">
        <div class="project-card green">
          <i class="ti ti-building-hospital proj-icon" aria-hidden="true" style="color:#39ff14"></i>
          <div class="proj-title">Hospital Management System</div>
          <div class="proj-desc">Full-stack platform with scheduling, auth &amp; doctor management</div>
          <div class="proj-tags">
            <span class="proj-tag">JavaScript</span>
            <span class="proj-tag">PHP</span>
            <span class="proj-tag">MySQL</span>
          </div>
        </div>
        <div class="project-card blue">
          <i class="ti ti-lock proj-icon" aria-hidden="true" style="color:#00d4ff"></i>
          <div class="proj-title">Secure Flask REST API</div>
          <div class="proj-desc">JWT auth, 2FA, RBAC &amp; MySQL on a hardened REST backend</div>
          <div class="proj-tags">
            <span class="proj-tag">Python</span>
            <span class="proj-tag">Flask</span>
            <span class="proj-tag">JWT</span>
          </div>
        </div>
        <div class="project-card purple">
          <i class="ti ti-books proj-icon" aria-hidden="true" style="color:#a78bfa"></i>
          <div class="proj-title">Educational Platform</div>
          <div class="proj-desc">Scalable LMS with real-time features &amp; auth via Supabase</div>
          <div class="proj-tags">
            <span class="proj-tag">TypeScript</span>
            <span class="proj-tag">Supabase</span>
            <span class="proj-tag">Full-Stack</span>
          </div>
        </div>
        <div class="project-card amber">
          <i class="ti ti-bug proj-icon" aria-hidden="true" style="color:#f59e0b"></i>
          <div class="proj-title">Vulnerability Scanner</div>
          <div class="proj-desc">Python-based security tool for vulnerability scanning &amp; analysis</div>
          <div class="proj-tags">
            <span class="proj-tag">Python</span>
            <span class="proj-tag">Cybersecurity</span>
          </div>
        </div>
      </div>
    </div>

    <div class="section">
      <div class="sec-header">
        <span class="sec-label">Certifications</span>
        <div class="sec-line"></div>
      </div>
      <div class="cert-list">
        <div class="cert-item">
          <i class="ti ti-certificate" aria-hidden="true"></i>
          <span class="cert-name">Cisco — Introduction to Cybersecurity</span>
        </div>
        <div class="cert-item">
          <i class="ti ti-certificate" aria-hidden="true"></i>
          <span class="cert-name">AWS Academy — Cloud Foundations</span>
        </div>
        <div class="cert-item">
          <i class="ti ti-certificate" aria-hidden="true"></i>
          <span class="cert-name">AWS Academy — Cloud Security Foundations</span>
        </div>
      </div>
    </div>

    <div class="section">
      <div class="sec-header">
        <span class="sec-label">Connect</span>
        <div class="sec-line"></div>
      </div>
      <div class="connect-row">
        <a class="connect-btn" href="https://github.com/AhmedOmara1">
          <i class="ti ti-brand-github" aria-hidden="true"></i>GitHub
        </a>
        <a class="connect-btn" href="https://linkedin.com/in/ahmed-omara-2805a8248">
          <i class="ti ti-brand-linkedin" aria-hidden="true"></i>LinkedIn
        </a>
        <a class="connect-btn" href="mailto:ahmedyasser2325@gmail.com">
          <i class="ti ti-mail" aria-hidden="true"></i>Email
        </a>
      </div>
    </div>

    <div class="footer-bar">
      <span class="footer-text">Building <span>secure</span>, scalable &amp; modern digital experiences.</span>
      <a class="portfolio-link" href="https://omara-dev.lovable.app/">omara-dev.lovable.app ↗</a>
    </div>

  </div>
</div>
