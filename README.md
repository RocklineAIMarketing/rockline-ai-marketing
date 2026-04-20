# rockline-ai-marketing
************The Play: Use Schema Markup (specifically Organization or RelatedTo properties) to explicitly define these relationships for AI crawlers. This turns a simple link into a structured data point.***********
header foot v2
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Rockline AI Marketing – Header &amp; Footer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Rajdhani:wght@400;500;600;700&family=Exo+2:wght@300;400;500;600&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
<style>
  :root {
    --blue-bright: #279cf5;
    --blue-light:  #bbe0fc;
    --blue-mid:    #8fcbfa;
    --blue-dark:   #032844;
    --white:       #ffffff;
    --glass:       rgba(3,40,68,0.82);
    --ticker-bg:   #021d32;
  }
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  html { scroll-behavior: smooth; }
  body { font-family: 'Exo 2', sans-serif; background: var(--blue-dark); color: var(--white); overflow-x: hidden; }

  /* =============================================
     DESKTOP HEADER
     ============================================= */
  #site-header {
    background: linear-gradient(180deg, #075C9D 0%, var(--blue-dark) 100%);
    border-bottom: 1px solid rgba(39,156,245,0.18);
  }
  .header-brand {
    display: flex; align-items: center; justify-content: center;
    position: relative; padding: 18px 24px 12px;
  }
  .cta-sms {
    position: absolute; left: 32px; top: 50%; transform: translateY(-50%);
    display: flex; align-items: center; gap: 8px;
    background: linear-gradient(135deg, var(--blue-bright), #1479c4);
    color: var(--white); text-decoration: none;
    font-family: 'Rajdhani', sans-serif; font-weight: 700;
    font-size: 13px; letter-spacing: 1.6px; text-transform: uppercase;
    padding: 10px 20px; border-radius: 4px;
    border: 1px solid rgba(255,255,255,0.12);
    box-shadow: 0 4px 20px rgba(39,156,245,0.3);
    transition: transform .2s, box-shadow .2s; white-space: nowrap;
  }
  .cta-sms:hover { transform: translateY(calc(-50% - 2px)); box-shadow: 0 10px 32px rgba(39,156,245,0.5); }
  .logo-placeholder {
    width: 150px; height: 72px;
    border: 2px dashed var(--blue-mid); border-radius: 8px;
    display: flex; align-items: center; justify-content: center;
    background: rgba(143,203,250,0.05); cursor: pointer;
    transition: border-color .3s, background .3s;
  }
  .logo-placeholder:hover { border-color: var(--blue-bright); background: rgba(39,156,245,0.1); }
  .logo-placeholder span {
    font-family: 'Rajdhani', sans-serif; font-size: 10px;
    letter-spacing: 1.5px; color: var(--blue-mid);
    text-transform: uppercase; text-align: center; line-height: 1.5;
  }

  /* =============================================
     DESKTOP STICKY NAV + TICKER
     ============================================= */
  #sticky-nav-zone {
    position: sticky; top: 0; z-index: 500;
    background: var(--glass);
    backdrop-filter: blur(18px); -webkit-backdrop-filter: blur(18px);
    border-bottom: 1px solid rgba(39,156,245,0.18);
    box-shadow: 0 4px 30px rgba(2,10,20,0.6);
  }
  nav.main-nav { display: flex; align-items: center; justify-content: center; gap: 2px; padding: 0 16px; }
  .nav-item { position: relative; }
  .nav-btn {
    display: flex; align-items: center; gap: 5px;
    padding: 14px 20px;
    font-family: 'Rajdhani', sans-serif; font-weight: 600;
    font-size: 13px; letter-spacing: 2px; text-transform: uppercase;
    color: var(--blue-light); background: none; border: none;
    cursor: pointer; text-decoration: none;
    transition: color .2s; white-space: nowrap; position: relative;
  }
  .nav-btn:hover, .nav-item.is-open > .nav-btn { color: var(--white); }
  a.nav-btn.active { color: var(--white); }
  a.nav-btn::after {
    content: ''; position: absolute;
    bottom: 8px; left: 20px; right: 20px;
    height: 2px; background: var(--blue-bright);
    border-radius: 2px; transform: scaleX(0); transition: transform .25s;
  }
  a.nav-btn:hover::after, a.nav-btn.active::after { transform: scaleX(1); }
  span.nav-btn { cursor: default; }
  .chevron { width: 10px; height: 10px; transition: transform .25s; flex-shrink: 0; }
  .nav-item.is-open .chevron { transform: rotate(180deg); }

  .dropdown {
    position: absolute; top: 100%; left: 50%;
    transform: translateX(-50%) translateY(6px);
    min-width: 220px;
    background: rgba(2,12,24,0.97);
    border: 1px solid rgba(39,156,245,0.2); border-radius: 6px;
    box-shadow: 0 16px 48px rgba(0,0,0,0.55);
    opacity: 0; pointer-events: none;
    transition: opacity .22s, transform .22s; z-index: 600; overflow: hidden;
  }
  .dropdown::before {
    content: ''; position: absolute;
    top: -8px; left: 0; right: 0; height: 8px;
  }
  .nav-item.is-open .dropdown {
    opacity: 1; pointer-events: auto;
    transform: translateX(-50%) translateY(0);
  }
  .dropdown a {
    display: block; padding: 12px 22px;
    font-family: 'Exo 2', sans-serif; font-size: 13px;
    color: var(--blue-light); text-decoration: none; letter-spacing: .5px;
    border-bottom: 1px solid rgba(39,156,245,0.07);
    transition: background .18s, color .18s, padding-left .18s;
  }
  .dropdown a:last-child { border-bottom: none; }
  .dropdown a:hover { background: rgba(39,156,245,0.1); color: var(--white); padding-left: 28px; }

  /* =============================================
     TICKER
     ============================================= */
  .ticker-wrap {
    background: var(--ticker-bg);
    border-top: 1px solid rgba(39,156,245,0.1);
    padding: 7px 0; overflow: hidden; position: relative;
    pointer-events: none;
  }
  .ticker-label {
    position: absolute; left: 0; top: 0; bottom: 0; z-index: 2;
    display: flex; align-items: center;
    padding: 0 18px 0 14px;
    background: var(--blue-bright);
    font-family: 'Rajdhani', sans-serif; font-weight: 700;
    font-size: 10px; letter-spacing: 2px; text-transform: uppercase;
    color: var(--blue-dark); white-space: nowrap;
    clip-path: polygon(0 0, calc(100% - 8px) 0, 100% 50%, calc(100% - 8px) 100%, 0 100%);
  }
  .ticker-wrap::after {
    content: ''; position: absolute; right: 0; top: 0; bottom: 0; width: 60px;
    background: linear-gradient(to right, transparent, var(--ticker-bg));
    z-index: 3; pointer-events: none;
  }
  .ticker-inner { overflow: hidden; padding-left: 112px; }
  .ticker-track {
    display: flex; width: max-content;
    animation: tickerScroll 60s linear infinite;
  }
  .ticker-item {
    font-family: 'Space Mono', monospace; font-size: 10.5px;
    color: var(--blue-mid); white-space: nowrap;
    padding: 0 44px; display: flex; align-items: center; gap: 10px;
  }
  .ticker-item::after { content: '◆'; color: var(--blue-bright); font-size: 7px; }
  @keyframes tickerScroll {
    0%   { transform: translateX(0); }
    100% { transform: translateX(-50%); }
  }

  /* =============================================
     MOBILE STICKY HEADER
     ============================================= */
  #mobile-sticky {
    display: none;
    position: fixed; top: 0; left: 0; right: 0;
    z-index: 800; flex-direction: column;
  }
  .mobile-topbar {
    display: flex; align-items: center; justify-content: center;
    position: relative; padding: 10px 16px;
    background: rgba(2,12,24,0.97);
    backdrop-filter: blur(14px); -webkit-backdrop-filter: blur(14px);
    border-bottom: 1px solid rgba(39,156,245,0.15);
  }
  .mobile-logo-bar {
    width: 90px; height: 42px;
    border: 1px dashed rgba(143,203,250,0.3); border-radius: 6px;
    display: flex; align-items: center; justify-content: center;
  }
  .mobile-logo-bar span {
    font-family: 'Rajdhani', sans-serif; font-size: 8px;
    color: rgba(143,203,250,0.4); text-transform: uppercase; letter-spacing: 1px;
  }
  .hamburger-trigger {
    position: absolute; right: 16px; top: 50%; transform: translateY(-50%);
    width: 44px; height: 44px;
    cursor: pointer; background: rgba(39,156,245,0.06); border: 1px solid rgba(39,156,245,0.35);
    border-radius: 6px; padding: 0;
    display: flex; align-items: center; justify-content: center;
    transition: background .25s, border-color .25s, box-shadow .25s;
    box-shadow: 0 0 10px rgba(39,156,245,0.2);
  }
  .hamburger-trigger:hover,
  .hamburger-trigger.open {
    background: rgba(39,156,245,0.14); border-color: rgba(39,156,245,0.75);
    box-shadow: 0 0 18px rgba(39,156,245,0.45), 0 0 6px rgba(39,156,245,0.3) inset;
  }
  .hamburger-bars { display: flex; flex-direction: column; gap: 5px; width: 20px; position: relative; }
  .hamburger-bars span {
    display: block; height: 2px; border-radius: 2px; background: var(--blue-light);
    transition: transform .3s cubic-bezier(.22,1,.36,1), opacity .2s, width .3s;
  }
  .hamburger-bars span:nth-child(1) { width: 20px; }
  .hamburger-bars span:nth-child(2) { width: 14px; }
  .hamburger-bars span:nth-child(3) { width: 20px; }
  .hamburger-trigger.open .hamburger-bars span:nth-child(1) { transform: translateY(7px) rotate(45deg); }
  .hamburger-trigger.open .hamburger-bars span:nth-child(2) { opacity: 0; width: 0; }
  .hamburger-trigger.open .hamburger-bars span:nth-child(3) { transform: translateY(-7px) rotate(-45deg); }

  .mobile-ticker-strip {
    background: var(--ticker-bg); border-top: none;
    border-bottom: 1px solid rgba(39,156,245,0.1);
    padding: 5px 0; pointer-events: none;
  }
  .mobile-ticker-strip .ticker-label { font-size: 9px; padding: 0 14px 0 10px; }
  .mobile-ticker-strip .ticker-inner { padding-left: 88px; }
  .mobile-ticker-strip .ticker-track { animation-duration: 50s; }
  .mobile-ticker-strip .ticker-item { font-size: 9.5px; padding: 0 30px; }

  /* =============================================
     MOBILE PANEL + OVERLAY
     ============================================= */
  .mobile-overlay {
    display: none; position: fixed; inset: 0;
    background: rgba(2,9,16,0.55); z-index: 700;
    opacity: 0; transition: opacity .3s;
    backdrop-filter: blur(4px); pointer-events: none;
  }
  .mobile-overlay.visible { opacity: 1; pointer-events: auto; }
  .mobile-panel {
    position: fixed; top: 0; right: -310px; width: 290px; height: 100%;
    background: rgba(2,12,24,0.99); border-left: 1px solid rgba(39,156,245,0.18);
    z-index: 900; transition: right .34s cubic-bezier(.22,1,.36,1);
    overflow-y: auto; padding-bottom: 48px;
  }
  .mobile-panel.open { right: 0; }
  .mobile-panel-logo { display: flex; justify-content: center; padding: 28px 20px 18px; border-bottom: 1px solid rgba(39,156,245,0.1); }
  .mobile-panel-logo-box {
    width: 110px; height: 52px; border: 1px dashed rgba(143,203,250,0.25); border-radius: 6px;
    display: flex; align-items: center; justify-content: center;
  }
  .mobile-panel-logo-box span { font-family: 'Rajdhani', sans-serif; font-size: 8px; color: rgba(143,203,250,0.35); text-transform: uppercase; letter-spacing: 1px; }
  .mobile-nav-list { list-style: none; padding: 10px 0; }
  .mobile-nav-list > li > a,
  .mobile-nav-list > li > .m-parent {
    display: flex; align-items: center; justify-content: space-between;
    padding: 13px 22px;
    font-family: 'Rajdhani', sans-serif; font-weight: 600;
    font-size: 14px; letter-spacing: 1.8px; text-transform: uppercase;
    color: var(--blue-light); text-decoration: none;
    border-bottom: 1px solid rgba(39,156,245,0.06);
    transition: background .18s, color .18s; cursor: pointer;
  }
  .mobile-nav-list > li > a:hover { background: rgba(39,156,245,0.08); color: var(--white); }
  .mobile-nav-list > li > .m-parent { color: rgba(187,224,252,0.55); cursor: default; }
  .m-chevron { width: 12px; height: 12px; transition: transform .25s; color: rgba(143,203,250,0.5); flex-shrink: 0; }
  .m-parent.sub-open .m-chevron { transform: rotate(180deg); }
  .mobile-sub { display: none; background: rgba(39,156,245,0.03); border-bottom: 1px solid rgba(39,156,245,0.06); }
  .mobile-sub.open { display: block; }
  .mobile-sub a {
    display: block; padding: 10px 22px 10px 34px;
    font-size: 12.5px; color: var(--blue-mid); text-decoration: none;
    border-bottom: 1px solid rgba(39,156,245,0.04); letter-spacing: .4px;
    transition: color .18s, padding-left .18s;
  }
  .mobile-sub a:hover { color: var(--white); padding-left: 40px; }
  .mobile-panel-cta { padding: 18px 20px 0; }
  .mobile-panel-cta a {
    display: flex; align-items: center; justify-content: center; gap: 8px;
    width: 100%; padding: 13px;
    background: linear-gradient(135deg, var(--blue-bright), #1479c4);
    color: var(--white); text-decoration: none;
    font-family: 'Rajdhani', sans-serif; font-weight: 700;
    font-size: 13px; letter-spacing: 2px; text-transform: uppercase;
    border-radius: 4px; box-shadow: 0 4px 20px rgba(39,156,245,0.3);
    transition: box-shadow .25s;
  }
  .mobile-panel-cta a:hover { box-shadow: 0 8px 28px rgba(39,156,245,0.5); }

  /* =============================================
     FOOTER
     ============================================= */
  footer {
    background: linear-gradient(180deg, var(--blue-dark) 0%, #075C9D 100%);
    border-top: 1px solid rgba(39,156,245,0.14);
  }
  .footer-main { display: grid; grid-template-columns: 1fr auto 1fr; gap: 24px; align-items: center; padding: 16px 32px; border-bottom: 1px solid rgba(39,156,245,0.08); max-width: 1200px; margin: 0 auto; }
  .footer-address { font-size: 12.5px; line-height: 1.9; color: var(--blue-mid); font-style: normal; }
  .footer-address strong { display: block; font-family: 'Rajdhani', sans-serif; font-size: 14px; color: var(--white); letter-spacing: 1px; margin-bottom: 2px; }
  .footer-address a { color: var(--blue-bright); text-decoration: none; }
  .footer-address a:hover { text-decoration: underline; }
  .footer-logo-col { display: flex; justify-content: center; align-items: center; }
  .footer-logo-box { width: 90px; height: 44px; border: 1px dashed rgba(143,203,250,0.25); border-radius: 6px; display: flex; align-items: center; justify-content: center; }
  .footer-logo-box span { font-family: 'Rajdhani', sans-serif; font-size: 9px; color: rgba(143,203,250,0.35); text-transform: uppercase; letter-spacing: 1px; }
  .footer-hours { text-align: right; font-size: 12px; color: var(--blue-mid); }
  .footer-hours strong { display: block; font-family: 'Rajdhani', sans-serif; font-size: 13px; color: var(--white); letter-spacing: 1px; margin-bottom: 4px; }
  .hours-grid { display: grid; grid-template-columns: auto auto; gap: 0 10px; font-size: 11.5px; justify-content: end; }
  .hours-grid span:nth-child(even) { color: var(--blue-light); }
  .footer-social { display: flex; align-items: center; justify-content: center; gap: 6px; padding: 10px 24px; flex-wrap: wrap; }
  .social-link { width: 36px; height: 36px; border-radius: 6px; border: 1px solid rgba(255,255,255,0.07); display: flex; align-items: center; justify-content: center; text-decoration: none; background: rgba(255,255,255,0.03); transition: transform .2s, border-color .2s, background .2s; }
  .social-link:hover { transform: translateY(-3px); border-color: rgba(255,255,255,0.18); background: rgba(255,255,255,0.07); }
  .footer-bottom { padding: 8px 24px; text-align: center; font-size: 10px; color: rgba(143,203,250,0.25); letter-spacing: .8px; border-top: 1px solid rgba(39,156,245,0.05); }

  /* =============================================
     RESPONSIVE
     ============================================= */
  @media (max-width: 768px) {
    #site-header, #sticky-nav-zone { display: none; }
    #mobile-sticky { display: flex; }
    .mobile-overlay { display: block; }
    main { padding-top: 92px; }
    .footer-main { grid-template-columns: 1fr; text-align: center; gap: 12px; padding: 14px 20px; }
    .footer-hours { text-align: center; }
    .hours-grid { justify-content: center; }
    .footer-logo-col { justify-content: center; }
  }

  /* Demo spacer so header/footer aren't flush */
  .demo-spacer {
    min-height: 200px;
    display: flex; align-items: center; justify-content: center;
    color: rgba(143,203,250,0.25);
    font-family: 'Space Mono', monospace; font-size: 11px;
    letter-spacing: 1px; text-transform: uppercase;
    border-top: 1px solid rgba(39,156,245,0.06);
    border-bottom: 1px solid rgba(39,156,245,0.06);
  }
</style>
</head>
<body>

<!-- ═══════════════════════════════════════════════════════════════
     HEADER (Desktop)
     ════════════════════════════════════════════════════════════ -->
<header id="site-header">
  <div class="header-brand">
    <a href="sms:+18155555555?body=Hi%2C%20I%27d%20like%20to%20learn%20more%20about%20Rockline%20AI%20Marketing!" class="cta-sms">
      <svg width="15" height="15" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/></svg>
      Contact Us
    </a>
    <div class="logo-placeholder">
      <span>Rockline AI<br>Marketing</span>
    </div>
  </div>
</header>

<!-- ═══════════════════════════════════════════════════════════════
     STICKY NAV + TICKER (Desktop)
     ════════════════════════════════════════════════════════════ -->
<div id="sticky-nav-zone">
  <nav class="main-nav" role="navigation" aria-label="Main navigation">
    <div class="nav-item"><a href="index.html" class="nav-btn active">Home</a></div>
    <div class="nav-item">
      <span class="nav-btn" tabindex="0">About <svg class="chevron" viewBox="0 0 10 10" fill="none" stroke="currentColor" stroke-width="1.8"><path d="M2 3.5L5 6.5L8 3.5"/></svg></span>
      <div class="dropdown">
        <a href="about/agency-profile.html">Agency Profile</a>
        <a href="about/customer-success-stories.html">Customer Success Stories</a>
        <a href="about/community-activism.html">Community Activism</a>
      </div>
    </div>
    <div class="nav-item">
      <span class="nav-btn" tabindex="0">Portfolio <svg class="chevron" viewBox="0 0 10 10" fill="none" stroke="currentColor" stroke-width="1.8"><path d="M2 3.5L5 6.5L8 3.5"/></svg></span>
      <div class="dropdown">
        <a href="portfolio/website-gallery.html">Website Gallery</a>
        <a href="portfolio/photo-gallery.html">Photo Gallery</a>
        <a href="portfolio/social-gallery.html">Social Gallery</a>
      </div>
    </div>
    <div class="nav-item">
      <span class="nav-btn" tabindex="0">Services <svg class="chevron" viewBox="0 0 10 10" fill="none" stroke="currentColor" stroke-width="1.8"><path d="M2 3.5L5 6.5L8 3.5"/></svg></span>
      <div class="dropdown">
        <a href="services/custom-websites.html">Custom Websites</a>
        <a href="services/microblogging.html">Microblogging</a>
        <a href="services/aerial-8k-photography.html">Aerial &amp; 8K Photography</a>
      </div>
    </div>
    <div class="nav-item">
      <span class="nav-btn" tabindex="0">Contact <svg class="chevron" viewBox="0 0 10 10" fill="none" stroke="currentColor" stroke-width="1.8"><path d="M2 3.5L5 6.5L8 3.5"/></svg></span>
      <div class="dropdown">
        <a href="contact/business-information.html">Business Information</a>
        <a href="contact/social-media.html">Social Media</a>
        <a href="contact/q-and-a.html">Q &amp; A</a>
      </div>
    </div>
  </nav>
  <div class="ticker-wrap">
    <div class="ticker-label">GEO FAQ</div>
    <div class="ticker-inner">
      <div class="ticker-track" id="desktopTicker">
        <div class="ticker-item">What is Generative Engine Optimization (GEO)?</div>
        <div class="ticker-item">How does GEO differ from traditional SEO?</div>
        <div class="ticker-item">Can AI-driven content appear in ChatGPT and Gemini answers?</div>
        <div class="ticker-item">What makes a website discoverable by AI search engines?</div>
        <div class="ticker-item">How does Rockline AI Marketing implement GEO strategies?</div>
        <div class="ticker-item">Is GEO replacing SEO — or working alongside it?</div>
        <div class="ticker-item">How do large language models discover and cite local businesses?</div>
        <div class="ticker-item">What role does structured data play in GEO?</div>
        <div class="ticker-item">How quickly can GEO improve your online visibility?</div>
        <div class="ticker-item">What industries benefit most from Generative Engine Optimization?</div>
      </div>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════════════════════════════
     MOBILE STICKY HEADER
     ════════════════════════════════════════════════════════════ -->
<div id="mobile-sticky">
  <div class="mobile-topbar">
    <div class="mobile-logo-bar"><span>Logo</span></div>
    <button class="hamburger-trigger" id="hamburgerTrigger" aria-label="Open navigation">
      <div class="hamburger-bars"><span></span><span></span><span></span></div>
    </button>
  </div>
  <div class="mobile-ticker-strip ticker-wrap">
    <div class="ticker-label">GEO FAQ</div>
    <div class="ticker-inner">
      <div class="ticker-track" id="mobileTicker">
        <div class="ticker-item">What is Generative Engine Optimization (GEO)?</div>
        <div class="ticker-item">How does GEO differ from traditional SEO?</div>
        <div class="ticker-item">Can AI-driven content appear in ChatGPT &amp; Gemini?</div>
        <div class="ticker-item">What makes a website discoverable by AI?</div>
        <div class="ticker-item">How does Rockline AI Marketing implement GEO?</div>
        <div class="ticker-item">Is GEO replacing SEO — or working alongside it?</div>
        <div class="ticker-item">How do LLMs discover and cite local businesses?</div>
        <div class="ticker-item">What role does structured data play in GEO?</div>
        <div class="ticker-item">How quickly can GEO improve your visibility?</div>
        <div class="ticker-item">Which industries benefit most from GEO?</div>
      </div>
    </div>
  </div>
</div>

<!-- Mobile overlay + side panel -->
<div class="mobile-overlay" id="mobileOverlay"></div>
<div class="mobile-panel" id="mobilePanel" role="dialog" aria-label="Navigation">
  <div class="mobile-panel-logo"><div class="mobile-panel-logo-box"><span>Logo Here</span></div></div>
  <ul class="mobile-nav-list">
    <li><a href="index.html">Home</a></li>
    <li>
      <div class="m-parent" onclick="toggleSub(this)">About <svg class="m-chevron" viewBox="0 0 10 10" fill="none" stroke="currentColor" stroke-width="1.8"><path d="M2 3.5L5 6.5L8 3.5"/></svg></div>
      <div class="mobile-sub"><a href="about/agency-profile.html">Agency Profile</a><a href="about/customer-success-stories.html">Customer Success Stories</a><a href="about/community-activism.html">Community Activism</a></div>
    </li>
    <li>
      <div class="m-parent" onclick="toggleSub(this)">Portfolio <svg class="m-chevron" viewBox="0 0 10 10" fill="none" stroke="currentColor" stroke-width="1.8"><path d="M2 3.5L5 6.5L8 3.5"/></svg></div>
      <div class="mobile-sub"><a href="portfolio/website-gallery.html">Website Gallery</a><a href="portfolio/photo-gallery.html">Photo Gallery</a><a href="portfolio/social-gallery.html">Social Gallery</a></div>
    </li>
    <li>
      <div class="m-parent" onclick="toggleSub(this)">Services <svg class="m-chevron" viewBox="0 0 10 10" fill="none" stroke="currentColor" stroke-width="1.8"><path d="M2 3.5L5 6.5L8 3.5"/></svg></div>
      <div class="mobile-sub"><a href="services/custom-websites.html">Custom Websites</a><a href="services/microblogging.html">Microblogging</a><a href="services/aerial-8k-photography.html">Aerial &amp; 8K Photography</a></div>
    </li>
    <li>
      <div class="m-parent" onclick="toggleSub(this)">Contact <svg class="m-chevron" viewBox="0 0 10 10" fill="none" stroke="currentColor" stroke-width="1.8"><path d="M2 3.5L5 6.5L8 3.5"/></svg></div>
      <div class="mobile-sub"><a href="contact/business-information.html">Business Information</a><a href="contact/social-media.html">Social Media</a><a href="contact/q-and-a.html">Q &amp; A</a></div>
    </li>
  </ul>
  <div class="mobile-panel-cta">
    <a href="sms:+18155555555?body=Hi%2C%20I%27d%20like%20to%20learn%20more%20about%20Rockline%20AI%20Marketing!">
      <svg width="15" height="15" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/></svg>
      Text Us Now
    </a>
  </div>
</div>

<!-- ═══════════════════════════════════════════════════════════════
     MAIN CONTENT PLACEHOLDER
     ════════════════════════════════════════════════════════════ -->
<main>
  <div class="demo-spacer">← Page content goes here →</div>
</main>

<!-- ═══════════════════════════════════════════════════════════════
     FOOTER
     ════════════════════════════════════════════════════════════ -->
<footer>
  <div class="footer-main">
    <address class="footer-address">
      <strong>Rockline AI Marketing</strong>
      Lockport, IL<br>
      <a href="tel:+18155555555">815-555-5555</a>
    </address>
    <div class="footer-logo-col">
      <div class="footer-logo-box"><span>Logo</span></div>
    </div>
    <div class="footer-hours">
      <strong>Business Hours</strong>
      <div class="hours-grid"><span>Mon – Sun</span><span>7:00 AM – 9:00 PM</span></div>
    </div>
  </div>
  <div class="footer-social">
    <a href="#" class="social-link" title="YouTube" target="_blank" rel="noopener"><svg width="18" height="18" viewBox="0 0 24 24"><path fill="#FF0000" d="M23.5 6.2a3 3 0 0 0-2.1-2.1C19.5 3.6 12 3.6 12 3.6s-7.5 0-9.4.5A3 3 0 0 0 .5 6.2C0 8.1 0 12 0 12s0 3.9.5 5.8a3 3 0 0 0 2.1 2.1c1.9.5 9.4.5 9.4.5s7.5 0 9.4-.5a3 3 0 0 0 2.1-2.1C24 15.9 24 12 24 12s0-3.9-.5-5.8z"/><path fill="#fff" d="M9.6 15.6V8.4l6.3 3.6-6.3 3.6z"/></svg></a>
    <a href="#" class="social-link" title="Google My Business" target="_blank" rel="noopener"><svg width="18" height="18" viewBox="0 0 24 24"><path fill="#4285F4" d="M22.56 12.25c0-.78-.07-1.53-.2-2.25H12v4.26h5.92c-.26 1.37-1.04 2.53-2.21 3.31v2.77h3.57c2.08-1.92 3.28-4.74 3.28-8.09z"/><path fill="#34A853" d="M12 23c2.97 0 5.46-.98 7.28-2.66l-3.57-2.77c-.98.66-2.23 1.06-3.71 1.06-2.86 0-5.29-1.93-6.16-4.53H2.18v2.84C3.99 20.53 7.7 23 12 23z"/><path fill="#FBBC05" d="M5.84 14.09c-.22-.66-.35-1.36-.35-2.09s.13-1.43.35-2.09V7.07H2.18C1.43 8.55 1 10.22 1 12s.43 3.45 1.18 4.93l3.66-2.84z"/><path fill="#EA4335" d="M12 5.38c1.62 0 3.06.56 4.21 1.64l3.15-3.15C17.45 2.09 14.97 1 12 1 7.7 1 3.99 3.47 2.18 7.07l3.66 2.84c.87-2.6 3.3-4.53 6.16-4.53z"/></svg></a>
    <a href="#" class="social-link" title="Instagram" target="_blank" rel="noopener"><svg width="18" height="18" viewBox="0 0 24 24"><defs><radialGradient id="ig" cx="30%" cy="107%" r="150%"><stop offset="0%" stop-color="#fdf497"/><stop offset="45%" stop-color="#fd5949"/><stop offset="60%" stop-color="#d6249f"/><stop offset="90%" stop-color="#285AEB"/></radialGradient></defs><rect width="24" height="24" rx="5" fill="url(#ig)"/><path fill="#fff" d="M12 7.2A4.8 4.8 0 1 0 12 16.8 4.8 4.8 0 0 0 12 7.2zm0 7.9a3.1 3.1 0 1 1 0-6.2 3.1 3.1 0 0 1 0 6.2zm6.1-8.1a1.1 1.1 0 1 1-2.2 0 1.1 1.1 0 0 1 2.2 0zM21 8.9c-.1-1.5-.4-2.8-1.5-3.9-1.1-1.1-2.4-1.4-3.9-1.5C14.1 3.4 9.9 3.4 8.4 3.5 6.9 3.6 5.6 3.9 4.5 5 3.4 6.1 3.1 7.4 3 8.9 2.9 10.4 2.9 14.6 3 16.1c.1 1.5.4 2.8 1.5 3.9 1.1 1.1 2.4 1.4 3.9 1.5 1.5.1 5.7.1 7.2 0 1.5-.1 2.8-.4 3.9-1.5 1.1-1.1 1.4-2.4 1.5-3.9.1-1.5.1-5.7 0-7.2zm-2 8.7a3.2 3.2 0 0 1-1.8 1.8c-1.2.5-4.2.4-5.6.4s-4.3.1-5.6-.4a3.2 3.2 0 0 1-1.8-1.8c-.5-1.2-.4-4.2-.4-5.6s-.1-4.3.4-5.6A3.2 3.2 0 0 1 5.8 4.6c1.2-.5 4.2-.4 5.6-.4s4.3-.1 5.6.4a3.2 3.2 0 0 1 1.8 1.8c.5 1.2.4 4.2.4 5.6s.1 4.3-.4 5.6z"/></svg></a>
    <a href="#" class="social-link" title="Facebook" target="_blank" rel="noopener"><svg width="18" height="18" viewBox="0 0 24 24"><rect width="24" height="24" rx="4" fill="#1877F2"/><path fill="#fff" d="M16.6 12H13.8V21H10.4V12H8.4V9H10.4V7.2C10.4 5.3 11.6 3 14.5 3L17.1 3V6.2H15.5C15.2 6.2 14.8 6.4 14.8 7V9H17.1L16.6 12Z"/></svg></a>
    <a href="#" class="social-link" title="Threads" target="_blank" rel="noopener"><svg width="18" height="18" viewBox="0 0 24 24"><rect width="24" height="24" rx="4" fill="#000"/><path fill="none" stroke="#fff" stroke-width="1.3" stroke-linecap="round" d="M16.5 11.3c-.2-1-.7-1.8-1.5-2.4-1-.7-2.2-1-3.5-.9-1.1.1-2 .5-2.7 1.2-.9.9-1.3 2.1-1.3 3.5 0 3 1.9 5 4.8 5.1h.3c1.1 0 2-.2 2.8-.7 1-.6 1.6-1.6 1.6-2.9 0-1-.4-1.9-1.1-2.5.4.5.6 1.1.6 1.8 0 1-.5 1.7-1.3 2.1-.6.3-1.3.4-2.1.4h-.2c-2-.1-3.3-1.4-3.3-3.3 0-.3 0-.6.1-.9.3-1.1 1-1.9 2.2-2.3.7-.3 1.5-.4 2.3-.4h.7c1.2.1 2.2.5 2.9 1.3.5.5.8 1.1 1 1.8"/></svg></a>
    <a href="#" class="social-link" title="TikTok" target="_blank" rel="noopener"><svg width="18" height="18" viewBox="0 0 24 24"><rect width="24" height="24" rx="4" fill="#010101"/><path fill="#fff" d="M17 6.7a4.6 4.6 0 0 1-2.7-.9 4.6 4.6 0 0 1-1.7-2.9H10v8.3l.01 4.5a2.7 2.7 0 0 1-2.7 2.5 2.7 2.7 0 0 1-2.7-2.7 2.7 2.7 0 0 1 2.7-2.7c.3 0 .5 0 .8.1v-2.5a5.5 5.5 0 0 0-.8-.1A5.3 5.3 0 0 0 2 16.7a5.3 5.3 0 0 0 5.3 5.3 5.3 5.3 0 0 0 5.3-5.3v-7a7.3 7.3 0 0 0 4.2 1.3V8.6A4.6 4.6 0 0 1 17 6.7z"/></svg></a>
    <a href="#" class="social-link" title="Substack" target="_blank" rel="noopener"><svg width="18" height="18" viewBox="0 0 24 24"><rect width="24" height="24" rx="4" fill="#FF6719"/><path fill="#fff" d="M19 5.5H5v1.75h14V5.5zm0 3.75H5v1.75h14V9.25zM5 13l7 5 7-5v7.5L12 18l-7 2.5V13z"/></svg></a>
    <a href="#" class="social-link" title="X (Twitter)" target="_blank" rel="noopener"><svg width="18" height="18" viewBox="0 0 24 24"><rect width="24" height="24" rx="4" fill="#000"/><path fill="#fff" d="M17.75 3h3.14l-6.86 7.84 8.06 10.66H16.2l-4.95-6.47-5.66 6.47H2.44l7.34-8.39L1.98 3h6.68l4.47 5.91L17.75 3zm-1.1 16.52h1.74L7.45 4.78H5.59l11.06 14.74z"/></svg></a>
  </div>
  <div class="footer-bottom">&copy; 2025 Rockline AI Marketing · Lockport, IL · All Rights Reserved</div>
</footer>

<!-- ═══════════════════════════════════════════════════════════════
     JAVASCRIPT
     ════════════════════════════════════════════════════════════ -->
<script>
  /* ── Seamless ticker ─────────────────────────────────────────── */
  function initSeamlessTicker(trackEl) {
    if (!trackEl) return;
    Array.from(trackEl.children).forEach(item => trackEl.appendChild(item.cloneNode(true)));
  }
  initSeamlessTicker(document.getElementById('desktopTicker'));
  initSeamlessTicker(document.getElementById('mobileTicker'));

  /* ── Desktop nav dropdowns ───────────────────────────────────── */
  const navItems    = document.querySelectorAll('#sticky-nav-zone .nav-item');
  const closeTimers = new Map();

  navItems.forEach(item => {
    if (!item.querySelector('.dropdown')) return;

    item.addEventListener('mouseenter', () => {
      clearTimeout(closeTimers.get(item));
      navItems.forEach(other => {
        if (other !== item) {
          clearTimeout(closeTimers.get(other));
          other.classList.remove('is-open');
        }
      });
      item.classList.add('is-open');
    });

    item.addEventListener('mouseleave', () => {
      closeTimers.set(item, setTimeout(() => {
        item.classList.remove('is-open');
      }, 200));
    });
  });

  document.addEventListener('click', e => {
    if (!e.target.closest('#sticky-nav-zone .nav-item')) {
      navItems.forEach(item => item.classList.remove('is-open'));
    }
  });

  /* ── Mobile nav ──────────────────────────────────────────────── */
  const hamburgerTrigger = document.getElementById('hamburgerTrigger');
  const mobilePanel      = document.getElementById('mobilePanel');
  const mobileOverlay    = document.getElementById('mobileOverlay');

  function openPanel() {
    mobilePanel.classList.add('open');
    mobileOverlay.classList.add('visible');
    hamburgerTrigger.classList.add('open');
    hamburgerTrigger.setAttribute('aria-label', 'Close navigation');
    document.body.style.overflow = 'hidden';
  }
  function closePanel() {
    mobilePanel.classList.remove('open');
    mobileOverlay.classList.remove('visible');
    hamburgerTrigger.classList.remove('open');
    hamburgerTrigger.setAttribute('aria-label', 'Open navigation');
    document.body.style.overflow = '';
  }
  hamburgerTrigger.addEventListener('click', () =>
    mobilePanel.classList.contains('open') ? closePanel() : openPanel()
  );
  mobileOverlay.addEventListener('click', closePanel);

  function toggleSub(el) {
    const sub    = el.nextElementSibling;
    const isOpen = sub.classList.contains('open');
    document.querySelectorAll('.mobile-sub.open').forEach(s => s.classList.remove('open'));
    document.querySelectorAll('.m-parent.sub-open').forEach(p => p.classList.remove('sub-open'));
    if (!isOpen) { sub.classList.add('open'); el.classList.add('sub-open'); }
  }
</script>
</body>
</html>
