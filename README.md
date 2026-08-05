# Fathi-Rayangga-Lab-1
!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Recuerdame — Latin Restaurant & Table Reservations</title>
<meta name="description" content="Recuerdame, a Latin restaurant with real flavor and a night you'll remember. Book your table now.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,400;0,9..144,600;0,9..144,700;1,9..144,500;1,9..144,600&family=Lora:ital,wght@0,400;0,500;1,400&family=Poppins:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    /* light warm base */
    --paper:#FFFBF2;
    --paper-2:#FFF1D2;
    --ink:#3A160B;
    --ink-soft:#7A5240;

    /* Spanish fiesta accents */
    --red:#E2382E;
    --red-deep:#B71C2B;
    --gold:#FFC53D;
    --gold-bright:#FFDE7A;
    --orange:#F2703C;
    --teal:#1E8C8C;

    /* text on colored / dark blocks */
    --white:#FFFBF2;
    --mist:rgba(255,251,242,0.86);

    --line-light: rgba(58,22,11,0.14);
    --line-dark: rgba(255,251,242,0.3);
    --shadow: 0 20px 46px rgba(58,22,11,0.16);
    --radius: 2px;
  }

  *{box-sizing:border-box; margin:0; padding:0;}
  html{scroll-behavior:smooth;}
  body{
    background:var(--paper);
    color:var(--ink);
    font-family:'Lora', serif;
    line-height:1.65;
    -webkit-font-smoothing:antialiased;
    overflow-x:hidden;
  }
  img,svg{display:block; max-width:100%;}
  a{color:inherit; text-decoration:none;}
  ul{list-style:none;}
  button{font-family:inherit; cursor:pointer;}

  .container{
    width:100%;
    max-width:1120px;
    margin:0 auto;
    padding:0 24px;
  }

  .eyebrow{
    font-family:'Poppins', sans-serif;
    font-size:12px;
    letter-spacing:0.32em;
    text-transform:uppercase;
    color:var(--red-deep);
    font-weight:600;
  }
  .on-color .eyebrow{ color:var(--gold-bright); }

  h1,h2,h3{
    font-family:'Fraunces', serif;
    font-weight:600;
    color:var(--ink);
    letter-spacing:-0.01em;
  }

  .btn{
    display:inline-flex;
    align-items:center;
    gap:10px;
    font-family:'Poppins', sans-serif;
    font-weight:600;
    font-size:14px;
    letter-spacing:0.03em;
    padding:14px 10px 14px 26px;
    border-radius:999px;
    border:1px solid transparent;
    transition:transform .25s ease, box-shadow .25s ease, background .25s ease, color .25s ease;
    white-space:nowrap;
  }
  .btn-icon{
    width:32px; height:32px; border-radius:50%;
    background:var(--red-deep);
    color:var(--gold-bright);
    display:flex; align-items:center; justify-content:center;
    flex-shrink:0;
  }
  .btn-icon svg{ width:15px; height:15px; }
  .btn-primary{
    background:linear-gradient(180deg, var(--gold-bright), var(--gold));
    color:var(--red-deep);
    box-shadow:0 12px 28px rgba(183,28,43,0.28);
  }
  .btn-primary:hover{ transform:translateY(-2px); box-shadow:0 16px 34px rgba(183,28,43,0.36); }
  .btn-square{ border-radius:var(--radius); padding:16px 28px; }
  .btn-square .btn-icon{ display:none; }

  /* ---------- NAV ---------- */
  header{
    position:sticky; top:0; z-index:60;
    background:linear-gradient(115deg, var(--red-deep) 0%, var(--red) 55%, var(--orange) 130%);
    border-bottom:1px solid var(--line-dark);
    overflow:hidden;
  }
  header .nav-texture{
    position:absolute; inset:0; opacity:0.16; pointer-events:none;
    background-image:
      radial-gradient(circle at 78% -40%, transparent 0 78px, var(--gold-bright) 79px, var(--gold-bright) 80px, transparent 81px),
      radial-gradient(circle at 78% -40%, transparent 0 120px, var(--gold-bright) 121px, var(--gold-bright) 122px, transparent 123px),
      radial-gradient(circle at 78% -40%, transparent 0 160px, var(--gold-bright) 161px, var(--gold-bright) 162px, transparent 163px),
      repeating-linear-gradient(115deg, transparent 0 34px, var(--gold-bright) 34px 35px, transparent 35px 68px);
    mix-blend-mode:overlay;
  }
  .nav{
    position:relative;
    display:flex; align-items:center; justify-content:space-between;
    padding:18px 24px;
    gap:20px;
  }
  .logo-mark{ position:relative; display:flex; align-items:center; height:44px; }
  .logo-mark .monogram{
    position:absolute; left:-6px; top:50%; transform:translateY(-52%);
    font-family:'Fraunces', serif;
    font-weight:700;
    font-size:64px;
    color:var(--gold-bright);
    opacity:0.45;
    line-height:1;
    letter-spacing:-6px;
    pointer-events:none;
    user-select:none;
  }
  .logo-mark .wordmark{
    position:relative;
    font-family:'Poppins', sans-serif;
    font-weight:600;
    font-size:14px;
    letter-spacing:0.24em;
    text-transform:uppercase;
    color:var(--white);
    padding-left:34px;
  }
  .logo-mark .wordmark span{ display:block; font-size:10px; letter-spacing:0.3em; color:var(--gold-bright); margin-top:2px;}

  .nav-links{
    display:none;
    align-items:center;
    gap:36px;
    font-family:'Poppins', sans-serif;
    font-size:14px;
    color:var(--mist);
  }
  .nav-links a{ position:relative; padding-bottom:4px; transition:color .2s ease;}
  .nav-links a:hover{ color:var(--gold-bright); }

  .has-dropdown{ position:relative; }
  .drop-btn{
    display:flex; align-items:center; gap:6px;
    background:none; border:none; color:var(--mist);
    font-family:'Poppins', sans-serif; font-size:14px;
    transition:color .2s ease;
  }
  .drop-btn:hover{ color:var(--gold-bright); }
  .drop-btn svg{ width:14px; height:14px; transition:transform .25s ease; }
  .has-dropdown.open .drop-btn svg{ transform:rotate(180deg); }
  .dropdown{
    position:absolute; top:calc(100% + 18px); left:50%; transform:translateX(-50%) translateY(6px);
    background:var(--red-deep); border:1px solid var(--line-dark);
    border-radius:var(--radius);
    min-width:180px;
    padding:10px;
    opacity:0; visibility:hidden;
    transition:opacity .2s ease, transform .2s ease, visibility .2s ease;
    box-shadow:var(--shadow);
  }
  .has-dropdown.open .dropdown{ opacity:1; visibility:visible; transform:translateX(-50%) translateY(0); }
  .dropdown a{
    display:block; padding:9px 12px; font-size:13.5px; color:var(--mist); border-radius:2px;
  }
  .dropdown a:hover{ background:rgba(255,222,122,0.14); color:var(--gold-bright); }

  .nav-cta{ display:none; }

  @media(min-width:900px){
    .nav-links{ display:flex; }
    .nav-cta{ display:inline-flex; }
  }

  /* ---------- HERO ---------- */
  .hero{
    position:relative;
    padding:100px 24px 0;
    text-align:center;
    overflow:hidden;
    background:
      radial-gradient(60% 55% at 50% 10%, rgba(255,222,122,0.35), transparent 65%),
      linear-gradient(160deg, var(--red-deep) 0%, var(--red) 45%, var(--orange) 100%);
  }
  .hero-glow{
    position:absolute; inset:0; pointer-events:none;
    background:radial-gradient(circle at 50% 25%, rgba(255,222,122,0.25), transparent 55%);
    animation:flicker 6s ease-in-out infinite;
  }
  @keyframes flicker{
    0%,100%{ opacity:1; }
    50%{ opacity:0.75; }
  }
  .hero-inner{ position:relative; max-width:760px; margin:0 auto; padding-bottom:70px;}
  .hero .eyebrow{ display:inline-block; margin-bottom:22px; color:var(--gold-bright); }
  .hero h1{
    font-size:clamp(48px, 10vw, 96px);
    font-style:italic;
    line-height:0.95;
    color:var(--white);
    text-shadow:0 2px 40px rgba(0,0,0,0.15);
  }
  .hero h1 span{ color:var(--gold-bright); }
  .hero p.lede{
    font-size:clamp(17px,2.4vw,20px);
    color:var(--mist);
    max-width:520px;
    margin:26px auto 36px;
  }
  .hero-actions{
    display:flex; flex-wrap:wrap; gap:16px; justify-content:center; align-items:center;
  }
  .hero-link{
    font-family:'Poppins', sans-serif;
    font-size:13px; letter-spacing:0.05em; text-transform:uppercase;
    color:var(--mist);
    border-bottom:1px solid var(--line-dark);
    padding-bottom:3px;
    transition:color .2s ease, border-color .2s ease;
  }
  .hero-link:hover{ color:var(--gold-bright); border-color:var(--gold-bright); }

  .scallop{
    width:100%; height:34px; display:block;
    fill:var(--paper-2);
  }

  /* ---------- SECTIONS shared ---------- */
  section{ padding:90px 0; position:relative; }
  .section-head{ text-align:center; max-width:640px; margin:0 auto 56px; }
  .section-head h2{ font-size:clamp(30px,4.4vw,44px); margin-top:14px; }
  .section-head p{ color:var(--ink-soft); margin-top:14px; font-size:16px; }

  /* ---------- FEATURES ---------- */
  .features{ background:var(--paper-2); }
  .feature-grid{
    display:grid; gap:28px;
    grid-template-columns:1fr;
  }
  @media(min-width:760px){ .feature-grid{ grid-template-columns:repeat(3,1fr); } }
  .feature-card{
    border:1px solid var(--line-light);
    background:var(--paper);
    padding:38px 30px;
    box-shadow:0 10px 26px rgba(58,22,11,0.06);
    transition:transform .3s ease, border-color .3s ease, box-shadow .3s ease;
  }
  .feature-card:hover{ transform:translateY(-6px); border-color:var(--red); box-shadow:0 18px 34px rgba(226,56,46,0.14); }
  .feature-icon{
    width:46px; height:46px;
    margin-bottom:22px;
  }
  .feature-card:nth-child(1) .feature-icon{ color:var(--red); }
  .feature-card:nth-child(2) .feature-icon{ color:var(--orange); }
  .feature-card:nth-child(3) .feature-icon{ color:var(--teal); }
  .feature-card h3{ font-size:21px; margin-bottom:12px; }
  .feature-card p{ color:var(--ink-soft); font-size:15px; }

  /* ---------- TESTIMONIALS ---------- */
  .testimoni{ background:var(--paper); }
  .testi-grid{
    display:grid; gap:24px; grid-template-columns:1fr;
  }
  @media(min-width:760px){ .testi-grid{ grid-template-columns:repeat(3,1fr); } }
  .testi-card{
    background:var(--paper-2);
    border:1px solid var(--line-light);
    padding:34px 28px;
    display:flex; flex-direction:column; gap:18px;
  }
  .quote-mark{ width:30px; height:30px; color:var(--red); }
  .testi-card p.quote{ font-style:italic; color:var(--ink); font-size:16px; }
  .testi-who{ display:flex; align-items:center; gap:12px; margin-top:auto; padding-top:8px; border-top:1px solid var(--line-light); }
  .testi-avatar{
    width:38px; height:38px; border-radius:50%;
    background:linear-gradient(135deg, var(--gold), var(--red));
    flex-shrink:0;
  }
  .testi-name{ font-family:'Poppins',sans-serif; font-size:13px; font-weight:600; color:var(--ink); }
  .testi-role{ font-family:'Poppins',sans-serif; font-size:12px; color:var(--ink-soft); }

  /* ---------- MENU BOOK ---------- */
  .harga{ background:var(--paper-2); }
  .menu-book{
    max-width:720px; margin:0 auto;
    border:1px solid var(--line-light);
    background:var(--paper);
    box-shadow:0 14px 34px rgba(58,22,11,0.08);
    padding:8px;
  }
  .menu-tabs{
    display:flex; flex-wrap:wrap; gap:8px;
    padding:14px;
    border-bottom:1px solid var(--line-light);
  }
  .menu-tab{
    background:none; border:1px solid var(--line-light);
    color:var(--ink-soft);
    font-family:'Poppins',sans-serif; font-size:12.5px; letter-spacing:0.06em; text-transform:uppercase;
    padding:9px 16px; border-radius:999px;
    transition:all .2s ease;
  }
  .menu-tab.active{ background:var(--red); border-color:var(--red); color:var(--white); font-weight:600; }
  .menu-tab:hover:not(.active){ border-color:var(--red); color:var(--red); }

  .menu-panel{ display:none; padding:34px 30px 26px; }
  .menu-panel.active{ display:block; }
  .menu-panel-title{
    font-family:'Poppins',sans-serif; font-size:11px; letter-spacing:0.2em; text-transform:uppercase;
    color:var(--red-deep); margin-bottom:20px;
  }
  .menu-item{
    display:flex; align-items:baseline; gap:10px;
    padding:18px 0;
    border-bottom:1px dashed var(--line-light);
  }
  .menu-item:last-child{ border-bottom:none; padding-bottom:0; }
  .menu-name{ font-family:'Fraunces', serif; font-size:19px; color:var(--ink); }
  .menu-desc{ display:block; font-family:'Lora',serif; font-size:13.5px; color:var(--ink-soft); margin-top:4px; font-style:italic;}
  .menu-fill{ flex:1; border-bottom:1px dotted var(--line-light); transform:translateY(-6px); min-width:20px; }
  .menu-price{ font-family:'Poppins',sans-serif; font-weight:700; color:var(--red-deep); font-size:15px; white-space:nowrap; }
  .menu-note{ text-align:center; margin-top:30px; font-size:13px; color:var(--ink-soft); font-family:'Poppins',sans-serif; letter-spacing:0.02em;}

  /* ---------- FAQ ---------- */
  .faq{ background:var(--paper); }
  .faq-list{ max-width:680px; margin:0 auto; }
  .faq-item{ border-bottom:1px solid var(--line-light); }
  .faq-q{
    width:100%; background:none; border:none; text-align:left;
    display:flex; align-items:center; justify-content:space-between;
    padding:24px 4px; color:var(--ink); font-family:'Fraunces',serif; font-size:18px;
    gap:20px;
  }
  .faq-q svg{ width:20px; height:20px; color:var(--red); flex-shrink:0; transition:transform .3s ease; }
  .faq-item.open .faq-q svg{ transform:rotate(45deg); }
  .faq-a{
    max-height:0; overflow:hidden; transition:max-height .35s ease;
    color:var(--ink-soft); font-size:15px;
  }
  .faq-a-inner{ padding:0 4px 24px; max-width:600px; }
  .faq-item.open .faq-a{ max-height:220px; }

  /* ---------- FINAL CTA ---------- */
  .ajakan{
    background:
      radial-gradient(60% 90% at 50% 0%, rgba(255,222,122,0.3), transparent 60%),
      linear-gradient(160deg, var(--orange) 0%, var(--red) 55%, var(--red-deep) 120%);
    text-align:center;
    padding:110px 24px;
  }
  .ajakan .eyebrow{ color:var(--gold-bright); }
  .ajakan h2{ font-size:clamp(32px,5vw,52px); font-style:italic; color:var(--white); }
  .ajakan p{ color:var(--mist); max-width:480px; margin:18px auto 36px; }
  .ajakan-actions{ display:flex; flex-direction:column; gap:16px; align-items:center; }
  .ajakan-phone{ font-family:'Poppins',sans-serif; font-size:13px; color:var(--mist); }
  .ajakan-phone a{ color:var(--gold-bright); border-bottom:1px solid var(--line-dark); }

  /* ---------- FOOTER ---------- */
  footer{ background:#2A0E08; padding:70px 24px 30px; border-top:1px solid var(--line-dark); }
  .footer-grid{
    display:grid; gap:40px; grid-template-columns:1fr;
    padding-bottom:40px;
  }
  @media(min-width:760px){ .footer-grid{ grid-template-columns:1.4fr 1fr 1fr 1fr; } }
  .footer-brand .wordmark{ color:var(--white); }
  .footer-brand p{ color:var(--mist); font-size:14px; margin-top:14px; max-width:280px; }
  .footer-col h4{
    font-family:'Poppins',sans-serif; font-size:12px; text-transform:uppercase;
    letter-spacing:0.12em; color:var(--gold-bright); margin-bottom:16px;
  }
  .footer-col li{ margin-bottom:10px; font-size:14px; color:var(--mist); }
  .footer-col a:hover{ color:var(--gold-bright); }
  .socials{ display:flex; gap:14px; margin-top:16px; }
  .socials a{
    width:36px; height:36px; border:1px solid var(--line-dark); border-radius:50%;
    display:flex; align-items:center; justify-content:center; color:var(--mist);
    transition:border-color .2s ease, color .2s ease;
  }
  .socials a:hover{ border-color:var(--gold); color:var(--gold-bright); }
  .socials svg{ width:16px; height:16px; }
  .footer-bottom{
    padding-top:26px; border-top:1px solid var(--line-dark);
    display:flex; flex-wrap:wrap; gap:10px; justify-content:space-between;
    font-family:'Poppins',sans-serif; font-size:12px; color:rgba(255,251,242,0.55);
  }

  .reveal{ opacity:0; transform:translateY(18px); transition:opacity .7s ease, transform .7s ease; }
  .reveal.in{ opacity:1; transform:translateY(0); }

  @media (prefers-reduced-motion: reduce){
    html{ scroll-behavior:auto; }
    .hero-glow{ animation:none; }
    .reveal{ transition:none; opacity:1; transform:none; }
  }
</style>
</head>
<body>

<header>
  <div class="nav-texture"></div>
  <div class="nav container">
    <a href="#" class="logo-mark">
      <span class="monogram">R</span>
      <span class="wordmark">Recuerdame<span>Latin Kitchen</span></span>
    </a>
    <nav class="nav-links">
      <a href="#home">Home</a>
      <a href="#fitur">About</a>
      <div class="has-dropdown" id="menuDropdown">
        <button class="drop-btn" aria-expanded="false">
          Menu
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M6 9l6 6 6-6"/></svg>
        </button>
        <div class="dropdown">
          <a href="#harga-starters">Starters</a>
          <a href="#harga-mains">Mains</a>
          <a href="#harga-desserts">Desserts</a>
          <a href="#harga-drinks">Drinks</a>
        </div>
      </div>
      <a href="#faq">FAQ</a>
    </nav>
    <a href="#reservasi" class="btn btn-primary nav-cta">
      Book a Table
      <span class="btn-icon">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2"><path d="M7 17L17 7M7 7h10v10"/></svg>
      </span>
    </a>
  </div>
</header>

<main>

  <!-- HERO -->
  <section class="hero on-color" id="home">
    <div class="hero-glow"></div>
    <div class="hero-inner">
      <span class="eyebrow">Latin Restaurant & Bar · Jakarta</span>
      <h1>Recuerda<span>me</span></h1>
      <p class="lede">Every dish is a memory worth celebrating. Come enjoy real Latin American food in a warm room lit by candlelight.</p>
      <div class="hero-actions">
        <a href="#reservasi" class="btn btn-primary btn-square">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><rect x="3" y="5" width="18" height="16" rx="1.5"/><path d="M3 10h18M8 3v4M16 3v4"/><circle cx="12" cy="15" r="2"/></svg>
          Book a Table
        </a>
        <a href="#harga" class="hero-link">See Full Menu →</a>
      </div>
    </div>
    <svg class="scallop" viewBox="0 0 600 34" preserveAspectRatio="none">
      <path d="M0,0 H600 V14 C575,34 550,4 525,14 C500,34 475,4 450,14 C425,34 400,4 375,14 C350,34 325,4 300,14 C275,34 250,4 225,14 C200,34 175,4 150,14 C125,34 100,4 75,14 C50,34 25,4 0,14 Z"/>
    </svg>
  </section>

  <!-- FEATURES -->
  <section class="features" id="fitur">
    <div class="container">
      <div class="section-head reveal">
        <span class="eyebrow">Why Recuerdame</span>
        <h2>A Night You Won't Forget</h2>
        <p>Three things that make every visit feel like a celebration.</p>
      </div>
      <div class="feature-grid">
        <div class="feature-card reveal">
          <svg class="feature-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><path d="M12 2c1.5 3 4 4.5 4 8a4 4 0 0 1-8 0c0-1 .3-1.8.8-2.6C9.5 8.6 10 7.5 10 6c0 1.6-1 2.4-1 4a3 3 0 0 0 3 3"/><path d="M6 21c0-3 2-4 6-4s6 1 6 4"/></svg>
          <h3>Open Fire Kitchen</h3>
          <p>Watch our chefs grill the finest meats over mesquite wood, right at your table.</p>
        </div>
        <div class="feature-card reveal">
          <svg class="feature-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><path d="M9 18V5l11-2v13"/><circle cx="6" cy="18" r="3"/><circle cx="17" cy="16" r="3"/></svg>
          <h3>Live Latin Music</h3>
          <p>Guitar and bolero music fills the room every weekend, played live on our small stage.</p>
        </div>
        <div class="feature-card reveal">
          <svg class="feature-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><path d="M8 3h8l-1 7a3 3 0 0 1-3 3v0a3 3 0 0 1-3-3L8 3Z"/><path d="M12 13v6M9 21h6"/></svg>
          <h3>Wine & Mezcal Bar</h3>
          <p>Let our sommelier guide you through more than 80 wines and mezcals from across Latin America.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- TESTIMONIALS -->
  <section class="testimoni" id="testimoni">
    <div class="container">
      <div class="section-head reveal">
        <span class="eyebrow">What Guests Say</span>
        <h2>Stories From Our Tables</h2>
      </div>
      <div class="testi-grid">
        <div class="testi-card reveal">
          <svg class="quote-mark" viewBox="0 0 24 24" fill="currentColor"><path d="M7 7c-2.5 1.5-4 4-4 7a5 5 0 0 0 5 5h1v-6H7c0-2 1-3.5 3-4.5L9 7Zm9 0c-2.5 1.5-4 4-4 7a5 5 0 0 0 5 5h1v-6h-2c0-2 1-3.5 3-4.5L18 7Z"/></svg>
          <p class="quote">"It feels like coming home to my grandma's kitchen in Oaxaca — warm, honest, and full of love."</p>
          <div class="testi-who">
            <div class="testi-avatar"></div>
            <div>
              <div class="testi-name">Amara S.</div>
              <div class="testi-role">Food Blogger</div>
            </div>
          </div>
        </div>
        <div class="testi-card reveal">
          <svg class="quote-mark" viewBox="0 0 24 24" fill="currentColor"><path d="M7 7c-2.5 1.5-4 4-4 7a5 5 0 0 0 5 5h1v-6H7c0-2 1-3.5 3-4.5L9 7Zm9 0c-2.5 1.5-4 4-4 7a5 5 0 0 0 5 5h1v-6h-2c0-2 1-3.5 3-4.5L18 7Z"/></svg>
          <p class="quote">"The most elegant night out I've had in Jakarta. Perfect service, unforgettable food."</p>
          <div class="testi-who">
            <div class="testi-avatar"></div>
            <div>
              <div class="testi-name">Bimo R.</div>
              <div class="testi-role">Regular Guest</div>
            </div>
          </div>
        </div>
        <div class="testi-card reveal">
          <svg class="quote-mark" viewBox="0 0 24 24" fill="currentColor"><path d="M7 7c-2.5 1.5-4 4-4 7a5 5 0 0 0 5 5h1v-6H7c0-2 1-3.5 3-4.5L9 7Zm9 0c-2.5 1.5-4 4-4 7a5 5 0 0 0 5 5h1v-6h-2c0-2 1-3.5 3-4.5L18 7Z"/></svg>
          <p class="quote">"Recuerdame isn't just a restaurant, it's a celebration. We'll definitely come back."</p>
          <div class="testi-who">
            <div class="testi-avatar"></div>
            <div>
              <div class="testi-name">Clara & Deni</div>
              <div class="testi-role">Anniversary Dinner</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- MENU BOOK -->
  <section class="harga" id="harga">
    <div class="container">
      <div class="section-head reveal">
        <span class="eyebrow">Our Menu Book</span>
        <h2>Simple, Honest, Delicious</h2>
        <p>Pick a category and see what we're serving tonight.</p>
      </div>

      <div class="menu-book reveal">
        <div class="menu-tabs">
          <button class="menu-tab active" data-tab="starters">Starters</button>
          <button class="menu-tab" data-tab="mains">Mains</button>
          <button class="menu-tab" data-tab="desserts">Desserts</button>
          <button class="menu-tab" data-tab="drinks">Drinks</button>
        </div>

        <div class="menu-panel active" id="harga-starters" data-panel="starters">
          <div class="menu-panel-title">Starters</div>
          <div class="menu-item">
            <div>
              <span class="menu-name">Shrimp Ceviche</span>
              <span class="menu-desc">Fresh shrimp, lime, chili, red onion</span>
            </div>
            <span class="menu-fill"></span>
            <span class="menu-price">Rp 145,000</span>
          </div>
          <div class="menu-item">
            <div>
              <span class="menu-name">Beef Empanadas</span>
              <span class="menu-desc">Crispy pastry filled with spiced beef</span>
            </div>
            <span class="menu-fill"></span>
            <span class="menu-price">Rp 95,000</span>
          </div>
        </div>

        <div class="menu-panel" id="harga-mains" data-panel="mains">
          <div class="menu-panel-title">Mains</div>
          <div class="menu-item">
            <div>
              <span class="menu-name">Al Pastor Tacos</span>
              <span class="menu-desc">3 pieces, grilled pork, roasted pineapple</span>
            </div>
            <span class="menu-fill"></span>
            <span class="menu-price">Rp 120,000</span>
          </div>
          <div class="menu-item">
            <div>
              <span class="menu-name">Argentine Churrasco</span>
              <span class="menu-desc">Fire-grilled steak, chimichurri sauce</span>
            </div>
            <span class="menu-fill"></span>
            <span class="menu-price">Rp 320,000</span>
          </div>
          <div class="menu-item">
            <div>
              <span class="menu-name">Paella Valenciana</span>
              <span class="menu-desc">Serves 2, seafood and saffron rice</span>
            </div>
            <span class="menu-fill"></span>
            <span class="menu-price">Rp 410,000</span>
          </div>
        </div>

        <div class="menu-panel" id="harga-desserts" data-panel="desserts">
          <div class="menu-panel-title">Desserts</div>
          <div class="menu-item">
            <div>
              <span class="menu-name">Tres Leches Cake</span>
              <span class="menu-desc">Soft three-milk cake with a touch of cinnamon</span>
            </div>
            <span class="menu-fill"></span>
            <span class="menu-price">Rp 85,000</span>
          </div>
        </div>

        <div class="menu-panel" id="harga-drinks" data-panel="drinks">
          <div class="menu-panel-title">Drinks</div>
          <div class="menu-item">
            <div>
              <span class="menu-name">Rosa Sangria</span>
              <span class="menu-desc">Pitcher, red wine, fresh seasonal fruit</span>
            </div>
            <span class="menu-fill"></span>
            <span class="menu-price">Rp 210,000</span>
          </div>
        </div>
      </div>
      <p class="menu-note reveal">Prices do not include tax and service. Menu items may change with the season.</p>
    </div>
  </section>

  <!-- FAQ -->
  <section class="faq" id="faq">
    <div class="container">
      <div class="section-head reveal">
        <span class="eyebrow">Common Questions</span>
        <h2>Quick FAQ</h2>
      </div>
      <div class="faq-list reveal">
        <div class="faq-item open">
          <button class="faq-q" aria-expanded="true">
            Do I need a reservation?
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 5v14M5 12h14"/></svg>
          </button>
          <div class="faq-a"><div class="faq-a-inner">We recommend booking ahead, especially on weekends. You can book using the button above or call us directly.</div></div>
        </div>
        <div class="faq-item">
          <button class="faq-q" aria-expanded="false">
            Do you have vegetarian options?
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 5v14M5 12h14"/></svg>
          </button>
          <div class="faq-a"><div class="faq-a-inner">Yes, we have vegetarian dishes and can adjust them for special requests or allergies. Just let us know when you book.</div></div>
        </div>
        <div class="faq-item">
          <button class="faq-q" aria-expanded="false">
            Is there a dress code?
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 5v14M5 12h14"/></svg>
          </button>
          <div class="faq-a"><div class="faq-a-inner">We suggest smart casual dress to match our elegant setting. Please avoid flip-flops and plain t-shirts.</div></div>
        </div>
        <div class="faq-item">
          <button class="faq-q" aria-expanded="false">
            How long do you hold my table?
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 5v14M5 12h14"/></svg>
          </button>
          <div class="faq-a"><div class="faq-a-inner">We hold your table for 15 minutes after your booking time. Please call us if you think you'll be late.</div></div>
        </div>
      </div>
    </div>
  </section>

  <!-- FINAL CTA -->
  <section class="ajakan on-color" id="reservasi">
    <span class="eyebrow reveal">Tables Are Limited</span>
    <h2 class="reveal">Make Tonight Memorable</h2>
    <p class="reveal">Tables fill up fast, especially on weekends. Book now and let us serve you a night you'll never forget.</p>
    <div class="ajakan-actions reveal">
      <a href="#" class="btn btn-primary btn-square">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><rect x="3" y="5" width="18" height="16" rx="1.5"/><path d="M3 10h18M8 3v4M16 3v4"/><circle cx="12" cy="15" r="2"/></svg>
        Book a Table Now
      </a>
      <span class="ajakan-phone">or call us at <a href="tel:+622157891234">+62 21 5789 1234</a></span>
    </div>
  </section>

</main>

<footer>
  <div class="container">
    <div class="footer-grid">
      <div class="footer-brand">
        <a href="#" class="logo-mark" style="position:static;">
          <span class="wordmark" style="padding-left:0;">Recuerdame<span>Latin Kitchen</span></span>
        </a>
        <p>A taste that stays, a memory that lasts. A Latin restaurant with soul, in the heart of Jakarta.</p>
        <div class="socials">
          <a href="#" aria-label="Instagram"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><rect x="3" y="3" width="18" height="18" rx="5"/><circle cx="12" cy="12" r="4"/><circle cx="17.5" cy="6.5" r="1"/></svg></a>
          <a href="#" aria-label="WhatsApp"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><path d="M4 20l1.4-4.2A8 8 0 1 1 9 18.6L4 20Z"/></svg></a>
          <a href="#" aria-label="Facebook"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><path d="M14 9h3V6h-3a3 3 0 0 0-3 3v2H8v3h3v6h3v-6h3l1-3h-4V9a1 1 0 0 1 1-1Z"/></svg></a>
        </div>
      </div>
      <div class="footer-col">
        <h4>Address</h4>
        <ul>
          <li>Jl. Cipaduy Swag No. 88</li>
          <li>South Jakarta, 12730</li>
        </ul>
      </div>
      <div class="footer-col">
        <h4>Opening Hours</h4>
        <ul>
          <li>Tue – Fri: 5 PM – 11 PM</li>
          <li>Sat – Sun: 12 PM – 12 AM</li>
          <li>Monday: Closed</li>
        </ul>
      </div>
      <div class="footer-col">
        <h4>Contact</h4>
        <ul>
          <li><a href="tel:+622157891234">+62 13 8987 1234</a></li>
          <li><a href="mailto:hello@recuerdame.id">hello@recuerdame.id</a></li>
          <li><a href="#">@recuerdame.id</a></li>
        </ul>
      </div>
    </div>
    <div class="footer-bottom">
      <span>© 2026 Recuerdame. All rights reserved.</span>
      <span>Made with love and Latin flavor.</span>
    </div>
  </div>
</footer>

<script>
  // Dropdown menu (click to open, closes on outside click)
  var dropdown = document.getElementById('menuDropdown');
  dropdown.querySelector('.drop-btn').addEventListener('click', function(e){
    e.stopPropagation();
    var isOpen = dropdown.classList.toggle('open');
    this.setAttribute('aria-expanded', isOpen);
  });
  document.addEventListener('click', function(){
    dropdown.classList.remove('open');
    dropdown.querySelector('.drop-btn').setAttribute('aria-expanded','false');
  });

  // Menu book tabs
  var tabs = document.querySelectorAll('.menu-tab');
  var panels = document.querySelectorAll('.menu-panel');
  tabs.forEach(function(tab){
    tab.addEventListener('click', function(){
      var target = tab.getAttribute('data-tab');
      tabs.forEach(function(t){ t.classList.remove('active'); });
      panels.forEach(function(p){ p.classList.remove('active'); });
      tab.classList.add('active');
      document.querySelector('.menu-panel[data-panel="'+target+'"]').classList.add('active');
    });
  });

  // Accordion FAQ
  document.querySelectorAll('.faq-item').forEach(function(item){
    var btn = item.querySelector('.faq-q');
    btn.addEventListener('click', function(){
      var isOpen = item.classList.contains('open');
      document.querySelectorAll('.faq-item').forEach(function(i){
        i.classList.remove('open');
        i.querySelector('.faq-q').setAttribute('aria-expanded','false');
      });
      if(!isOpen){
        item.classList.add('open');
        btn.setAttribute('aria-expanded','true');
      }
    });
  });

  // Scroll reveal
  if('IntersectionObserver' in window){
    var io = new IntersectionObserver(function(entries){
      entries.forEach(function(e){
        if(e.isIntersecting){
          e.target.classList.add('in');
          io.unobserve(e.target);
        }
      });
    }, { threshold: 0.15 });
    document.querySelectorAll('.reveal').forEach(function(el){ io.observe(el); });
  } else {
    document.querySelectorAll('.reveal').forEach(function(el){ el.classList.add('in'); });
  }
</script>

</body>
</html>
