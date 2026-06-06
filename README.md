<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Shivam Pandey — iOS Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet"/>
<style>
*{margin:0;padding:0;box-sizing:border-box}
:root{
  --bg:#0A0A0B;--surface:#111114;--surface2:#18181C;--border:#222228;--border2:#2E2E38;
  --blue:#3B82F6;--blue2:#60A5FA;--green:#22C55E;--amber:#F59E0B;--red:#EF4444;--purple:#A855F7;
  --text:#F0F0F4;--text2:#9090A0;--text3:#505060;
  --display:'Bebas Neue',sans-serif;--body:'DM Sans',sans-serif;--mono:'JetBrains Mono',monospace;
}
html{scroll-behavior:smooth}
body{background:var(--bg);color:var(--text);font-family:var(--body);font-size:15px;line-height:1.6;min-height:100vh}
::selection{background:rgba(59,130,246,0.3)}

/* NAV */
nav{position:sticky;top:0;z-index:100;background:rgba(10,10,11,0.85);backdrop-filter:blur(16px);border-bottom:1px solid var(--border);padding:0 32px;display:flex;align-items:center;justify-content:space-between;height:52px}
.nav-name{font-family:var(--display);font-size:22px;letter-spacing:0.05em;color:var(--text)}
.nav-links{display:flex;gap:6px}
.nav-link{font-size:12px;font-family:var(--mono);color:var(--text3);padding:5px 12px;border-radius:6px;cursor:pointer;transition:all 0.2s;border:none;background:none;text-decoration:none}
.nav-link:hover,.nav-link.active{color:var(--blue2);background:rgba(59,130,246,0.08)}
.nav-dot{width:7px;height:7px;border-radius:50%;background:var(--green);box-shadow:0 0 8px var(--green);animation:pulse-dot 2s ease-in-out infinite}
@keyframes pulse-dot{0%,100%{opacity:1;transform:scale(1)}50%{opacity:0.5;transform:scale(0.8)}}

/* HERO */
.hero{padding:72px 32px 64px;border-bottom:1px solid var(--border);position:relative;overflow:hidden}
.hero-bg-grid{position:absolute;inset:0;background-image:linear-gradient(var(--border) 1px,transparent 1px),linear-gradient(90deg,var(--border) 1px,transparent 1px);background-size:48px 48px;opacity:0.35;pointer-events:none}
.hero-bg-glow{position:absolute;top:-120px;left:-80px;width:500px;height:400px;background:radial-gradient(ellipse,rgba(59,130,246,0.07) 0%,transparent 65%);pointer-events:none}
.hero-inner{position:relative;max-width:860px}
.hero-status{display:inline-flex;align-items:center;gap:8px;background:rgba(34,197,94,0.08);border:1px solid rgba(34,197,94,0.2);color:#4ADE80;font-size:11px;font-family:var(--mono);padding:5px 14px;border-radius:100px;margin-bottom:28px;letter-spacing:0.04em}
.hero-title{font-family:var(--display);font-size:clamp(64px,10vw,112px);line-height:0.9;letter-spacing:0.02em;margin-bottom:6px}
.hero-title .accent{color:var(--blue2)}
.hero-subtitle{font-size:16px;color:var(--text2);font-weight:300;margin-bottom:32px;letter-spacing:0.02em}
.hero-chips{display:flex;flex-wrap:wrap;gap:8px;margin-bottom:40px}
.hchip{font-size:12px;font-family:var(--mono);color:var(--text2);background:var(--surface);border:1px solid var(--border2);padding:5px 12px;border-radius:6px;transition:all 0.2s;cursor:default}
.hchip:hover{border-color:var(--blue);color:var(--blue2);background:rgba(59,130,246,0.06)}
.hero-stats{display:flex;gap:1px;background:var(--border)}
.hstat{background:var(--surface);padding:20px 28px;flex:1;min-width:0}
.hstat-val{font-family:var(--display);font-size:42px;letter-spacing:0.04em;line-height:1;color:var(--text)}
.hstat-val span{color:var(--blue2);font-size:28px}
.hstat-key{font-size:11px;font-family:var(--mono);color:var(--text3);text-transform:uppercase;letter-spacing:0.1em;margin-top:4px}

/* SECTIONS */
.section{padding:56px 32px 0;max-width:900px}
.section-head{display:flex;align-items:baseline;gap:16px;margin-bottom:28px}
.section-num{font-family:var(--mono);font-size:11px;color:var(--blue);letter-spacing:0.06em}
.section-title{font-family:var(--display);font-size:32px;letter-spacing:0.04em}
.section-line{flex:1;height:1px;background:var(--border);margin-left:8px}

/* ABOUT CARDS */
.about-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px}
.acard{background:var(--surface);border:1px solid var(--border);border-radius:12px;padding:20px;transition:border-color 0.2s,transform 0.2s;cursor:default}
.acard:hover{border-color:var(--border2);transform:translateY(-2px)}
.acard-icon-row{display:flex;align-items:center;gap:10px;margin-bottom:10px}
.acard-icon{width:34px;height:34px;border-radius:9px;display:flex;align-items:center;justify-content:center;font-size:15px}
.acard-label{font-size:12px;font-family:var(--mono);font-weight:500;letter-spacing:0.04em}
.acard-body{font-size:13px;color:var(--text2);line-height:1.6;font-weight:300}

/* TECH STACK */
.stack-wrapper{display:grid;grid-template-columns:1fr 1fr;gap:12px}
.stack-card{background:var(--surface);border:1px solid var(--border);border-radius:12px;padding:18px 20px}
.stack-card-head{font-size:10px;font-family:var(--mono);color:var(--text3);letter-spacing:0.12em;text-transform:uppercase;margin-bottom:12px;display:flex;align-items:center;gap:8px}
.stack-card-head::after{content:'';flex:1;height:1px;background:var(--border)}
.badge-row{display:flex;flex-wrap:wrap;gap:6px}
.badge{font-size:11px;font-family:var(--mono);padding:4px 10px;border-radius:6px;border:1px solid;cursor:default;transition:all 0.15s}
.badge:hover{transform:scale(1.04)}
.b-blue{background:rgba(59,130,246,0.1);border-color:rgba(59,130,246,0.25);color:#93C5FD}
.b-green{background:rgba(34,197,94,0.1);border-color:rgba(34,197,94,0.25);color:#86EFAC}
.b-amber{background:rgba(245,158,11,0.1);border-color:rgba(245,158,11,0.25);color:#FCD34D}
.b-purple{background:rgba(168,85,247,0.1);border-color:rgba(168,85,247,0.25);color:#C4B5FD}
.b-red{background:rgba(239,68,68,0.1);border-color:rgba(239,68,68,0.25);color:#FCA5A5}
.b-gray{background:rgba(80,80,96,0.2);border-color:rgba(80,80,96,0.35);color:#9090A0}

/* PROJECTS */
.proj-list{display:flex;flex-direction:column;gap:16px}
.pcard{background:var(--surface);border:1px solid var(--border);border-radius:14px;padding:0;overflow:hidden;transition:border-color 0.2s}
.pcard:hover{border-color:var(--border2)}
.pcard-bar{height:3px;width:100%}
.pcard-body{padding:22px 24px}
.pcard-header{display:flex;align-items:flex-start;justify-content:space-between;gap:12px;margin-bottom:10px}
.pcard-title{font-family:var(--display);font-size:22px;letter-spacing:0.03em;line-height:1.1}
.pcard-type{font-size:10px;font-family:var(--mono);padding:4px 10px;border-radius:5px;border:1px solid;white-space:nowrap;margin-top:4px}
.pcard-desc{font-size:13px;color:var(--text2);font-weight:300;line-height:1.65;margin-bottom:14px}
.pcard-bullets{margin-bottom:16px;display:flex;flex-direction:column;gap:5px}
.pbullet{font-size:12.5px;color:var(--text2);display:flex;align-items:flex-start;gap:10px;font-weight:300}
.pbullet-dot{width:4px;height:4px;border-radius:50%;background:var(--text3);flex-shrink:0;margin-top:7px}
.pcard-tags{display:flex;flex-wrap:wrap;gap:6px}
.pcard-metric-row{display:flex;gap:1px;background:var(--border);border-top:1px solid var(--border);margin:0 0 0}
.pmetric{background:var(--surface2);flex:1;padding:12px 16px;text-align:center}
.pmetric-val{font-family:var(--mono);font-size:14px;font-weight:500}
.pmetric-key{font-size:10px;color:var(--text3);text-transform:uppercase;letter-spacing:0.08em;margin-top:2px;font-family:var(--mono)}

/* EXPERTISE */
.exp-grid{display:grid;grid-template-columns:1fr 1fr;gap:10px}
.exp-item{background:var(--surface);border:1px solid var(--border);border-radius:10px;padding:14px 16px;display:flex;gap:12px;align-items:center;transition:border-color 0.2s}
.exp-item:hover{border-color:var(--border2)}
.exp-stripe{width:3px;height:100%;border-radius:2px;flex-shrink:0;min-height:28px}
.exp-label{font-size:13px;color:var(--text2);font-weight:300;line-height:1.4}

/* EXPLORING */
.ex-grid{display:grid;grid-template-columns:1fr 1fr;gap:10px}
.ex-card{background:var(--surface);border:1px solid var(--border);border-radius:12px;padding:16px 18px;display:flex;align-items:flex-start;gap:12px;transition:all 0.2s}
.ex-card:hover{border-color:var(--blue);background:rgba(59,130,246,0.03)}
.ex-n{font-family:var(--mono);font-size:11px;color:var(--blue);font-weight:500;flex-shrink:0;margin-top:2px}
.ex-title{font-size:14px;font-weight:500;margin-bottom:3px}
.ex-sub{font-size:11px;color:var(--text3);font-family:var(--mono)}

/* STATS */
.stats-row{display:grid;grid-template-columns:1fr 1fr;gap:12px}
.stat-card{background:var(--surface);border:1px solid var(--border);border-radius:12px;padding:20px;text-align:center}
.stat-card img{border-radius:8px;max-width:100%;display:block}

/* CONNECT */
.connect-grid{display:flex;flex-wrap:wrap;gap:10px}
.ccard{display:flex;align-items:center;gap:12px;background:var(--surface);border:1px solid var(--border);border-radius:12px;padding:14px 20px;text-decoration:none;transition:all 0.2s;flex:1;min-width:200px}
.ccard:hover{border-color:var(--border2);transform:translateY(-2px)}
.ccard-icon{width:36px;height:36px;border-radius:9px;display:flex;align-items:center;justify-content:center;font-size:18px;flex-shrink:0}
.ccard-label{font-size:13px;font-weight:500;margin-bottom:2px}
.ccard-val{font-size:11px;font-family:var(--mono);color:var(--text3)}

/* QUOTE */
.quote-section{padding:48px 32px 64px;max-width:900px}
.quote-box{background:var(--surface);border:1px solid var(--border);border-left:3px solid var(--blue);border-radius:0 12px 12px 0;padding:24px 28px;position:relative}
.quote-mark{font-family:var(--display);font-size:72px;line-height:0.5;color:var(--border2);position:absolute;top:20px;left:20px;pointer-events:none;user-select:none}
.quote-text{font-size:16px;font-weight:300;color:var(--text2);line-height:1.75;font-style:italic;padding-left:16px}
.quote-author{font-size:11px;font-family:var(--mono);color:var(--text3);margin-top:12px;padding-left:16px;letter-spacing:0.06em}

/* FOOTER */
footer{border-top:1px solid var(--border);padding:20px 32px;display:flex;align-items:center;justify-content:space-between}
.footer-text{font-size:11px;font-family:var(--mono);color:var(--text3)}

/* ANIMATIONS */
@keyframes fadeUp{from{opacity:0;transform:translateY(20px)}to{opacity:1;transform:translateY(0)}}
.hero-inner>*{animation:fadeUp 0.6s ease both}
.hero-status{animation-delay:0s}
.hero-title{animation-delay:0.08s}
.hero-subtitle{animation-delay:0.14s}
.hero-chips{animation-delay:0.2s}
.hero-stats{animation-delay:0.26s}
</style>
</head>
<body>

<nav>
  <span class="nav-name">SP</span>
  <div class="nav-links">
    <a class="nav-link active" href="#about">about</a>
    <a class="nav-link" href="#stack">stack</a>
    <a class="nav-link" href="#work">work</a>
    <a class="nav-link" href="#connect">connect</a>
  </div>
  <div class="nav-dot"></div>
</nav>

<!-- HERO -->
<section class="hero" id="top">
  <div class="hero-bg-grid"></div>
  <div class="hero-bg-glow"></div>
  <div class="hero-inner">
    <div class="hero-status">
      <span style="width:6px;height:6px;border-radius:50%;background:#22C55E;box-shadow:0 0 6px #22C55E;display:inline-block"></span>
      Available for senior iOS roles
    </div>
    <div class="hero-title">SHIVAM<br/><span class="accent">PANDEY</span></div>
    <div class="hero-subtitle">iOS Engineer &nbsp;·&nbsp; Real-Time Systems &nbsp;·&nbsp; High-Performance Mobile</div>
    <div class="hero-chips">
      <span class="hchip">Swift</span><span class="hchip">SwiftUI</span><span class="hchip">UIKit</span>
      <span class="hchip">MQTT</span><span class="hchip">WebSockets</span>
      <span class="hchip">MVVM</span><span class="hchip">Clean Architecture</span><span class="hchip">async/await</span>
    </div>
    <div class="hero-stats">
      <div class="hstat"><div class="hstat-val">5<span>yrs</span></div><div class="hstat-key">Experience</div></div>
      <div class="hstat"><div class="hstat-val" style="color:var(--green)">Prod<span style="color:var(--text3);font-size:22px">ready</span></div><div class="hstat-key">Every Build</div></div>
      <div class="hstat"><div class="hstat-val">Top<span>5%</span></div><div class="hstat-key">iOS Engineer Tier</div></div>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section class="section" id="about">
  <div class="section-head">
    <span class="section-num">01 /</span>
    <span class="section-title">ABOUT ME</span>
    <div class="section-line"></div>
  </div>
  <div class="about-grid">
    <div class="acard">
      <div class="acard-icon-row">
        <div class="acard-icon" style="background:rgba(59,130,246,0.12)">📱</div>
        <span class="acard-label" style="color:var(--blue2)">iOS engineer</span>
      </div>
      <div class="acard-body">Swift, UIKit &amp; SwiftUI specialist. Builds polished, production-grade apps focused on real-world reliability and seamless user experience.</div>
    </div>
    <div class="acard">
      <div class="acard-icon-row">
        <div class="acard-icon" style="background:rgba(34,197,94,0.12)">📡</div>
        <span class="acard-label" style="color:#4ADE80">Real-time systems</span>
      </div>
      <div class="acard-body">Deep expertise in MQTT, WebSockets &amp; socket-based architectures for mission-critical live data flows and device communication.</div>
    </div>
    <div class="acard">
      <div class="acard-icon-row">
        <div class="acard-icon" style="background:rgba(245,158,11,0.12)">⚡</div>
        <span class="acard-label" style="color:#FCD34D">Performance obsessed</span>
      </div>
      <div class="acard-body">Concurrency, memory efficiency &amp; Instruments profiling at the core of every build. Debugs production issues others can't find.</div>
    </div>
    <div class="acard">
      <div class="acard-icon-row">
        <div class="acard-icon" style="background:rgba(168,85,247,0.12)">🏛️</div>
        <span class="acard-label" style="color:#C4B5FD">Clean architecture</span>
      </div>
      <div class="acard-body">MVVM + Clean Architecture + modular design. Builds codebases that scale across teams and survive years of production evolution.</div>
    </div>
  </div>
</section>

<!-- TECH STACK -->
<section class="section" id="stack">
  <div class="section-head">
    <span class="section-num">02 /</span>
    <span class="section-title">TECH STACK</span>
    <div class="section-line"></div>
  </div>
  <div class="stack-wrapper">
    <div class="stack-card">
      <div class="stack-card-head">Languages &amp; UI</div>
      <div class="badge-row">
        <span class="badge b-amber">Swift</span>
        <span class="badge b-blue">SwiftUI</span>
        <span class="badge b-blue">UIKit</span>
        <span class="badge b-gray">Objective-C</span>
      </div>
    </div>
    <div class="stack-card">
      <div class="stack-card-head">Concurrency</div>
      <div class="badge-row">
        <span class="badge b-green">async/await</span>
        <span class="badge b-green">Combine</span>
        <span class="badge b-purple">GCD</span>
        <span class="badge b-purple">OperationQueue</span>
      </div>
    </div>
    <div class="stack-card">
      <div class="stack-card-head">Networking &amp; real-time</div>
      <div class="badge-row">
        <span class="badge b-blue">REST APIs</span>
        <span class="badge b-green">WebSockets</span>
        <span class="badge b-purple">MQTT</span>
        <span class="badge b-gray">Alamofire</span>
        <span class="badge b-gray">URLSession</span>
      </div>
    </div>
    <div class="stack-card">
      <div class="stack-card-head">Storage &amp; security</div>
      <div class="badge-row">
        <span class="badge b-amber">CoreData</span>
        <span class="badge b-purple">Realm</span>
        <span class="badge b-green">Keychain</span>
        <span class="badge b-gray">UserDefaults</span>
      </div>
    </div>
    <div class="stack-card">
      <div class="stack-card-head">Architecture</div>
      <div class="badge-row">
        <span class="badge b-blue">MVVM</span>
        <span class="badge b-green">Clean Architecture</span>
        <span class="badge b-purple">Modular design</span>
        <span class="badge b-gray">Offline-first</span>
      </div>
    </div>
    <div class="stack-card">
      <div class="stack-card-head">Tools &amp; DevOps</div>
      <div class="badge-row">
        <span class="badge b-blue">Xcode</span>
        <span class="badge b-amber">Instruments</span>
        <span class="badge b-green">Fastlane</span>
        <span class="badge b-purple">SPM</span>
        <span class="badge b-gray">CocoaPods</span>
        <span class="badge b-red">Firebase</span>
        <span class="badge b-gray">Git</span>
      </div>
    </div>
  </div>
</section>

<!-- FEATURED WORK -->
<section class="section" id="work">
  <div class="section-head">
    <span class="section-num">03 /</span>
    <span class="section-title">FEATURED WORK</span>
    <div class="section-line"></div>
  </div>
  <div class="proj-list">

    <div class="pcard">
      <div class="pcard-bar" style="background:linear-gradient(90deg,#22C55E,transparent)"></div>
      <div class="pcard-body">
        <div class="pcard-header">
          <div class="pcard-title">Real-Time IoT Monitoring System</div>
          <span class="pcard-type" style="background:rgba(34,197,94,0.1);border-color:rgba(34,197,94,0.25);color:#4ADE80">MQTT · IoT</span>
        </div>
        <div class="pcard-desc">Low-latency iOS app monitoring IoT devices in real time. Engineered for stability in high-frequency, mission-critical environments.</div>
        <div class="pcard-bullets">
          <div class="pbullet"><div class="pbullet-dot"></div>Designed resilient message handling with retry &amp; persistence logic</div>
          <div class="pbullet"><div class="pbullet-dot"></div>Optimized background connectivity for stable device communication</div>
          <div class="pbullet"><div class="pbullet-dot"></div>Improved reliability in high-frequency data environments</div>
        </div>
        <div class="pcard-tags">
          <span class="badge b-amber">Swift</span>
          <span class="badge b-purple">MQTT</span>
          <span class="badge b-amber">CoreData</span>
          <span class="badge b-blue">MVVM</span>
        </div>
      </div>
      <div class="pcard-metric-row">
        <div class="pmetric"><div class="pmetric-val" style="color:#22C55E">↓ ms</div><div class="pmetric-key">Latency</div></div>
        <div class="pmetric"><div class="pmetric-val" style="color:#22C55E">99.9%</div><div class="pmetric-key">Uptime</div></div>
        <div class="pmetric"><div class="pmetric-val" style="color:#22C55E">Live</div><div class="pmetric-key">Data stream</div></div>
      </div>
    </div>

    <div class="pcard">
      <div class="pcard-bar" style="background:linear-gradient(90deg,#3B82F6,transparent)"></div>
      <div class="pcard-body">
        <div class="pcard-header">
          <div class="pcard-title">High-Performance Data Streaming Dashboard</div>
          <span class="pcard-type" style="background:rgba(59,130,246,0.1);border-color:rgba(59,130,246,0.25);color:#93C5FD">WebSockets · UIKit</span>
        </div>
        <div class="pcard-desc">Real-time dashboard handling continuous high-frequency updates. Engineered for buttery-smooth 60fps rendering under heavy sustained load.</div>
        <div class="pcard-bullets">
          <div class="pbullet"><div class="pbullet-dot"></div>Implemented optimized UI rendering for smooth updates</div>
          <div class="pbullet"><div class="pbullet-dot"></div>Reduced UI lag using batching and throttling strategies</div>
          <div class="pbullet"><div class="pbullet-dot"></div>Improved responsiveness under heavy data loads</div>
        </div>
        <div class="pcard-tags">
          <span class="badge b-blue">UIKit</span>
          <span class="badge b-green">Combine</span>
          <span class="badge b-green">WebSockets</span>
        </div>
      </div>
      <div class="pcard-metric-row">
        <div class="pmetric"><div class="pmetric-val" style="color:#60A5FA">60fps</div><div class="pmetric-key">Render</div></div>
        <div class="pmetric"><div class="pmetric-val" style="color:#60A5FA">↓ lag</div><div class="pmetric-key">UI lag</div></div>
        <div class="pmetric"><div class="pmetric-val" style="color:#60A5FA">Heavy</div><div class="pmetric-key">Load ready</div></div>
      </div>
    </div>

    <div class="pcard">
      <div class="pcard-bar" style="background:linear-gradient(90deg,#F59E0B,transparent)"></div>
      <div class="pcard-body">
        <div class="pcard-header">
          <div class="pcard-title">Secure Authentication Framework</div>
          <span class="pcard-type" style="background:rgba(245,158,11,0.1);border-color:rgba(245,158,11,0.25);color:#FCD34D">Auth · Keychain</span>
        </div>
        <div class="pcard-desc">End-to-end secure authentication with full token lifecycle management, encrypted storage, and seamless session continuity.</div>
        <div class="pcard-bullets">
          <div class="pbullet"><div class="pbullet-dot"></div>Implemented refresh-token based authentication system</div>
          <div class="pbullet"><div class="pbullet-dot"></div>Secure credential storage using Keychain</div>
          <div class="pbullet"><div class="pbullet-dot"></div>Session management with auto re-authentication</div>
        </div>
        <div class="pcard-tags">
          <span class="badge b-amber">Swift</span>
          <span class="badge b-green">Keychain</span>
          <span class="badge b-blue">REST APIs</span>
        </div>
      </div>
      <div class="pcard-metric-row">
        <div class="pmetric"><div class="pmetric-val" style="color:#FCD34D">Zero</div><div class="pmetric-key">Leaks</div></div>
        <div class="pmetric"><div class="pmetric-val" style="color:#FCD34D">Auto</div><div class="pmetric-key">Refresh</div></div>
        <div class="pmetric"><div class="pmetric-val" style="color:#FCD34D">AES</div><div class="pmetric-key">Encrypted</div></div>
      </div>
    </div>

  </div>
</section>

<!-- CORE EXPERTISE -->
<section class="section">
  <div class="section-head">
    <span class="section-num">04 /</span>
    <span class="section-title">CORE EXPERTISE</span>
    <div class="section-line"></div>
  </div>
  <div class="exp-grid">
    <div class="exp-item"><div class="exp-stripe" style="background:#22C55E"></div><span class="exp-label">Real-time mobile application development</span></div>
    <div class="exp-item"><div class="exp-stripe" style="background:#3B82F6"></div><span class="exp-label">High-performance UI rendering &amp; optimization</span></div>
    <div class="exp-item"><div class="exp-stripe" style="background:#A855F7"></div><span class="exp-label">Multi-threading &amp; concurrency management</span></div>
    <div class="exp-item"><div class="exp-stripe" style="background:#F59E0B"></div><span class="exp-label">System design for scalable iOS applications</span></div>
    <div class="exp-item"><div class="exp-stripe" style="background:#22C55E"></div><span class="exp-label">Offline-first architecture &amp; data synchronization</span></div>
    <div class="exp-item"><div class="exp-stripe" style="background:#EF4444"></div><span class="exp-label">Secure authentication flows &amp; session management</span></div>
  </div>
</section>

<!-- GITHUB STATS -->
<section class="section">
  <div class="section-head">
    <span class="section-num">05 /</span>
    <span class="section-title">GITHUB STATS</span>
    <div class="section-line"></div>
  </div>
  <div class="stats-row">
    <div class="stat-card"><img src="https://github-readme-streak-stats.herokuapp.com/?user=ShivamSp777&hide_border=true&theme=dark&background=111114&ring=3B82F6&fire=F59E0B&currStreakLabel=F0F0F4" alt="GitHub streak stats"/></div>
    <div class="stat-card"><img src="https://github-readme-stats.vercel.app/api/top-langs/?username=ShivamSp777&layout=compact&hide_border=true&theme=dark&bg_color=111114&title_color=3B82F6&text_color=9090A0" alt="Top languages"/></div>
  </div>
</section>

<!-- CURRENTLY EXPLORING -->
<section class="section">
  <div class="section-head">
    <span class="section-num">06 /</span>
    <span class="section-title">CURRENTLY EXPLORING</span>
    <div class="section-line"></div>
  </div>
  <div class="ex-grid">
    <div class="ex-card"><div class="ex-n">01</div><div><div class="ex-title">Advanced Swift Concurrency</div><div class="ex-sub">actors &amp; structured concurrency</div></div></div>
    <div class="ex-card"><div class="ex-n">02</div><div><div class="ex-title">Scalable Architecture</div><div class="ex-sub">large iOS codebase design</div></div></div>
    <div class="ex-card"><div class="ex-n">03</div><div><div class="ex-title">Performance Optimization</div><div class="ex-sub">real-time system profiling</div></div></div>
    <div class="ex-card"><div class="ex-n">04</div><div><div class="ex-title">Modular iOS Frameworks</div><div class="ex-sub">enterprise app architecture</div></div></div>
  </div>
</section>

<!-- CONNECT -->
<section class="section" id="connect">
  <div class="section-head">
    <span class="section-num">07 /</span>
    <span class="section-title">CONNECT</span>
    <div class="section-line"></div>
  </div>
  <div class="connect-grid">
    <a class="ccard" href="https://github.com/ShivamSp777">
      <div class="ccard-icon" style="background:rgba(80,80,96,0.2);font-size:18px">⌥</div>
      <div><div class="ccard-label">GitHub</div><div class="ccard-val">github.com/ShivamSp777</div></div>
    </a>
    <a class="ccard" href="https://www.linkedin.com/in/shivam-pandey-798a85152/">
      <div class="ccard-icon" style="background:rgba(59,130,246,0.12);font-size:18px">in</div>
      <div><div class="ccard-label">LinkedIn</div><div class="ccard-val">shivam-pandey-798a85152</div></div>
    </a>
    <a class="ccard" href="mailto:pandeyshivamsp526@gmail.com">
      <div class="ccard-icon" style="background:rgba(239,68,68,0.12);font-size:16px">✉</div>
      <div><div class="ccard-label">Email</div><div class="ccard-val">pandeyshivamsp526@gmail.com</div></div>
    </a>
  </div>
</section>

<!-- PHILOSOPHY -->
<div class="quote-section">
  <div class="section-head">
    <span class="section-num">08 /</span>
    <span class="section-title">PHILOSOPHY</span>
    <div class="section-line"></div>
  </div>
  <div class="quote-box">
    <div class="quote-mark">"</div>
    <div class="quote-text">Build systems that don't just work — but perform reliably under real-world constraints.</div>
    <div class="quote-author">— Shivam Pandey, iOS Engineer</div>
  </div>
</div>

<footer>
  <span class="footer-text">shivam pandey · ios engineer · 2025</span>
  <span class="footer-text">built with swift · shipped to production</span>
</footer>

<script>
const links = document.querySelectorAll('.nav-link');
links.forEach(l => l.addEventListener('click', () => {
  links.forEach(x => x.classList.remove('active'));
  l.classList.add('active');
}));

const obs = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if(e.isIntersecting){
      const id = e.target.id;
      links.forEach(l => {
        l.classList.toggle('active', l.getAttribute('href') === '#'+id);
      });
    }
  });
}, {rootMargin:'-40% 0px -55% 0px'});
['about','stack','work','connect'].forEach(id => {
  const el = document.getElementById(id);
  if(el) obs.observe(el);
});
</script>
</body>
</html>
