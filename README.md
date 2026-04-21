<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>ICT Scalping Strategy — SbCapitalCo.</title>
<link href="https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Barlow+Condensed:wght@300;400;600;700;900&family=Barlow:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #06080c;
    --card: #0f1520;
    --card2: #111a26;
    --border: #1a2840;
    --border2: #223050;
    --accent: #00d4ff;
    --green: #00e87a;
    --red: #ff3355;
    --gold: #f0c040;
    --muted: #3a5570;
    --text: #c0d4e8;
    --text-dim: #5a7a94;
    --text-bright: #e8f2ff;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }
  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Barlow', sans-serif;
    font-weight: 300;
    line-height: 1.6;
    overflow-x: hidden;
    padding-bottom: 80px;
  }

  /* WATERMARKS - toned down on mobile */
  .wm-corner {
    position: fixed;
    bottom: 12px;
    right: 16px;
    z-index: 9999;
    pointer-events: none;
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    gap: 2px;
  }
  .wm-corner-brand {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 700;
    font-size: 11px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: rgba(0,212,255,0.35);
  }
  .wm-corner-sub {
    font-family: 'Share Tech Mono', monospace;
    font-size: 7px;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    color: rgba(90,122,148,0.4);
  }

  .wm-ghost {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%) rotate(-30deg);
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 900;
    font-size: 12vw;
    letter-spacing: 0.1em;
    text-transform: uppercase;
    color: rgba(0,212,255,0.015);
    pointer-events: none;
    z-index: 0;
    white-space: nowrap;
    user-select: none;
  }

  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background: repeating-linear-gradient(0deg,transparent,transparent 2px,rgba(0,212,255,0.008) 2px,rgba(0,212,255,0.008) 4px);
    pointer-events: none;
    z-index: 2;
  }

  .page-wrap { position: relative; z-index: 3; }

  /* Top Bar */
  .topbar {
    background: rgba(6,8,12,0.98);
    border-bottom: 1px solid var(--border);
    padding: 0 16px;
    height: 44px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    position: sticky;
    top: 0;
    z-index: 500;
    backdrop-filter: blur(12px);
  }
  .topbar-left {
    font-family: 'Share Tech Mono', monospace;
    font-size: 8px;
    letter-spacing: 2px;
    color: var(--muted);
    text-transform: uppercase;
  }
  .topbar-brand {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 700;
    font-size: 13px;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--accent);
  }

  /* Hero - Mobile Optimized */
  .hero {
    padding: 32px 20px 28px;
    border-bottom: 1px solid var(--border);
    background: linear-gradient(135deg,rgba(0,212,255,0.05) 0%,transparent 55%);
    display: flex;
    flex-direction: column;
    gap: 24px;
  }
  .hero-eyebrow { display: flex; flex-wrap: wrap; gap: 8px; }
  .htag {
    font-family: 'Share Tech Mono', monospace;
    font-size: 8.5px;
    letter-spacing: 2px;
    text-transform: uppercase;
    padding: 4px 9px;
    border: 1px solid rgba(0,212,255,0.25);
    color: var(--accent);
    background: rgba(0,212,255,0.06);
    border-radius: 2px;
  }
  .htag.gold { border-color: rgba(240,192,64,0.25); color: var(--gold); background: rgba(240,192,64,0.06); }

  .hero-title {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 900;
    font-size: 2.4rem;
    line-height: 0.95;
    letter-spacing: -1px;
    color: var(--text-bright);
    text-transform: uppercase;
  }
  .hero-title .a { color: var(--accent); }
  .hero-title .d { color: var(--text-dim); font-weight: 300; }

  .hero-sub {
    font-size: 0.88rem;
    color: var(--text-dim);
    line-height: 1.5;
  }

  .brand-block {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    gap: 2px;
  }
  .brand-name {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 900;
    font-size: 1.65rem;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: var(--text-bright);
    line-height: 1;
  }
  .brand-name span { color: var(--accent); }

  .author-credit {
    font-family: 'Share Tech Mono', monospace;
    font-size: 8.5px;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    color: var(--muted);
  }

  /* Container */
  .container {
    max-width: 100%;
    margin: 0 auto;
    padding: 24px 16px 40px;
    display: flex;
    flex-direction: column;
    gap: 32px;
  }

  .sl {
    font-family: 'Share Tech Mono', monospace;
    font-size: 9px;
    letter-spacing: 3px;
    color: var(--accent);
    text-transform: uppercase;
    margin-bottom: 12px;
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .sl .n { color: var(--muted); }
  .sl::after { content:''; flex:1; height:1px; background:linear-gradient(90deg,var(--border2),transparent); }

  .card {
    background: var(--card);
    border: 1px solid var(--border);
    padding: 20px 18px;
    position: relative;
    overflow: hidden;
    border-radius: 4px;
  }
  .card::before { content:''; position:absolute; top:0; left:0; width:3px; height:100%; background:var(--accent); }
  .card.ga::before { background:var(--green); }
  .card.ra::before { background:var(--red); }
  .card.oa::before { background:var(--gold); }

  .ct {
    font-family: 'Barlow Condensed', sans-serif;
    font-weight: 700;
    font-size: 1.05rem;
    text-transform: uppercase;
    letter-spacing: 1px;
    color: var(--text-bright);
    margin-bottom: 14px;
  }

  /* Flow - better mobile scrolling */
  .flow {
    display: flex;
    overflow-x: auto;
    gap: 12px;
    padding-bottom: 12px;
    scrollbar-width: none;
  }
  .flow::-webkit-scrollbar { display: none; }
  .fs {
    flex: 0 0 82%;
    padding: 18px 14px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 4px;
    text-align: center;
    position: relative;
  }
  .fn { font-size: 7.5px; letter-spacing: 1.5px; opacity: 0.8; margin-bottom: 6px; }
  .fi { font-size: 1.8rem; margin-bottom: 8px; }
  .ftt { font-size: 0.95rem; font-weight: 700; letter-spacing: 0.5px; }

  .g2 { display: grid; grid-template-columns: 1fr; gap: 16px; }

  .steps { display: flex; flex-direction: column; gap: 10px; }
  .step {
    display: flex;
    gap: 12px;
    padding: 12px 14px;
    background: rgba(0,212,255,0.02);
    border: 1px solid rgba(0,212,255,0.08);
    border-radius: 4px;
  }
  .sn {
    font-family: 'Share Tech Mono', monospace;
    font-size: 11px;
    color: var(--accent);
    min-width: 20px;
  }

  .tr { display: flex; flex-wrap: wrap; gap: 6px; margin-top: 12px; }
  .tag {
    font-size: 8px;
    padding: 3px 8px;
    border: 1px solid var(--border2);
    border-radius: 2px;
  }

  .tbl { width: 100%; border-collapse: collapse; font-size: 0.82rem; }
  .tbl th, .tbl td { padding: 10px 12px; text-align: left; border-bottom: 1px solid var(--border); }

  .kz { padding: 16px; background: rgba(0,0,0,0.3); border: 1px solid var(--border); border-radius: 4px; }

  .disc {
    padding: 16px 18px;
    border: 1px solid rgba(255,51,85,0.25);
    background: rgba(255,51,85,0.04);
    border-radius: 4px;
    font-size: 0.82rem;
    line-height: 1.5;
  }

  .pfooter {
    padding: 20px 16px;
    border-top: 1px solid var(--border);
    background: rgba(6,8,12,0.95);
    font-size: 8px;
    color: var(--muted);
    text-align: center;
    line-height: 1.6;
  }

  /* Extra mobile tweaks */
  @media (min-width: 600px) {
    .hero { flex-direction: row; padding: 40px 24px; }
    .hero-title { font-size: 2.8rem; }
    .g2 { grid-template-columns: 1fr 1fr; }
    .flow { gap: 8px; }
    .fs { flex: 1; }
  }
</style>
</head>
<body>

<!-- WATERMARKS -->
<div class="wm-corner">
  <div class="wm-corner-brand">SbCapitalCo.</div>
  <div class="wm-corner-sub">by Sharn · All Rights Reserved</div>
</div>
<div class="wm-ghost">SbCapitalCo.</div>

<div class="page-wrap">

<!-- TOP BAR -->
<div class="topbar">
  <div class="topbar-left">ICT • Scalping Framework</div>
  <div class="topbar-brand">SbCapitalCo.</div>
</div>

<!-- HERO -->
<div class="hero">
  <div>
    <div class="hero-eyebrow">
      <span class="htag">ICT Strategy</span>
      <span class="htag gold">Scalping • Day Trading</span>
    </div>
    <div class="hero-title">
      <div>Smart Money</div>
      <div><span class="a">Scalping</span> <span class="d">Setup</span></div>
      <div>Framework</div>
    </div>
    <div class="hero-sub">Professional ICT-based scalping strategy. Market structure, kill zones, order blocks, FVGs &amp; high-probability execution.</div>
  </div>
  <div style="text-align:right;">
    <div class="brand-block">
      <div class="brand-name">Sb<span>Capital</span>Co.</div>
      <div class="brand-tag">Proprietary Framework</div>
    </div>
    <div class="author-credit">Lead Strategist — <span>Sharn</span></div>
  </div>
</div>

<!-- CONTENT -->
<div class="container">

  <!-- 01 Setup Flow -->
  <div>
    <div class="sl"><span class="n">01</span> Setup Flow</div>
    <div class="flow">
      <div class="fs"><div class="fn">STEP 01</div><div class="fi">🧭</div><div class="ftt">HTF Bias</div><div class="fs-sub">Daily &amp; 4H structure</div></div>
      <div class="fs"><div class="fn">STEP 02</div><div class="fi">⏰</div><div class="ftt">Kill Zone</div><div class="fs-sub">London / NY Open</div></div>
      <div class="fs"><div class="fn">STEP 03</div><div class="fi">🎯</div><div class="ftt">POI Hunt</div><div class="fs-sub">OB or FVG</div></div>
      <div class="fs"><div class="fn">STEP 04</div><div class="fi">✅</div><div class="ftt">Confirmation</div><div class="fs-sub">MSS + Displacement</div></div>
      <div class="fs"><div class="fn">STEP 05</div><div class="fi">📈</div><div class="ftt">Entry</div><div class="fs-sub">Limit at OB/FVG</div></div>
      <div class="fs"><div class="fn">STEP 06</div><div class="fi">🛡️</div><div class="ftt">Manage</div><div class="fs-sub">TP Liquidity • SL</div></div>
    </div>
  </div>

  <!-- 02 Timeframes -->
  <div>
    <div class="sl"><span class="n">02</span> Multi-Timeframe Framework</div>
    <div class="card">
      <table class="tbl">
        <thead><tr><th>Timeframe</th><th>Role</th></tr></thead>
        <tbody>
          <tr><td>Daily / 4H</td><td>Directional Bias</td></tr>
          <tr><td>15M</td><td>Setup &amp; MSS Confirmation</td></tr>
          <tr><td>5M</td><td>Refinement &amp; Displacement</td></tr>
          <tr><td>1M–2M</td><td>Precise Entry &amp; Management</td></tr>
        </tbody>
      </table>
    </div>
  </div>

  <!-- 03 Kill Zones -->
  <div>
    <div class="sl"><span class="n">03</span> ICT Kill Zones (EST)</div>
    <div class="g2">
      <div class="card oa">
        <div class="ct">London Open <span style="font-size:0.75rem;opacity:0.7;">(Prime)</span></div>
        <div class="kz"><strong>02:00 – 05:00</strong><br>Best for major FX pairs</div>
      </div>
      <div class="card oa">
        <div class="ct">New York Open <span style="font-size:0.75rem;opacity:0.7;">(Prime)</span></div>
        <div class="kz"><strong>08:30 – 11:00</strong><br>Highest volume session</div>
      </div>
    </div>
  </div>

  <!-- 04 Entry Setups -->
  <div>
    <div class="sl"><span class="n">04</span> Entry Setups</div>
    <div class="g2">
      <div class="card ga">
        <div class="ct">Long Bias • Bullish Setup</div>
        <div class="steps">
          <div class="step"><div class="sn">01</div><div>HTF Bullish Structure + Discount Zone</div></div>
          <div class="step"><div class="sn">02</div><div>Sell-Side Liquidity Sweep</div></div>
          <div class="step"><div class="sn">03</div><div>Bullish MSS + Displacement</div></div>
          <div class="step"><div class="sn">04</div><div>Limit Buy at Bullish OB / FVG</div></div>
        </div>
      </div>

      <div class="card ra">
        <div class="ct">Short Bias • Bearish Setup</div>
        <div class="steps">
          <div class="step"><div class="sn">01</div><div>HTF Bearish Structure + Premium Zone</div></div>
          <div class="step"><div class="sn">02</div><div>Buy-Side Liquidity Sweep</div></div>
          <div class="step"><div class="sn">03</div><div>Bearish MSS + Displacement</div></div>
          <div class="step"><div class="sn">04</div><div>Limit Sell at Bearish OB / FVG</div></div>
        </div>
      </div>
    </div>
  </div>

  <!-- Disclaimer -->
  <div class="disc">
    <strong style="color:#ff3355;">RISK NOTICE:</strong> This is for educational purposes only. Trading carries substantial risk of capital loss. Not financial advice.
  </div>

</div>

<!-- FOOTER -->
<div class="pfooter">
  ICT Scalping Framework • © SbCapitalCo. by Sharn<br>
  All Rights Reserved
</div>

</div>

<script>
  // Optional: Add subtle tile watermark if desired
</script>

</body>
</html>
