<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Redeemed & Cleaned | Home Cleaning & Organization</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Lato:wght@300;400;600&display=swap" rel="stylesheet">
<script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@4/dist/email.min.js"></script>
<style>
  *{margin:0;padding:0;box-sizing:border-box}
  :root{--gold:#d4a843;--dark:#1b4332;--light:#f0f7f4;--white:#fff;--muted:#74a98a;--text:#3a5a47}
  html{scroll-behavior:smooth}
  body{font-family:'Lato',sans-serif;color:var(--dark);background:var(--white)}

  nav{position:fixed;top:0;width:100%;background:rgba(255,255,255,0.97);z-index:100;border-bottom:1px solid #ede8e1;padding:0 5%}
  .nav-inner{max-width:1100px;margin:0 auto;display:flex;align-items:center;justify-content:space-between;height:64px}
  .nav-logo{font-family:'Playfair Display',serif;font-size:1.1rem;color:var(--dark)}
  .nav-logo span{font-style:italic;color:var(--gold)}
  .nav-links{display:flex;gap:28px;list-style:none}
  .nav-links a{font-size:0.75rem;letter-spacing:2px;text-transform:uppercase;text-decoration:none;color:var(--muted);font-weight:600;transition:color .2s}
  .nav-links a:hover{color:var(--gold)}
  .nav-cta{background:var(--dark);color:var(--white)!important;padding:8px 18px;border-radius:3px}
  .nav-cta:hover{background:var(--gold)!important}
  .hamburger{display:none;flex-direction:column;gap:5px;cursor:pointer;padding:4px}
  .hamburger span{width:22px;height:2px;background:var(--dark);border-radius:2px}
  .mobile-menu{display:none;position:fixed;top:64px;left:0;width:100%;background:var(--white);border-bottom:1px solid #ede8e1;padding:20px 5%;z-index:99}
  .mobile-menu a{display:block;font-size:0.85rem;letter-spacing:2px;text-transform:uppercase;text-decoration:none;color:var(--dark);padding:12px 0;border-bottom:1px solid #f0ece7;font-weight:600}
  @media(max-width:680px){.nav-links{display:none}.hamburger{display:flex}}

  .hero{min-height:100vh;background:linear-gradient(160deg,#0d2b1f 0%,#1b4332 50%,#2d6a4f 100%);display:flex;align-items:center;justify-content:center;text-align:center;padding:100px 5% 60px;position:relative;overflow:hidden}
  .hero::before{content:'';position:absolute;inset:0;background:url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none'%3E%3Cg fill='%23b5956a' fill-opacity='0.04'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E")}
  .hero-content{position:relative;max-width:700px}
  .hero-badge{display:inline-block;font-size:0.65rem;letter-spacing:4px;text-transform:uppercase;color:var(--gold);border:1px solid rgba(181,149,106,0.4);padding:6px 16px;border-radius:20px;margin-bottom:24px}
  .hero h1{font-family:'Playfair Display',serif;font-size:clamp(2.4rem,6vw,4rem);color:var(--white);line-height:1.15;margin-bottom:20px}
  .hero h1 em{font-style:italic;color:var(--gold)}
  .hero p{font-size:1rem;color:rgba(255,255,255,0.7);line-height:1.8;margin-bottom:36px;max-width:520px;margin-left:auto;margin-right:auto}
  .hero-btns{display:flex;gap:14px;justify-content:center;flex-wrap:wrap}
  .btn-primary{background:var(--gold);color:var(--white);padding:14px 32px;border-radius:3px;text-decoration:none;font-size:0.75rem;letter-spacing:2px;text-transform:uppercase;font-weight:600;transition:.2s}
  .btn-primary:hover{opacity:.88}
  .btn-outline{border:1px solid rgba(255,255,255,0.35);color:var(--white);padding:14px 32px;border-radius:3px;text-decoration:none;font-size:0.75rem;letter-spacing:2px;text-transform:uppercase;font-weight:600;transition:.2s}
  .btn-outline:hover{border-color:var(--gold);color:var(--gold)}

  section{padding:80px 5%}
  .section-inner{max-width:1100px;margin:0 auto}
  .section-label{font-size:0.68rem;letter-spacing:4px;text-transform:uppercase;color:var(--gold);margin-bottom:12px}
  .section-title{font-family:'Playfair Display',serif;font-size:clamp(1.6rem,3vw,2.2rem);color:var(--dark);margin-bottom:16px}
  .section-sub{font-size:0.9rem;color:var(--text);line-height:1.8;max-width:560px}
  .divider-gold{display:flex;align-items:center;gap:12px;margin:20px 0 48px}
  .divider-gold::before,.divider-gold::after{content:'';flex:1;height:1px}
  .divider-gold::before{background:linear-gradient(to right,var(--gold),transparent)}
  .divider-gold::after{background:linear-gradient(to left,var(--gold),transparent)}
  .divider-gold span{color:var(--gold);font-size:0.7rem}

  #about{background:var(--light)}
  .about-grid{display:grid;grid-template-columns:1fr 1fr;gap:60px;align-items:center}
  @media(max-width:700px){.about-grid{grid-template-columns:1fr}}
  .about-values{display:grid;grid-template-columns:1fr 1fr;gap:16px;margin-top:32px}
  .value-card{background:var(--white);border-radius:6px;padding:20px;border-left:3px solid var(--gold)}
  .value-card h4{font-family:'Playfair Display',serif;font-size:0.95rem;color:var(--dark);margin-bottom:6px}
  .value-card p{font-size:0.78rem;color:var(--text);line-height:1.6}
  .about-img-box{background:linear-gradient(135deg,#1b4332,#2d6a4f);border-radius:8px;padding:48px 36px;text-align:center;color:var(--white)}
  .about-icon-wrap{margin-bottom:20px}
  .about-icon-wrap svg{width:48px;height:48px;fill:var(--gold)}
  .about-img-box h3{font-family:'Playfair Display',serif;font-size:1.4rem;margin-bottom:12px}
  .about-img-box p{font-size:0.83rem;line-height:1.8;color:rgba(255,255,255,0.75)}
  .about-tagline{margin-top:24px;border-top:1px solid rgba(181,149,106,0.3);padding-top:20px;font-family:'Playfair Display',serif;font-style:italic;font-size:0.85rem;color:var(--gold)}

  #pricing{background:var(--white)}
  .pricing-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:24px}
  .price-card{border-radius:8px;border:1px solid #ede8e1;padding:32px 26px;display:flex;flex-direction:column;position:relative;transition:.2s}
  .price-card:hover{box-shadow:0 6px 30px rgba(0,0,0,0.08);transform:translateY(-3px)}
  .price-card.popular{border-color:var(--gold);box-shadow:0 4px 24px rgba(181,149,106,0.15)}
  .popular-badge{position:absolute;top:-1px;right:20px;background:var(--gold);color:var(--white);font-size:0.62rem;letter-spacing:2px;text-transform:uppercase;padding:4px 12px;border-radius:0 0 6px 6px;font-weight:700}
  .price-icon{margin-bottom:14px}
  .price-icon svg{width:32px;height:32px;stroke:var(--gold);fill:none;stroke-width:1.5;stroke-linecap:round;stroke-linejoin:round}
  .price-name{font-family:'Playfair Display',serif;font-size:1.2rem;font-weight:700;color:var(--dark)}
  .price-tag-line{font-size:0.68rem;letter-spacing:2px;text-transform:uppercase;color:var(--gold);margin:3px 0 14px}
  .price-amount{font-size:1.9rem;font-weight:700;color:var(--dark);line-height:1}
  .price-amount sup{font-size:1rem;vertical-align:super}
  .price-amount small{font-size:0.82rem;font-weight:400;color:var(--muted)}
  .price-note{font-size:0.7rem;color:var(--muted);margin:4px 0 16px}
  .price-divider{height:1px;background:linear-gradient(to right,transparent,#ddd6cc,transparent);margin:16px 0}
  .price-desc{font-size:0.82rem;color:var(--text);line-height:1.7;margin-bottom:16px}
  .price-includes{list-style:none;flex:1}
  .price-includes li{font-size:0.78rem;color:var(--text);padding:5px 0;border-bottom:1px solid #f5f2ee;display:flex;gap:8px;line-height:1.5}
  .price-includes li:last-child{border-bottom:none}
  .price-includes li::before{content:'–';color:var(--gold);font-weight:700;flex-shrink:0}

  #addons{background:var(--light)}
  .addons-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:16px}
  .addon-card{background:var(--white);border-radius:6px;padding:18px;display:flex;justify-content:space-between;align-items:center;border:1px solid #ede8e1}
  .addon-name{font-size:0.85rem;font-weight:600;color:var(--dark);margin-bottom:3px}
  .addon-desc{font-size:0.72rem;color:var(--muted)}
  .addon-price{font-size:1rem;font-weight:700;color:var(--gold);white-space:nowrap;margin-left:12px}

  .recurring-section{margin-top:60px;background:#1b4332;border-radius:10px;padding:40px;text-align:center}
  .recurring-section h3{font-family:'Playfair Display',serif;color:var(--white);font-size:1.4rem;margin-bottom:8px}
  .recurring-section p{color:rgba(255,255,255,0.65);font-size:0.85rem;margin-bottom:28px}
  .recurring-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(140px,1fr));gap:16px;max-width:700px;margin:0 auto}
  .rec-card{background:rgba(255,255,255,0.07);border-radius:6px;padding:18px 12px;text-align:center}
  .rec-card strong{display:block;font-size:1.3rem;color:var(--gold);margin-bottom:4px}
  .rec-card em{display:block;color:var(--white);font-style:normal;font-size:0.82rem;font-weight:600;margin-bottom:2px}
  .rec-card span{color:rgba(255,255,255,0.5);font-size:0.72rem}

  #contact{background:var(--white)}
  .contact-grid{display:grid;grid-template-columns:1fr 1.6fr;gap:60px;align-items:start}
  @media(max-width:760px){.contact-grid{grid-template-columns:1fr}}
  .contact-info h3{font-family:'Playfair Display',serif;font-size:1.3rem;color:var(--dark);margin-bottom:14px}
  .contact-info p{font-size:0.85rem;color:var(--text);line-height:1.8;margin-bottom:24px}
  .contact-detail{display:flex;align-items:center;gap:12px;margin-bottom:14px;font-size:0.83rem;color:var(--text)}
  .contact-detail .icon{width:36px;height:36px;background:var(--light);border-radius:50%;display:flex;align-items:center;justify-content:center;flex-shrink:0}
  .contact-detail .icon svg{width:16px;height:16px;stroke:var(--gold);fill:none;stroke-width:1.8;stroke-linecap:round;stroke-linejoin:round}
  .contact-promise{background:var(--light);border-radius:6px;padding:18px;margin-top:28px;font-size:0.78rem;color:var(--text);line-height:1.7;border-left:3px solid var(--gold)}
  .contact-promise strong{color:var(--dark)}

  .form-card{background:var(--light);border-radius:8px;padding:36px}
  .form-row{display:grid;grid-template-columns:1fr 1fr;gap:16px}
  @media(max-width:500px){.form-row{grid-template-columns:1fr}}
  .form-group{margin-bottom:18px}
  label{font-size:0.7rem;letter-spacing:1.5px;text-transform:uppercase;color:var(--dark);font-weight:700;display:block;margin-bottom:6px}
  input,select,textarea{width:100%;padding:11px 14px;border:1px solid #ddd6cc;border-radius:4px;font-size:0.85rem;color:var(--dark);background:var(--white);font-family:'Lato',sans-serif;outline:none;transition:border .2s}
  input:focus,select:focus,textarea:focus{border-color:var(--gold)}
  textarea{min-height:90px;resize:vertical}
  .checkbox-group{display:flex;flex-direction:column;gap:8px;background:var(--white);border:1px solid #ddd6cc;border-radius:4px;padding:14px}
  .checkbox-group label{font-size:0.82rem;letter-spacing:0;text-transform:none;font-weight:400;display:flex;align-items:center;gap:8px;cursor:pointer;color:var(--text)}
  .checkbox-group label input[type=checkbox]{width:15px;height:15px;accent-color:var(--gold);flex-shrink:0}
  .form-submit{width:100%;padding:14px;background:var(--dark);color:var(--white);border:none;border-radius:4px;font-size:0.75rem;letter-spacing:2.5px;text-transform:uppercase;font-weight:700;cursor:pointer;transition:.2s;font-family:'Lato',sans-serif;margin-top:6px}
  .form-submit:hover{background:var(--gold)}
  .form-submit:disabled{background:#ccc;cursor:not-allowed}
  .form-note{font-size:0.72rem;color:var(--muted);text-align:center;margin-top:10px}
  .success-msg{display:none;background:#f0f8f2;border:1px solid #a8d5b5;border-radius:6px;padding:24px;text-align:center;margin-top:16px}
  .success-msg h4{color:#3a7a50;font-family:'Playfair Display',serif;font-size:1.2rem;margin-bottom:8px}
  .success-msg p{font-size:0.85rem;color:#5a7a65;line-height:1.7}
  .error-msg{display:none;background:#fff0f0;border:1px solid #f5c1c1;border-radius:6px;padding:16px;text-align:center;margin-top:12px;font-size:0.82rem;color:#a33}

  footer{background:var(--dark);color:rgba(255,255,255,0.6);text-align:center;padding:36px 5%}
  .foot-logo{font-family:'Playfair Display',serif;font-size:1.2rem;color:var(--white);margin-bottom:8px}
  .foot-logo span{font-style:italic;color:var(--gold)}
  footer p{font-size:0.75rem;margin-top:6px}
  .foot-careers{display:inline-block;margin-top:14px;font-size:0.7rem;letter-spacing:2px;text-transform:uppercase;color:var(--gold);text-decoration:none;border:1px solid rgba(212,168,67,0.35);padding:6px 18px;border-radius:3px;transition:.2s}
  .foot-careers:hover{background:var(--gold);color:var(--dark)}
</style>
</head>
<body>

<nav>
  <div class="nav-inner">
    <div class="nav-logo" onclick="showMain();window.scrollTo(0,0);" style="cursor:pointer">Redeemed <span>&</span> Cleaned</div>
    <ul class="nav-links">
      <li><a href="#about" onclick="showMain()">About</a></li>
      <li><a href="#pricing" onclick="showMain()">Services</a></li>
      <li><a href="#addons" onclick="showMain()">Add-Ons</a></li>
      <li><a href="#" onclick="showCareers();return false;">Careers</a></li>
      <li><a href="#contact" class="nav-cta" onclick="showMain()">Get a Quote</a></li>
    </ul>
    <div class="hamburger" onclick="toggleMenu()">
      <span></span><span></span><span></span>
    </div>
  </div>
</nav>
<div class="mobile-menu" id="mobileMenu">
  <a href="#about" onclick="showMain();toggleMenu()">About</a>
  <a href="#pricing" onclick="showMain();toggleMenu()">Services</a>
  <a href="#addons" onclick="showMain();toggleMenu()">Add-Ons</a>
  <a href="#" onclick="showCareers();toggleMenu();return false;">Careers</a>
  <a href="#contact" onclick="showMain();toggleMenu()">Get a Quote</a>
</div>

<section class="hero" id="home">
  <div class="hero-content">
    <div class="hero-badge">Residential Cleaning &amp; Organization</div>
    <h1>A Clean Home.<br>A <em>Restored</em> Space.</h1>
    <p>Professional home cleaning, deep cleaning, organization, and decluttering services — done with integrity, care, and attention to every detail.</p>
    <div class="hero-btns">
      <a href="#pricing" class="btn-primary" onclick="showMain()">View Services</a>
      <a href="#contact" class="btn-outline" onclick="showMain()">Request a Quote</a>
    </div>
  </div>
</section>

<section id="about">
  <div class="section-inner">
    <div class="about-grid">
      <div>
        <div class="section-label">Who We Are</div>
        <h2 class="section-title">Cleaning With Purpose &amp; Grace</h2>
        <div class="divider-gold"><span>&#10022;</span></div>
        <p class="section-sub">Redeemed &amp; Cleaned is a residential cleaning and organization service rooted in integrity, excellence, and genuine care for every home we enter. We treat your home as if it were our own.</p>
        <p style="font-size:0.85rem;color:var(--text);line-height:1.8;margin-top:16px">Whether you need a regular maintenance clean, a deep refresh, help decluttering, or a fresh start with a move-in/move-out clean — we show up on time, work hard, and leave your home transformed.</p>
        <div class="about-values">
          <div class="value-card"><h4>Integrity</h4><p>We work honestly in every home, respecting your space and your trust.</p></div>
          <div class="value-card"><h4>Excellence</h4><p>We don't cut corners. Every visit is done with care and attention to detail.</p></div>
          <div class="value-card"><h4>Reliability</h4><p>Consistent, dependable service you can count on every single time.</p></div>
          <div class="value-card"><h4>Care</h4><p>We treat every home with the same pride and respect as our own.</p></div>
        </div>
      </div>
      <div class="about-img-box">
        <div class="about-icon-wrap">
          <svg viewBox="0 0 48 48" xmlns="http://www.w3.org/2000/svg">
            <path d="M6 20L24 6l18 14v22H30V28H18v14H6z" stroke="#b5956a" stroke-width="2" fill="none" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </div>
        <h3>Serving Your Home<br>With a Caring Heart</h3>
        <p>We believe a clean, ordered home is a gift to your family. Every room we clean is approached with purpose, pride, and a genuine desire to make your life easier.</p>
        <div class="about-tagline">"A place for everything, and everything in its place."</div>
      </div>
    </div>
  </div>
</section>

<section id="pricing">
  <div class="section-inner">
    <div class="section-label">Our Services</div>
    <h2 class="section-title">Honest Pricing, Quality Work</h2>
    <div class="divider-gold"><span>&#10022;</span></div>
    <div class="pricing-grid">

      <div class="price-card">
        <div class="price-icon">
          <svg viewBox="0 0 24 24"><path d="M3 9l9-7 9 7v11a2 2 0 01-2 2H5a2 2 0 01-2-2z"/><polyline points="9 22 9 12 15 12 15 22"/></svg>
        </div>
        <div class="price-name">The Grace Clean</div>
        <div class="price-tag-line">Essential Maintenance</div>
        <div class="price-amount"><sup>$</sup>60 <small>– $100</small></div>
        <div class="price-note">Per visit &middot; up to 1,500 sq ft</div>
        <div class="price-divider"></div>
        <p class="price-desc">A faithful, consistent clean for homes that need regular upkeep. Perfect for weekly or biweekly clients who want a fresh, tidy home maintained with care and reliability.</p>
        <ul class="price-includes">
          <li>Kitchen surfaces, sink &amp; appliance exteriors</li>
          <li>Bathroom sanitizing &amp; scrubbing</li>
          <li>Vacuuming &amp; mopping all floors</li>
          <li>Dusting surfaces &amp; ceiling fans</li>
          <li>Trash removal throughout home</li>
          <li>Bed making (linens provided by client)</li>
        </ul>
      </div>

      <div class="price-card popular">
        <div class="popular-badge">Most Popular</div>
        <div class="price-icon">
          <svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="10"/><path d="M8 12l3 3 5-5"/></svg>
        </div>
        <div class="price-name">The Redeemed Clean</div>
        <div class="price-tag-line">Deep Refresh</div>
        <div class="price-amount"><sup>$</sup>140 <small>– $220</small></div>
        <div class="price-note">Per visit &middot; up to 2,000 sq ft</div>
        <div class="price-divider"></div>
        <p class="price-desc">A thorough, top-to-bottom transformation for homes that need more than surface care. Ideal for first-time clients, seasonal refreshes, or homes needing extra attention.</p>
        <ul class="price-includes">
          <li>Everything in The Grace Clean</li>
          <li>Inside oven &amp; microwave</li>
          <li>Baseboards, door frames &amp; light switches</li>
          <li>Window sills &amp; interior window cleaning</li>
          <li>Cabinet fronts &amp; drawer exteriors</li>
        </ul>
      </div>

      <div class="price-card">
        <div class="price-icon">
          <svg viewBox="0 0 24 24"><rect x="3" y="3" width="7" height="7"/><rect x="14" y="3" width="7" height="7"/><rect x="14" y="14" width="7" height="7"/><rect x="3" y="14" width="7" height="7"/></svg>
        </div>
        <div class="price-name">The Restored Home</div>
        <div class="price-tag-line">Organization &amp; Declutter</div>
        <div class="price-amount"><sup>$</sup>180 <small>– $300</small></div>
        <div class="price-note">Per session &middot; 3–5 hours</div>
        <div class="price-divider"></div>
        <p class="price-desc">More than clean — this is a full reset. We bring peace and order to overwhelmed spaces, helping families reclaim their home through thoughtful decluttering and intentional organization.</p>
        <ul class="price-includes">
          <li>Full room organization (closets, pantry, etc.)</li>
          <li>Decluttering &amp; sorting system</li>
          <li>Donation bag prep &amp; coordination</li>
          <li>Organized storage &amp; categorized systems</li>
          <li>Kitchen pantry or cabinet overhaul</li>
          <li>Before &amp; after photo documentation</li>
        </ul>
      </div>

      <div class="price-card">
        <div class="price-icon">
          <svg viewBox="0 0 24 24"><path d="M5 12H3l9-9 9 9h-2"/><path d="M5 12v7a2 2 0 002 2h10a2 2 0 002-2v-7"/><path d="M10 22v-6h4v6"/></svg>
        </div>
        <div class="price-name">Move-In / Move-Out</div>
        <div class="price-tag-line">Fresh Start Clean</div>
        <div class="price-amount"><sup>$</sup>200 <small>– $350</small></div>
        <div class="price-note">Flat rate &middot; based on sq ft</div>
        <div class="price-divider"></div>
        <p class="price-desc">Starting fresh or leaving well — this package ensures every inch is spotless for the next chapter. Great for renters, homeowners, and local landlords beginning or ending a lease.</p>
        <ul class="price-includes">
          <li>Full deep clean of entire home</li>
          <li>Inside all cabinets, drawers &amp; closets</li>
          <li>Appliances cleaned inside &amp; out</li>
          <li>Walls spot-cleaned &amp; baseboards detailed</li>
          <li>Garage sweep (if applicable)</li>
          <li>Bathroom &amp; kitchen sanitized thoroughly</li>
          <li>Certificate of clean available on request</li>
        </ul>
      </div>

    </div>

    <div class="recurring-section">
      <h3>Recurring Client Savings</h3>
      <p>Commit to regular service and save on every visit.</p>
      <div class="recurring-grid">
        <div class="rec-card"><strong>5% off</strong><em>Monthly</em><span>1&times; per month</span></div>
        <div class="rec-card"><strong>10% off</strong><em>Biweekly</em><span>2&times; per month</span></div>
        <div class="rec-card"><strong>15% off</strong><em>Weekly</em><span>Every week</span></div>
        <div class="rec-card"><strong>$20 off</strong><em>Referral</em><span>Per new client referred</span></div>
      </div>
    </div>
  </div>
</section>

<section id="addons">
  <div class="section-inner">
    <div class="section-label">Customize Your Clean</div>
    <h2 class="section-title">Optional Add-Ons</h2>
    <div class="divider-gold"><span>&#10022;</span></div>
    <p class="section-sub" style="margin-bottom:32px">Enhance any package with these individual add-on services. Just check them off when you submit your request.</p>
    <div class="addons-grid">
      <div class="addon-card"><div><div class="addon-name">Interior Windows</div><div class="addon-desc">Full home window cleaning inside</div></div><div class="addon-price">+$25</div></div>
      <div class="addon-card"><div><div class="addon-name">Oven Deep Clean</div><div class="addon-desc">Interior oven scrub &amp; degrease</div></div><div class="addon-price">+$30</div></div>
      <div class="addon-card" style="grid-column:1/-1;background:#f0f7f4;border-color:var(--gold)"><div><div class="addon-name" style="color:var(--dark)">&#10022; Included in The Redeemed Clean</div><div class="addon-desc" style="font-size:0.75rem">Interior Windows and Oven Deep Clean are already included at no extra charge with The Redeemed Clean package.</div></div></div>
      <div class="addon-card"><div><div class="addon-name">Refrigerator Deep Clean</div><div class="addon-desc">Full interior scrub &amp; wipe-down</div></div><div class="addon-price">+$30</div></div>
      <div class="addon-card"><div><div class="addon-name">Single Room Organization</div><div class="addon-desc">One closet, pantry, or bedroom</div></div><div class="addon-price">+$50</div></div>
      <div class="addon-card"><div><div class="addon-name">Patio / Porch Sweep</div><div class="addon-desc">Sweep, wipe furniture &amp; tidy</div></div><div class="addon-price">+$20</div></div>
      <div class="addon-card"><div><div class="addon-name">Laundry — Fold &amp; Organize</div><div class="addon-desc">Fold and organize one full load</div></div><div class="addon-price">+$30</div></div>
    </div>
  </div>
</section>

<section id="contact">
  <div class="section-inner">
    <div class="contact-grid">
      <div class="contact-info">
        <div class="section-label">Get In Touch</div>
        <h2 class="section-title">Request a Quote</h2>
        <div class="divider-gold" style="margin-bottom:24px"><span>&#10022;</span></div>
        <p>Fill out the form and we'll get back to you within 24 hours with a custom quote based on your home and needs. No obligation — just honest conversation.</p>
        <div class="contact-detail">
          <div class="icon"><svg viewBox="0 0 24 24"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg></div>
          <div>alissahicks@redeemedandcleaned.com</div>
        </div>
        <div class="contact-detail">
          <div class="icon"><svg viewBox="0 0 24 24"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0118 0z"/><circle cx="12" cy="10" r="3"/></svg></div>
          <div>Proudly serving Carlinville, IL &amp; surrounding areas</div>
        </div>
        <div class="contact-detail">
          <div class="icon"><svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/></svg></div>
          <div>Mon – Fri &nbsp;&middot;&nbsp; 8:00am – 4:00pm</div>
        </div>
        <div class="contact-promise">
          <strong>Our Promise:</strong> We enter every home with honesty, integrity, and a genuine desire to serve. Your space and your trust are safe with us.
        </div>
      </div>

      <div class="form-card">
        <form id="quoteForm" onsubmit="submitForm(event)">
          <div class="form-row">
            <div class="form-group"><label>First Name *</label><input type="text" id="firstName" required placeholder="Jane"></div>
            <div class="form-group"><label>Last Name *</label><input type="text" id="lastName" required placeholder="Smith"></div>
          </div>
          <div class="form-row">
            <div class="form-group"><label>Phone *</label><input type="tel" id="phone" required placeholder="(555) 000-0000"></div>
            <div class="form-group"><label>Email</label><input type="email" id="email" placeholder="jane@email.com"></div>
          </div>
          <div class="form-group"><label>Your Address / City *</label><input type="text" id="address" required placeholder="123 Main St, Your Town"></div>
          <div class="form-row">
            <div class="form-group">
              <label>Home Size</label>
              <select id="homeSize">
                <option value="">Select range</option>
                <option>Under 1,000 sq ft</option>
                <option>1,000 – 1,500 sq ft</option>
                <option>1,500 – 2,000 sq ft</option>
                <option>2,000 – 2,500 sq ft</option>
                <option>2,500+ sq ft</option>
              </select>
            </div>
            <div class="form-group">
              <label>Bedrooms</label>
              <select id="bedrooms">
                <option value="">Select</option>
                <option>1</option><option>2</option><option>3</option>
                <option>4</option><option>5</option><option>6+</option>
              </select>
            </div>
          </div>
          <div class="form-row">
            <div class="form-group">
              <label>Bathrooms</label>
              <select id="bathrooms">
                <option value="">Select</option>
                <option>1</option><option>2</option><option>3</option>
                <option>4</option><option>5</option>
              </select>
            </div>
            <div class="form-group">
              <label>Pets in the Home?</label>
              <select id="pets">
                <option value="">Select one</option>
                <option>No pets</option>
                <option>Dogs</option><option>Cats</option>
                <option>Dogs &amp; Cats</option><option>Other</option>
              </select>
            </div>
          </div>
          <div class="form-group">
            <label>Service Interested In *</label>
            <select id="service" required>
              <option value="">Select a service</option>
              <option>The Grace Clean — Maintenance ($60–$100)</option>
              <option>The Redeemed Clean — Deep Refresh ($140–$220)</option>
              <option>The Restored Home — Organization ($180–$300)</option>
              <option>Move-In / Move-Out Clean ($200–$350)</option>
              <option>Not sure yet — need a recommendation</option>
            </select>
          </div>
          <div class="form-group">
            <label>How Often?</label>
            <select id="frequency">
              <option value="">Select one</option>
              <option>One-time only</option>
              <option>Monthly</option>
              <option>Biweekly</option>
              <option>Weekly</option>
              <option>Not sure yet</option>
            </select>
          </div>
          <div class="form-group">
            <label>Optional Add-Ons</label>
            <div class="checkbox-group">
              <label><input type="checkbox" class="addon" value="Interior Windows (+$25)"> Interior Windows (+$25)</label>
              <label><input type="checkbox" class="addon" value="Oven Deep Clean (+$30)"> Oven Deep Clean (+$30)</label>
              <label><input type="checkbox" class="addon" value="Refrigerator Deep Clean (+$30)"> Refrigerator Deep Clean (+$30)</label>
              <label><input type="checkbox" class="addon" value="Single Room Organization (+$50)"> Single Room Organization (+$50)</label>
              <label><input type="checkbox" class="addon" value="Patio / Porch Sweep (+$20)"> Patio / Porch Sweep (+$20)</label>
              <label><input type="checkbox" class="addon" value="Laundry Fold & Organize (+$30)"> Laundry — Fold &amp; Organize (+$30)</label>
            </div>
            <p style="font-size:0.72rem;color:var(--muted);margin-top:8px;font-style:italic">&#10022; Interior Windows and Oven Deep Clean are included with The Redeemed Clean — no need to select them separately.</p>
          </div>
          <div class="form-group">
            <label>Special Instructions / Notes</label>
            <textarea id="notes" placeholder="Allergies, sensitivities, areas of focus, access instructions..."></textarea>
          </div>
          <div class="form-group">
            <label>How Did You Hear About Us?</label>
            <input type="text" id="referral" placeholder="e.g. referred by a friend, Facebook, word of mouth...">
          </div>
          <button type="submit" class="form-submit" id="submitBtn">Send My Quote Request</button>
          <p class="form-note">We'll be in touch with you promptly. No spam, ever.</p>
        </form>
        <div class="success-msg" id="successMsg">
          <h4>Request Received!</h4>
          <p>Thank you! We'll be in touch within 24 hours with your custom quote.</p>
        </div>
        <div class="error-msg" id="errorMsg">
          Something went wrong. Please email us directly at alissahicks@redeemedandcleaned.com
        </div>
      </div>
    </div>
  </div>
</section>

<footer id="mainFooter">
  <div class="foot-logo">Redeemed <span>&</span> Cleaned</div>
  <p>Residential Cleaning &amp; Organization &nbsp;&middot;&nbsp; Proudly Serving Carlinville, IL &amp; Surrounding Areas</p>
  <p style="margin-top:8px;opacity:.5;font-size:0.7rem">&copy; 2025 Redeemed &amp; Cleaned. All rights reserved.</p>
  <a href="#" onclick="showCareers();return false;" class="foot-careers">We're Hiring — Join Our Team</a>
</footer>

<script>
  (function(){emailjs.init({publicKey:"O06yzWAZebWqid3hP"});})();

  function toggleMenu(){
    var m=document.getElementById('mobileMenu');
    m.style.display=m.style.display==='block'?'none':'block';
  }

  function submitForm(e){
    e.preventDefault();
    var btn=document.getElementById('submitBtn');
    btn.disabled=true;
    btn.textContent='Sending...';

    var addons=[];
    document.querySelectorAll('.addon:checked').forEach(function(c){addons.push(c.value);});

    var params={
      to_email:'alissahicks@redeemedandcleaned.com',
      from_name:document.getElementById('firstName').value+' '+document.getElementById('lastName').value,
      phone:document.getElementById('phone').value,
      email:document.getElementById('email').value||'Not provided',
      address:document.getElementById('address').value,
      home_size:document.getElementById('homeSize').value||'Not specified',
      bedrooms:document.getElementById('bedrooms').value||'Not specified',
      bathrooms:document.getElementById('bathrooms').value||'Not specified',
      service:document.getElementById('service').value,
      frequency:document.getElementById('frequency').value||'Not specified',
      addons:addons.length?addons.join(', '):'None selected',
      pets:document.getElementById('pets').value||'Not specified',
      notes:document.getElementById('notes').value||'None',
      referral:document.getElementById('referral').value||'Not provided'
    };

    emailjs.send('service_qd4csnq','template_aa8zurg',params)
      .then(function(){
        document.getElementById('quoteForm').style.display='none';
        document.getElementById('successMsg').style.display='block';
      },function(){
        btn.disabled=false;
        btn.textContent='Send My Quote Request';
        document.getElementById('errorMsg').style.display='block';
      });
  }
}
</script>

<!-- ═══════════════════════════════════════════════════
     CAREERS PAGE (hidden by default)
════════════════════════════════════════════════════ -->
<div id="careersPage" style="display:none">

<style>
  /* ── Careers-specific styles ── */
  .careers-hero{background:var(--dark);padding:52px 5% 0;text-align:center;position:relative;overflow:hidden}
  .careers-hero::before{content:'';position:absolute;inset:0;background:radial-gradient(ellipse at 60% 0%,rgba(212,168,67,.13) 0%,transparent 70%);pointer-events:none}
  .careers-band{height:4px;background:var(--gold);width:100%;margin-bottom:36px}
  .careers-band-bot{height:4px;background:var(--gold);width:100%;margin-top:36px}
  .careers-brand{font-family:'Playfair Display',serif;font-size:.9rem;color:rgba(255,255,255,.55);letter-spacing:4px;text-transform:uppercase;margin-bottom:10px}
  .careers-brand span{color:var(--gold)}
  .careers-title{font-family:'Playfair Display',serif;font-size:2.8rem;font-weight:700;color:#fff;line-height:1.1;margin-bottom:10px}
  .careers-title em{font-style:italic;color:var(--gold)}
  .careers-sub{font-size:.82rem;letter-spacing:4px;text-transform:uppercase;color:rgba(255,255,255,.45);margin-bottom:22px}
  .careers-desc{max-width:520px;margin:0 auto 36px;font-size:.97rem;color:rgba(255,255,255,.75);line-height:1.8}

  .perks-row{display:flex;justify-content:center;background:#2d6a4f;flex-wrap:wrap}
  .perk{flex:1;min-width:160px;max-width:240px;padding:22px 18px;text-align:center;border-right:1px solid rgba(255,255,255,.1)}
  .perk:last-child{border-right:none}
  .perk-icon{font-size:1.4rem;margin-bottom:6px}
  .perk-label{font-size:.72rem;letter-spacing:2px;text-transform:uppercase;color:rgba(255,255,255,.5);margin-bottom:3px}
  .perk-val{font-size:.92rem;color:#fff;font-weight:600}

  .app-wrap{max-width:760px;margin:44px auto 64px;padding:0 5%}
  .app-card{background:#fff;box-shadow:0 8px 48px rgba(0,0,0,.1);overflow:hidden}
  .app-card-band{height:14px;background:var(--dark)}
  .app-card-band::after{content:'';display:block;height:4px;background:var(--gold);margin-top:3px}
  .app-card-band-bot{height:14px;background:var(--dark)}
  .app-card-band-bot::before{content:'';display:block;height:4px;background:var(--gold);margin-bottom:3px}
  .app-body{padding:40px 48px}

  .app-sec{font-size:.63rem;letter-spacing:3.5px;text-transform:uppercase;color:var(--dark);font-weight:700;display:flex;align-items:center;gap:12px;margin-bottom:20px;margin-top:32px}
  .app-sec:first-of-type{margin-top:0}
  .app-sec::after{content:'';flex:1;height:1px;background:#c8ddd4}

  .app-grid{display:grid;grid-template-columns:1fr 1fr;gap:18px}
  .app-full{grid-column:1/-1}
  .app-field{display:flex;flex-direction:column;gap:5px}
  .app-field label{font-size:.62rem;letter-spacing:2.5px;text-transform:uppercase;color:#74a98a;font-weight:700}
  .app-field label .req{color:var(--gold);margin-left:2px}
  .app-field input,.app-field select,.app-field textarea{border:none;border-bottom:1.5px solid #c8ddd4;padding:7px 2px;font-size:.88rem;color:var(--dark);font-family:'Lato',sans-serif;background:transparent;outline:none;transition:border-color .2s;width:100%}
  .app-field input:focus,.app-field select:focus,.app-field textarea:focus{border-bottom-color:var(--gold)}
  .app-field select{cursor:pointer;appearance:none;background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='10' height='6'%3E%3Cpath d='M0 0l5 6 5-6z' fill='%2374a98a'/%3E%3C/svg%3E");background-repeat:no-repeat;background-position:right 4px center}
  .app-field textarea{resize:vertical;min-height:72px;line-height:1.6}

  .app-check-group{display:flex;flex-direction:column;gap:10px;margin-top:2px}
  .app-check-item{display:flex;align-items:flex-start;gap:10px;font-size:.85rem;color:#3a5a47;cursor:pointer;line-height:1.45}
  .app-check-item input[type=checkbox],.app-check-item input[type=radio]{appearance:none;width:18px;height:18px;border:2px solid #2d6a4f;border-radius:3px;flex-shrink:0;margin-top:1px;cursor:pointer;transition:all .15s;background:#fff}
  .app-check-item input[type=radio]{border-radius:50%}
  .app-check-item input[type=checkbox]:checked,.app-check-item input[type=radio]:checked{background:var(--gold);border-color:var(--gold);background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 12 12'%3E%3Cpolyline points='2,6 5,9 10,3' stroke='white' stroke-width='2.5' fill='none' stroke-linecap='round' stroke-linejoin='round'/%3E%3C/svg%3E");background-size:11px;background-repeat:no-repeat;background-position:center}
  .app-check-item input[type=radio]:checked{background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 12 12'%3E%3Ccircle cx='6' cy='6' r='3' fill='white'/%3E%3C/svg%3E")}
  .app-check-item:hover input[type=checkbox],.app-check-item:hover input[type=radio]{border-color:var(--gold);background:#fffbf0}
  .app-radio-row{display:flex;flex-wrap:wrap;gap:20px}
  .app-days-grid{display:grid;grid-template-columns:1fr 1fr;gap:8px;margin-top:10px}

  .app-file-zone{border:2px dashed #c8ddd4;border-radius:4px;padding:24px;text-align:center;cursor:pointer;transition:border-color .2s,background .2s;position:relative}
  .app-file-zone:hover,.app-file-zone.dragover{border-color:var(--gold);background:rgba(212,168,67,.05)}
  .app-file-zone input[type=file]{position:absolute;inset:0;opacity:0;cursor:pointer;width:100%;height:100%}
  .app-file-icon{font-size:1.6rem;margin-bottom:6px}
  .app-file-main{font-size:.85rem;color:var(--dark);font-weight:600;margin-bottom:3px}
  .app-file-sub{font-size:.75rem;color:#74a98a}
  .app-file-name{margin-top:8px;font-size:.8rem;color:#2d6a4f;font-weight:600;display:none}

  .app-disclaimer{background:var(--light);border-left:3px solid var(--gold);padding:14px 18px;font-size:.8rem;color:#3a5a47;line-height:1.7;margin-top:8px}
  .app-disclaimer strong{color:var(--dark)}

  .app-div{display:flex;align-items:center;gap:12px;margin:28px 0}
  .app-div::before,.app-div::after{content:'';flex:1;height:1px}
  .app-div::before{background:linear-gradient(to right,transparent,var(--gold))}
  .app-div::after{background:linear-gradient(to left,transparent,var(--gold))}
  .app-div span{color:var(--gold);font-size:1rem}

  .app-submit-row{text-align:center;margin-top:8px}
  .app-btn{padding:14px 52px;background:var(--dark);color:#fff;border:none;font-family:'Lato',sans-serif;font-size:.73rem;letter-spacing:3px;text-transform:uppercase;font-weight:700;cursor:pointer;transition:background .2s}
  .app-btn:hover{background:var(--gold);color:var(--dark)}
  .app-btn:disabled{opacity:.5;cursor:not-allowed}
  .app-status{margin-top:18px;padding:14px 20px;border-radius:4px;font-size:.85rem;text-align:center;display:none}
  .app-status.success{background:#e6f4ee;color:var(--dark);border:1px solid #c8ddd4;display:block}
  .app-status.error{background:#fdf0f0;color:#b94040;border:1px solid #f0c0c0;display:block}

  .back-link{display:inline-flex;align-items:center;gap:6px;font-size:.72rem;letter-spacing:2px;text-transform:uppercase;color:#74a98a;cursor:pointer;border:none;background:none;font-family:'Lato',sans-serif;font-weight:700;padding:0;margin-bottom:0}
  .back-link:hover{color:var(--gold)}

  @media(max-width:600px){
    .app-grid{grid-template-columns:1fr}
    .app-full{grid-column:1}
    .app-body{padding:28px 22px}
    .careers-title{font-size:2rem}
    .app-radio-row{flex-direction:column;gap:10px}
    .perks-row{flex-direction:column}
    .perk{border-right:none;border-bottom:1px solid rgba(255,255,255,.1)}
  }
</style>

<!-- Careers Hero -->
<div class="careers-hero" style="padding-top:80px">
  <div class="careers-band"></div>
  <div class="careers-brand">Redeemed <span>&</span> Cleaned</div>
  <div class="careers-title">Join <em>Our Team</em></div>
  <div class="careers-sub">Now Hiring — Cleaning Professionals</div>
  <div class="careers-desc">We're looking for reliable, detail-oriented people who take pride in their work and love leaving a space transformed. If that's you, we'd love to hear from you.</div>
  <div class="careers-band-bot"></div>
</div>

<!-- Perks Bar -->
<div class="perks-row">
  <div class="perk"><div class="perk-icon">💰</div><div class="perk-label">Compensation</div><div class="perk-val">$18 – $22 / hr</div></div>
  <div class="perk"><div class="perk-icon">🗓️</div><div class="perk-label">Schedule</div><div class="perk-val">Flexible Hours</div></div>
  <div class="perk"><div class="perk-icon">📍</div><div class="perk-label">Coverage Area</div><div class="perk-val">Carlinville &amp; Surrounding</div></div>
  <div class="perk"><div class="perk-icon">🤝</div><div class="perk-label">Environment</div><div class="perk-val">Supportive Team</div></div>
</div>

<!-- Application Form -->
<div class="app-wrap">

  <!-- Back link -->
  <button class="back-link" onclick="showMain()" style="margin-bottom:20px">&#8592; Back to Main Site</button>

  <div class="app-card">
    <div class="app-card-band"></div>
    <div class="app-body">
      <form id="appForm" novalidate>

        <div class="app-sec">Personal Information</div>
        <div class="app-grid">
          <div class="app-field" id="af-first"><label>First Name <span class="req">*</span></label><input type="text" name="first_name" placeholder="Jane" required></div>
          <div class="app-field" id="af-last"><label>Last Name <span class="req">*</span></label><input type="text" name="last_name" placeholder="Smith" required></div>
          <div class="app-field" id="af-email"><label>Email Address <span class="req">*</span></label><input type="email" name="app_email" placeholder="you@email.com" required></div>
          <div class="app-field" id="af-phone"><label>Phone Number <span class="req">*</span></label><input type="tel" name="app_phone" placeholder="(217) 555-0100" required></div>
          <div class="app-field app-full" id="af-address"><label>Street Address <span class="req">*</span></label><input type="text" name="app_address" placeholder="123 Main St, City, IL  62626" required></div>
        </div>

        <div class="app-sec">Legal Eligibility</div>
        <div class="app-grid">
          <div class="app-field app-full"><label>Are you legally authorized to work in the United States? <span class="req">*</span></label>
            <div class="app-radio-row" style="margin-top:10px">
              <label class="app-check-item"><input type="radio" name="work_auth" value="Yes"> Yes, I am authorized to work in the U.S.</label>
              <label class="app-check-item"><input type="radio" name="work_auth" value="No"> No</label>
            </div>
          </div>
          <div class="app-field app-full"><label>Are you 18 years of age or older? <span class="req">*</span></label>
            <div class="app-radio-row" style="margin-top:10px">
              <label class="app-check-item"><input type="radio" name="age_18" value="Yes"> Yes</label>
              <label class="app-check-item"><input type="radio" name="age_18" value="No"> No</label>
            </div>
          </div>
          <div class="app-field app-full"><label>Have you ever been convicted of a felony? <span class="req">*</span></label>
            <div class="app-radio-row" style="margin-top:10px">
              <label class="app-check-item"><input type="radio" name="felony" value="No"> No</label>
              <label class="app-check-item"><input type="radio" name="felony" value="Yes"> Yes — a conviction does not automatically disqualify you</label>
            </div>
          </div>
          <div class="app-field app-full"><label>Do you have a valid driver's license and reliable transportation? <span class="req">*</span></label>
            <div class="app-radio-row" style="margin-top:10px">
              <label class="app-check-item"><input type="radio" name="transportation" value="Yes"> Yes</label>
              <label class="app-check-item"><input type="radio" name="transportation" value="No"> No</label>
            </div>
          </div>
        </div>

        <div class="app-sec">Availability &amp; Position</div>
        <div class="app-grid">
          <div class="app-field app-full"><label>What days are you generally available? <span class="req">*</span></label>
            <div class="app-days-grid">
              <label class="app-check-item"><input type="checkbox" name="avail_days" value="Monday"> Monday</label>
              <label class="app-check-item"><input type="checkbox" name="avail_days" value="Tuesday"> Tuesday</label>
              <label class="app-check-item"><input type="checkbox" name="avail_days" value="Wednesday"> Wednesday</label>
              <label class="app-check-item"><input type="checkbox" name="avail_days" value="Thursday"> Thursday</label>
              <label class="app-check-item"><input type="checkbox" name="avail_days" value="Friday"> Friday</label>
              <label class="app-check-item"><input type="checkbox" name="avail_days" value="Saturday"> Saturday</label>
              <label class="app-check-item"><input type="checkbox" name="avail_days" value="Sunday"> Sunday</label>
            </div>
          </div>
          <div class="app-field" id="af-hours"><label>Preferred hours per week <span class="req">*</span></label>
            <select name="hours_week" required>
              <option value="">Select…</option>
              <option>Part-time (under 20 hrs)</option>
              <option>Part-time (20–29 hrs)</option>
              <option>Full-time (30+ hrs)</option>
              <option>Flexible / As needed</option>
            </select>
          </div>
          <div class="app-field" id="af-start"><label>Earliest available start date <span class="req">*</span></label><input type="date" name="start_date" required></div>
        </div>

        <div class="app-sec">Experience &amp; Background</div>
        <div class="app-grid">
          <div class="app-field app-full"><label>Do you have prior professional cleaning experience?</label>
            <div class="app-radio-row" style="margin-top:10px">
              <label class="app-check-item"><input type="radio" name="prior_exp" value="Yes"> Yes</label>
              <label class="app-check-item"><input type="radio" name="prior_exp" value="No"> No</label>
            </div>
          </div>
          <div class="app-field app-full"><label>If yes — briefly describe your experience</label><textarea name="exp_detail" placeholder="e.g. 2 years residential cleaning, familiar with move-out cleans…"></textarea></div>
          <div class="app-field app-full"><label>How did you hear about this position?</label>
            <select name="referral_src">
              <option value="">Select…</option>
              <option>Word of mouth / friend or family</option>
              <option>Facebook</option>
              <option>Google search</option>
              <option>Indeed or job board</option>
              <option>Our website</option>
              <option>Other</option>
            </select>
          </div>
          <div class="app-field app-full"><label>Anything else you'd like us to know?</label><textarea name="additional" placeholder="Optional — share anything relevant to your application…"></textarea></div>
        </div>

        <div class="app-sec">Résumé / References</div>
        <div class="app-field app-full">
          <label>Upload Résumé <span style="font-size:.65rem;color:#74a98a;font-style:italic;text-transform:none;letter-spacing:0">(optional — PDF, DOC, or DOCX · max 5 MB)</span></label>
          <div class="app-file-zone" id="appFileZone">
            <input type="file" id="appResumeFile" accept=".pdf,.doc,.docx">
            <div class="app-file-icon">📄</div>
            <div class="app-file-main">Click to browse or drag &amp; drop</div>
            <div class="app-file-sub">PDF, DOC, or DOCX — up to 5 MB</div>
            <div class="app-file-name" id="appFileName"></div>
          </div>
        </div>

        <div class="app-disclaimer">
          <strong>Equal Opportunity Statement:</strong> Redeemed &amp; Cleaned LLC is an equal opportunity employer and does not discriminate on the basis of race, color, religion, sex, national origin, age, disability, or any other characteristic protected by law.
        </div>

        <div class="app-div"><span>&#10022;</span></div>

        <div class="app-field app-full" style="margin-bottom:22px">
          <label class="app-check-item" style="align-items:flex-start">
            <input type="checkbox" id="appConsent" required style="margin-top:3px">
            <span>I certify that the information provided is true and complete to the best of my knowledge. I consent to Redeemed &amp; Cleaned LLC retaining this application for consideration. <span class="req">*</span></span>
          </label>
        </div>

        <div class="app-submit-row">
          <button class="app-btn" type="submit" id="appSubmitBtn">Submit Application</button>
          <div class="app-status" id="appStatusMsg"></div>
        </div>

      </form>
    </div>
    <div class="app-card-band-bot"></div>
  </div>
</div>

  <footer>
    <div class="foot-logo">Redeemed <span>&</span> Cleaned</div>
    <p>Residential Cleaning &amp; Organization &nbsp;&middot;&nbsp; Proudly Serving Carlinville, IL &amp; Surrounding Areas</p>
    <p style="margin-top:8px;opacity:.5;font-size:0.7rem">&copy; 2025 Redeemed &amp; Cleaned. All rights reserved.</p>
    <button onclick="showMain()" style="margin-top:14px;font-size:0.7rem;letter-spacing:2px;text-transform:uppercase;color:var(--gold);background:none;border:1px solid rgba(212,168,67,0.35);padding:6px 18px;border-radius:3px;cursor:pointer;font-family:'Lato',sans-serif">&#8592; Back to Main Site</button>
  </footer>

</div><!-- end #careersPage -->

<script>
  // ── Page switching ──────────────────────────────────────────
  var mainEls = ['home','about','pricing','addons','contact','mainFooter'];

  function showCareers(){
    mainEls.forEach(function(id){ var el=document.getElementById(id); if(el) el.style.display='none'; });
    document.getElementById('careersPage').style.display='block';
    window.scrollTo(0,0);
  }

  function showMain(){
    document.getElementById('careersPage').style.display='none';
    mainEls.forEach(function(id){ var el=document.getElementById(id); if(el) el.style.display=''; });
    window.scrollTo(0,0);
  }

  // ── Careers form ────────────────────────────────────────────
  var appZone = document.getElementById('appFileZone');
  var appFileInput = document.getElementById('appResumeFile');
  var appFileNameEl = document.getElementById('appFileName');

  appZone.addEventListener('dragover',function(e){e.preventDefault();appZone.classList.add('dragover');});
  appZone.addEventListener('dragleave',function(){appZone.classList.remove('dragover');});
  appZone.addEventListener('drop',function(e){e.preventDefault();appZone.classList.remove('dragover');if(e.dataTransfer.files[0]){appFileInput.files=e.dataTransfer.files;showAppFileName();}});
  appFileInput.addEventListener('change',showAppFileName);

  function showAppFileName(){
    var f=appFileInput.files[0];
    if(!f)return;
    if(f.size>5*1024*1024){alert('File is larger than 5 MB. Please choose a smaller file.');appFileInput.value='';appFileNameEl.style.display='none';return;}
    appFileNameEl.textContent='✓ '+f.name;
    appFileNameEl.style.display='block';
  }

  function getChecked(name){
    return Array.from(document.querySelectorAll('input[name="'+name+'"]:checked')).map(function(el){return el.value;}).join(', ')||'None selected';
  }
  function getRadio(name){
    var el=document.querySelector('input[name="'+name+'"]:checked');
    return el?el.value:'Not answered';
  }
  function getVal(name){
    var el=document.querySelector('[name="'+name+'"]');
    return el?el.value.trim():'';
  }
  function toBase64(file){
    return new Promise(function(res,rej){var r=new FileReader();r.onload=function(){res(r.result.split(',')[1]);};r.onerror=rej;r.readAsDataURL(file);});
  }
  function nowStr(){return new Date().toLocaleDateString('en-US',{month:'long',day:'numeric',year:'numeric'});}

  document.getElementById('appForm').addEventListener('submit',async function(e){
    e.preventDefault();
    var errors=[];
    if(!getVal('first_name'))errors.push('First name');
    if(!getVal('last_name'))errors.push('Last name');
    if(!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(getVal('app_email')))errors.push('Valid email address');
    if(getVal('app_phone').length<7)errors.push('Phone number');
    if(!getVal('app_address'))errors.push('Street address');
    if(!getVal('hours_week'))errors.push('Hours per week');
    if(!getVal('start_date'))errors.push('Start date');
    if(!document.getElementById('appConsent').checked)errors.push('Consent checkbox');

    var statusEl=document.getElementById('appStatusMsg');
    if(errors.length>0){
      statusEl.className='app-status error';
      statusEl.textContent='Please complete the following: '+errors.join(', ')+'.';
      statusEl.style.display='block';
      return;
    }

    var btn=document.getElementById('appSubmitBtn');
    btn.disabled=true;btn.textContent='Sending…';
    statusEl.style.display='none';

    var params={
      applicant_name:getVal('first_name')+' '+getVal('last_name'),
      first_name:getVal('first_name'),
      last_name:getVal('last_name'),
      email:getVal('app_email'),
      phone:getVal('app_phone'),
      address:getVal('app_address'),
      work_auth:getRadio('work_auth'),
      age_18:getRadio('age_18'),
      felony:getRadio('felony'),
      transportation:getRadio('transportation'),
      avail_days:getChecked('avail_days'),
      hours_week:getVal('hours_week'),
      start_date:getVal('start_date'),
      prior_exp:getRadio('prior_exp'),
      exp_detail:getVal('exp_detail')||'N/A',
      referral:getVal('referral_src')||'Not specified',
      additional:getVal('additional')||'N/A',
      submitted_at:nowStr(),
      reply_to:getVal('app_email'),
      has_resume:'No résumé uploaded',
      resume_name:'None'
    };

    var resumeFile=appFileInput.files[0];
    if(resumeFile){
      try{
        var b64=await toBase64(resumeFile);
        params.resume_name=resumeFile.name;
        params.resume_data=b64;
        params.has_resume='Yes — see attachment';
      }catch(err){params.has_resume='File could not be attached';}
    }

    try{
      await emailjs.send('service_qd4csnq','template_5emaxh8',params);
      statusEl.className='app-status success';
      statusEl.textContent='✓ Your application has been submitted! We\'ll be in touch soon.';
      statusEl.style.display='block';
      document.getElementById('appForm').reset();
      appFileNameEl.style.display='none';
    }catch(err){
      statusEl.className='app-status error';
      statusEl.textContent='Something went wrong. Please email us directly at alissahicks@redeemedandcleaned.com.';
      statusEl.style.display='block';
    }
    btn.disabled=false;btn.textContent='Submit Application';
  });
</script>
</body>
</html>
