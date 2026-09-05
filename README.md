<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Vaxora — Strategy-led marketing agency</title>
<meta name="description" content="Vaxora is a strategy-led creative and marketing partner for brands ready to build, not just launch.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:opsz,wght@12..96,400;12..96,500;12..96,600;12..96,700;12..96,800&family=Archivo:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --ink: #1B1A33;
    --twilight: #26254A;
    --bone: #F2EEE4;
    --mist: #ADA9CC;
    --amber: #F0AA3D;
    --amber-soft: #F5BB5E;
    --jade: #55BFAE;
    --rule: rgba(242, 238, 228, 0.14);
    --rule-strong: rgba(242, 238, 228, 0.34);
    --max-w: 1180px;
    --pad: clamp(1.25rem, 4vw, 3rem);
  }

  * { box-sizing: border-box; }
  html { scroll-behavior: smooth; }

  body {
    margin: 0;
    background: var(--ink);
    color: var(--bone);
    font-family: 'Archivo', sans-serif;
    font-size: 16px;
    line-height: 1.6;
    -webkit-font-smoothing: antialiased;
  }

  h1, h2, h3, h4 {
    font-family: 'Bricolage Grotesque', sans-serif;
    margin: 0;
    color: var(--bone);
  }

  p { margin: 0; }
  a { color: inherit; text-decoration: none; }

  a:focus-visible, button:focus-visible {
    outline: 2px solid var(--amber);
    outline-offset: 3px;
    border-radius: 2px;
  }

  .container {
    max-width: var(--max-w);
    margin-inline: auto;
    padding-inline: var(--pad);
  }

  .section { padding-block: clamp(4rem, 9vw, 7.5rem); }
  .alt { background: var(--twilight); }

  .lede {
    color: var(--mist);
    font-size: clamp(1.05rem, 0.4vw + 1rem, 1.25rem);
  }

  .btn {
    display: inline-block;
    padding: 0.7rem 1.4rem;
    border-radius: 3px;
    font-weight: 600;
    font-size: 0.95rem;
  }

  .btn-primary { background: var(--amber); color: var(--ink); transition: background 0.2s ease; }
  .btn-primary:hover { background: var(--amber-soft); }

  .btn-outline {
    border: 1px solid rgba(242, 238, 228, 0.35);
    color: var(--bone);
    transition: border-color 0.2s ease, background 0.2s ease;
  }
  .btn-outline:hover { border-color: var(--bone); background: rgba(242, 238, 228, 0.06); }

  .link-underline {
    font-weight: 600;
    border-bottom: 1px solid var(--rule-strong);
    padding-bottom: 2px;
    transition: border-color 0.2s ease;
  }
  .link-underline:hover { border-color: var(--bone); }

  .nav {
    position: sticky;
    top: 0;
    z-index: 50;
    background: rgba(27, 26, 51, 0.86);
    backdrop-filter: blur(8px);
    -webkit-backdrop-filter: blur(8px);
    border-bottom: 1px solid var(--rule);
  }

  .nav-inner { display: flex; align-items: center; justify-content: space-between; padding-block: 1.1rem; }
  .logo { font-size: 1.4rem; font-weight: 700; letter-spacing: -0.01em; }

  .nav-links { display: flex; align-items: center; gap: 2.25rem; font-size: 0.95rem; font-weight: 500; }
  .nav-links a:not(.btn) { position: relative; padding-block: 0.25rem; }
  .nav-links a:not(.btn)::after {
    content: '';
    position: absolute;
    left: 0; bottom: 0;
    width: 0; height: 1px;
    background: var(--bone);
    transition: width 0.25s ease;
  }
  .nav-links a:not(.btn):hover::after { width: 100%; }

  .nav-toggle { display: none; flex-direction: column; gap: 5px; background: none; border: none; padding: 8px; cursor: pointer; }
  .nav-toggle span { width: 22px; height: 2px; background: var(--bone); transition: transform 0.2s ease, opacity 0.2s ease; }

  @media (max-width: 760px) {
    .nav-toggle { display: flex; }
    .nav-links {
      position: fixed;
      inset: 62px 0 0 0;
      flex-direction: column;
      align-items: flex-start;
      gap: 1.6rem;
      background: var(--ink);
      padding: 2rem var(--pad);
      transform: translateY(-8px);
      opacity: 0;
      pointer-events: none;
      transition: opacity 0.2s ease, transform 0.2s ease;
    }
    .nav-links.open { opacity: 1; transform: translateY(0); pointer-events: auto; }
    .nav-toggle[aria-expanded="true"] span:nth-child(1) { transform: translateY(7px) rotate(45deg); }
    .nav-toggle[aria-expanded="true"] span:nth-child(2) { opacity: 0; }
    .nav-toggle[aria-expanded="true"] span:nth-child(3) { transform: translateY(-7px) rotate(-45deg); }
  }

  .hero { position: relative; overflow: hidden; padding-block: clamp(5rem, 12vw, 9rem) clamp(4rem, 8vw, 6rem); }

  .hero-glow-1 {
    position: absolute; top: -140px; right: -110px;
    width: 480px; height: 480px;
    background: radial-gradient(circle, rgba(240, 170, 61, 0.26), transparent 70%);
    pointer-events: none;
  }
  .hero-glow-2 {
    position: absolute; bottom: -170px; left: -130px;
    width: 420px; height: 420px;
    background: radial-gradient(circle, rgba(85, 191, 174, 0.18), transparent 70%);
    pointer-events: none;
  }

  .hero-inner { position: relative; max-width: 760px; }

  .hero h1 {
    font-size: clamp(2.4rem, 3.6vw + 1.2rem, 4.5rem);
    font-weight: 700;
    line-height: 1.08;
    letter-spacing: -0.02em;
  }

  .hero .lede { margin-top: 1.75rem; max-width: 46ch; }

  .hero-ctas { margin-top: 2.5rem; display: flex; align-items: center; gap: 2rem; flex-wrap: wrap; }

  .reveal { animation: rise 0.7s cubic-bezier(.2,.7,.3,1) both; }
  .reveal-1 { animation-delay: .05s; }
  .reveal-2 { animation-delay: .18s; }
  .reveal-3 { animation-delay: .3s; }

  @keyframes rise {
    from { opacity: 0; transform: translateY(14px); }
    to { opacity: 1; transform: translateY(0); }
  }

  @media (prefers-reduced-motion: reduce) {
    .reveal { animation: none; opacity: 1; transform: none; }
  }

  .section h2 {
    font-size: clamp(1.7rem, 1.2vw + 1.3rem, 2.35rem);
    font-weight: 600;
    letter-spacing: -0.01em;
    max-width: 20ch;
  }

  .services-list { margin-top: 2.75rem; }
  .service-row {
    display: grid;
    grid-template-columns: minmax(180px, 320px) 1fr;
    gap: 2rem;
    padding-block: 1.6rem;
    border-top: 1px solid var(--rule);
  }
  .services-list .service-row:last-child { border-bottom: 1px solid var(--rule); }
  .service-row h3 { font-size: 1.25rem; font-weight: 600; }
  .service-row p { color: var(--mist); max-width: 52ch; }

  @media (max-width: 640px) {
    .service-row { grid-template-columns: 1fr; gap: 0.5rem; }
  }

  .work-grid { margin-top: 2.75rem; display: grid; grid-template-columns: repeat(12, 1fr); gap: 1.25rem; }

  .work-tile {
    grid-column: span 12;
    border: 1px solid var(--rule);
    border-radius: 4px;
    padding: 2rem;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    min-height: 230px;
    background: var(--twilight);
    transition: border-color 0.2s ease;
  }
  .work-tile:hover { border-color: var(--rule-strong); }

  @media (min-width: 780px) {
    .work-tile:nth-child(1) { grid-column: span 7; min-height: 270px; }
    .work-tile:nth-child(2) { grid-column: span 5; }
    .work-tile:nth-child(3) { grid-column: span 5; }
    .work-tile:nth-child(4) { grid-column: span 7; }
  }

  .work-tag { font-size: 0.85rem; font-weight: 600; color: var(--jade); }
  .work-tile h3 { font-size: 1.5rem; margin-top: 0.6rem; font-weight: 600; }
  .work-tile:hover h3 { text-decoration: underline; text-underline-offset: 4px; text-decoration-color: var(--rule-strong); }

  .work-stat { margin-top: 1.5rem; }
  .work-stat .num {
    display: block;
    font-family: 'Bricolage Grotesque', sans-serif;
    font-size: clamp(2rem, 2vw + 1.5rem, 3rem);
    font-weight: 700;
    color: var(--amber);
    line-height: 1;
  }
  .work-stat .label { display: block; margin-top: 0.4rem; font-size: 0.9rem; color: var(--mist); }

  .about-grid { margin-top: 2.75rem; display: grid; grid-template-columns: 1.1fr 1fr; gap: 3.5rem; }
  .about-col p { margin-top: 1.25rem; color: var(--mist); max-width: 50ch; font-size: 1.05rem; }

  .principle { padding-block: 1.4rem; border-top: 1px solid var(--rule); }
  .principles .principle:last-child { border-bottom: 1px solid var(--rule); }
  .principle h3 { font-size: 1.05rem; font-weight: 600; }
  .principle p { margin-top: 0.45rem; font-size: 0.95rem; color: var(--mist); }

  @media (max-width: 780px) {
    .about-grid { grid-template-columns: 1fr; gap: 2rem; }
  }

  .contact h2 { max-width: 16ch; }
  .contact .lede { margin-top: 1.25rem; max-width: 46ch; }

  .contact-row { margin-top: 2.25rem; display: flex; align-items: center; gap: 2rem; flex-wrap: wrap; }

  .contact-email {
    font-family: 'Bricolage Grotesque', sans-serif;
    font-size: clamp(1.25rem, 1vw + 1rem, 1.6rem);
    font-weight: 600;
    border-bottom: 1px solid var(--rule-strong);
  }
  .contact-email:hover { border-color: var(--bone); }

  .footer { border-top: 1px solid var(--rule); padding-block: 2.5rem; }
  .footer-inner { display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 1.25rem; font-size: 0.9rem; color: var(--mist); }
  .footer-links { display: flex; gap: 1.5rem; }
  .footer-links a:hover { color: var(--bone); }
</style>
</head>
<body>

<header class="nav">
  <div class="container nav-inner">
    <a href="#top" class="logo">Vaxora</a>
    <button class="nav-toggle" aria-expanded="false" aria-controls="nav-links" aria-label="Toggle menu">
      <span></span><span></span><span></span>
    </button>
    <nav class="nav-links" id="nav-links">
      <a href="#services">Services</a>
      <a href="#work">Work</a>
      <a href="#about">About</a>
      <a href="#contact" class="btn btn-outline">Contact</a>
    </nav>
  </div>
</header>

<main>
  <section class="hero" id="top">
    <div class="hero-glow-1"></div>
    <div class="hero-glow-2"></div>
    <div class="container hero-inner">
      <h1 class="reveal reveal-1">Most marketing spends attention.<br>We compound it.</h1>
      <p class="lede reveal reveal-2">Vaxora is a strategy-led creative partner for brands ready to build, not just launch.</p>
      <div class="hero-ctas reveal reveal-3">
        <a href="#contact" class="btn btn-primary">Start a project</a>
        <a href="#work" class="link-underline">See our work</a>
      </div>
    </div>
  </section>

  <section class="section alt" id="services">
    <div class="container">
      <h2>What we do</h2>
      <div class="services-list">
        <div class="service-row">
          <h3>Brand Strategy</h3>
          <p>Positioning, naming, and messaging that give a brand a reason to be chosen.</p>
        </div>
        <div class="service-row">
          <h3>Content &amp; Social</h3>
          <p>Editorial calendars and community management that make a brand worth following.</p>
        </div>
        <div class="service-row">
          <h3>Performance Media</h3>
          <p>Paid search and social campaigns built around one number: return.</p>
        </div>
        <div class="service-row">
          <h3>SEO &amp; Organic Growth</h3>
          <p>Technical and editorial SEO that keeps compounding long after a campaign ends.</p>
        </div>
        <div class="service-row">
          <h3>Web &amp; Product Design</h3>
          <p>Sites and digital products designed to convert, not just to look good.</p>
        </div>
        <div class="service-row">
          <h3>Analytics &amp; Reporting</h3>
          <p>Dashboards and attribution models that show what's actually working.</p>
        </div>
      </div>
    </div>
  </section>

  <section class="section" id="work">
    <div class="container">
      <h2>Selected work</h2>
      <div class="work-grid">
        <div class="work-tile">
          <div>
            <span class="work-tag">Branding</span>
            <h3>Northline Coffee</h3>
          </div>
          <div class="work-stat">
            <span class="num">+64%</span>
            <span class="label">unaided brand recall, six months post-launch</span>
          </div>
        </div>
        <div class="work-tile">
          <div>
            <span class="work-tag">Performance Media</span>
            <h3>Fernweg Travel</h3>
          </div>
          <div class="work-stat">
            <span class="num">3.2×</span>
            <span class="label">return on ad spend</span>
          </div>
        </div>
        <div class="work-tile">
          <div>
            <span class="work-tag">Web Design</span>
            <h3>Arden &amp; Oak</h3>
          </div>
          <div class="work-stat">
            <span class="num">+41%</span>
            <span class="label">checkout conversion rate</span>
          </div>
        </div>
        <div class="work-tile">
          <div>
            <span class="work-tag">Content &amp; Social</span>
            <h3>PulseFit Studio</h3>
          </div>
          <div class="work-stat">
            <span class="num">+128%</span>
            <span class="label">organic engagement in 90 days</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section class="section alt" id="about">
    <div class="container about-grid">
      <div class="about-col">
        <h2>Why Vaxora</h2>
        <p>Vaxora was built on a simple idea: most marketing is optimized for launch day, not for the eighteen months after. We plan every campaign to keep working long after the media budget stops, so growth doesn't reset every quarter.</p>
      </div>
      <div class="principles">
        <div class="principle">
          <h3>Strategy before spend</h3>
          <p>Every channel decision traces back to one positioning idea, not a media plan built first and justified later.</p>
        </div>
        <div class="principle">
          <h3>Senior, not delegated</h3>
          <p>Every account is run by people who've done the job before, with no hand-offs to a junior team once the pitch is won.</p>
        </div>
        <div class="principle">
          <h3>Built to compound</h3>
          <p>We measure a campaign by what's still working a year later, not just by launch-week numbers.</p>
        </div>
      </div>
    </div>
  </section>

  <section class="section contact" id="contact">
    <div class="container">
      <h2>Let's start somewhere.</h2>
      <p class="lede">Tell us about the brand, the goal, and the timeline. We reply within two business days.</p>
      <div class="contact-row">
        <a href="mailto:hello@vaxora.co" class="contact-email">hello@vaxora.co</a>
        <a href="mailto:hello@vaxora.co" class="btn btn-primary">Start a project</a>
      </div>
    </div>
  </section>
</main>

<footer class="footer">
  <div class="container footer-inner">
    <span>© <span id="year"></span> Vaxora. All rights reserved.</span>
    <div class="footer-links">
      <a href="#services">Services</a>
      <a href="#work">Work</a>
      <a href="#about">About</a>
    </div>
  </div>
</footer>

<script>
  var toggle = document.querySelector('.nav-toggle');
  var links = document.getElementById('nav-links');
  toggle.addEventListener('click', function () {
    var open = links.classList.toggle('open');
    toggle.setAttribute('aria-expanded', open);
  });
  links.querySelectorAll('a').forEach(function (a) {
    a.addEventListener('click', function () {
      links.classList.remove('open');
      toggle.setAttribute('aria-expanded', 'false');
    });
  });
  document.getElementById('year').textContent = new Date().getFullYear();
</script>

</body>
</html>
