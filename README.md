<!DOCTYPE html>

<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>OGM — Studio Créatif</title>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@300;400;600;700&family=Bebas+Neue&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --black: #080808;
    --dark: #111111;
    --card: #161616;
    --gold: #C9A84C;
    --gold-light: #E8C97A;
    --gold-dim: #8a6e2f;
    --white: #F5F0E8;
    --grey: #888;
    --border: rgba(201,168,76,0.2);
  }

- { margin: 0; padding: 0; box-sizing: border-box; }

html { scroll-behavior: smooth; }

body {
background: var(–black);
color: var(–white);
font-family: ‘DM Sans’, sans-serif;
overflow-x: hidden;
cursor: none;
}

/* Custom cursor */
.cursor {
position: fixed;
width: 8px; height: 8px;
background: var(–gold);
border-radius: 50%;
pointer-events: none;
z-index: 9999;
transform: translate(-50%, -50%);
transition: transform 0.1s;
}
.cursor-ring {
position: fixed;
width: 32px; height: 32px;
border: 1px solid rgba(201,168,76,0.5);
border-radius: 50%;
pointer-events: none;
z-index: 9998;
transform: translate(-50%, -50%);
transition: all 0.15s ease;
}

/* NAV */
nav {
position: fixed; top: 0; left: 0; right: 0;
z-index: 100;
padding: 24px 60px;
display: flex;
justify-content: space-between;
align-items: center;
background: linear-gradient(to bottom, rgba(8,8,8,0.95), transparent);
backdrop-filter: blur(10px);
}

.logo {
font-family: ‘Bebas Neue’, sans-serif;
font-size: 2.8rem;
letter-spacing: 0.15em;
color: var(–gold);
text-shadow: 0 0 30px rgba(201,168,76,0.4);
}

.nav-links {
display: flex;
gap: 40px;
list-style: none;
}

.nav-links a {
font-family: ‘DM Sans’, sans-serif;
font-size: 0.78rem;
letter-spacing: 0.18em;
text-transform: uppercase;
color: var(–grey);
text-decoration: none;
transition: color 0.3s;
}
.nav-links a:hover { color: var(–gold); }

.nav-cta {
padding: 10px 26px;
border: 1px solid var(–gold);
color: var(–gold) !important;
transition: all 0.3s !important;
}
.nav-cta:hover {
background: var(–gold) !important;
color: var(–black) !important;
}

/* HERO */
.hero {
min-height: 100vh;
display: flex;
align-items: center;
justify-content: center;
position: relative;
overflow: hidden;
padding: 120px 60px 80px;
}

.hero-bg {
position: absolute; inset: 0;
background: radial-gradient(ellipse 80% 60% at 60% 40%, rgba(201,168,76,0.07) 0%, transparent 60%),
radial-gradient(ellipse 40% 40% at 20% 80%, rgba(201,168,76,0.04) 0%, transparent 50%);
}

.hero-grid {
position: absolute; inset: 0;
background-image: linear-gradient(rgba(201,168,76,0.04) 1px, transparent 1px),
linear-gradient(90deg, rgba(201,168,76,0.04) 1px, transparent 1px);
background-size: 60px 60px;
mask-image: radial-gradient(ellipse 80% 80% at 50% 50%, black, transparent);
}

.hero-content {
position: relative;
z-index: 2;
max-width: 900px;
}

.hero-tag {
display: inline-block;
font-size: 0.72rem;
letter-spacing: 0.25em;
text-transform: uppercase;
color: var(–gold);
border: 1px solid var(–border);
padding: 8px 20px;
margin-bottom: 40px;
animation: fadeUp 0.8s ease both;
}

.hero-title {
font-family: ‘Bebas Neue’, sans-serif;
font-size: clamp(5rem, 14vw, 11rem);
line-height: 0.9;
letter-spacing: 0.05em;
color: var(–white);
animation: fadeUp 0.8s ease 0.15s both;
}

.hero-title span {
color: var(–gold);
display: block;
}

.hero-sub {
font-family: ‘Cormorant Garamond’, serif;
font-size: 1.5rem;
font-weight: 300;
color: var(–grey);
margin-top: 24px;
letter-spacing: 0.05em;
animation: fadeUp 0.8s ease 0.3s both;
}

.hero-desc {
font-size: 0.95rem;
color: rgba(245,240,232,0.6);
line-height: 1.8;
max-width: 520px;
margin-top: 20px;
animation: fadeUp 0.8s ease 0.45s both;
}

.hero-btns {
display: flex;
gap: 20px;
margin-top: 48px;
animation: fadeUp 0.8s ease 0.6s both;
}

.btn-gold {
padding: 16px 40px;
background: var(–gold);
color: var(–black);
font-weight: 600;
font-size: 0.82rem;
letter-spacing: 0.15em;
text-transform: uppercase;
text-decoration: none;
transition: all 0.3s;
}
.btn-gold:hover {
background: var(–gold-light);
transform: translateY(-2px);
box-shadow: 0 10px 30px rgba(201,168,76,0.3);
}

.btn-outline {
padding: 16px 40px;
border: 1px solid rgba(245,240,232,0.3);
color: var(–white);
font-size: 0.82rem;
letter-spacing: 0.15em;
text-transform: uppercase;
text-decoration: none;
transition: all 0.3s;
}
.btn-outline:hover {
border-color: var(–gold);
color: var(–gold);
}

.hero-stats {
display: flex;
gap: 60px;
margin-top: 80px;
padding-top: 40px;
border-top: 1px solid var(–border);
animation: fadeUp 0.8s ease 0.75s both;
}

.stat-num {
font-family: ‘Bebas Neue’, sans-serif;
font-size: 2.8rem;
color: var(–gold);
letter-spacing: 0.05em;
}
.stat-label {
font-size: 0.72rem;
letter-spacing: 0.15em;
text-transform: uppercase;
color: var(–grey);
margin-top: 4px;
}

/* SECTIONS */
section {
padding: 120px 60px;
}

.section-tag {
font-size: 0.72rem;
letter-spacing: 0.25em;
text-transform: uppercase;
color: var(–gold);
margin-bottom: 16px;
}

.section-title {
font-family: ‘Bebas Neue’, sans-serif;
font-size: clamp(2.5rem, 5vw, 4rem);
letter-spacing: 0.06em;
line-height: 1;
color: var(–white);
margin-bottom: 16px;
}

.section-line {
width: 60px;
height: 2px;
background: var(–gold);
margin-bottom: 60px;
}

/* SERVICES */
#services { background: var(–dark); }

.services-grid {
display: grid;
grid-template-columns: repeat(2, 1fr);
gap: 2px;
}

.service-card {
background: var(–card);
padding: 50px 44px;
border: 1px solid transparent;
transition: all 0.4s;
position: relative;
overflow: hidden;
}

.service-card::before {
content: ‘’;
position: absolute;
top: 0; left: 0; right: 0;
height: 2px;
background: var(–gold);
transform: scaleX(0);
transition: transform 0.4s;
transform-origin: left;
}

.service-card:hover {
border-color: var(–border);
transform: translateY(-4px);
box-shadow: 0 20px 60px rgba(0,0,0,0.5);
}

.service-card:hover::before { transform: scaleX(1); }

.service-icon {
font-size: 2.5rem;
margin-bottom: 24px;
}

.service-title {
font-family: ‘Bebas Neue’, sans-serif;
font-size: 1.8rem;
letter-spacing: 0.08em;
color: var(–white);
margin-bottom: 16px;
}

.service-desc {
font-size: 0.9rem;
line-height: 1.8;
color: var(–grey);
margin-bottom: 24px;
}

.service-features {
list-style: none;
display: flex;
flex-direction: column;
gap: 8px;
}

.service-features li {
font-size: 0.82rem;
color: rgba(245,240,232,0.6);
padding-left: 16px;
position: relative;
}

.service-features li::before {
content: ‘—’;
position: absolute;
left: 0;
color: var(–gold);
}

/* PACKAGES */
#packages { background: var(–black); }

.packages-grid {
display: grid;
grid-template-columns: repeat(3, 1fr);
gap: 24px;
}

.pkg-card {
background: var(–card);
border: 1px solid var(–border);
padding: 44px 36px;
transition: all 0.4s;
position: relative;
}

.pkg-card.featured {
border-color: var(–gold);
background: linear-gradient(160deg, #1c1a12, var(–card));
}

.pkg-card.featured::after {
content: ‘POPULAIRE’;
position: absolute;
top: -1px; right: 24px;
background: var(–gold);
color: var(–black);
font-size: 0.65rem;
font-weight: 700;
letter-spacing: 0.15em;
padding: 6px 14px;
}

.pkg-card:hover {
transform: translateY(-6px);
box-shadow: 0 30px 80px rgba(0,0,0,0.6);
}

.pkg-icon { font-size: 2rem; margin-bottom: 20px; }

.pkg-name {
font-family: ‘Bebas Neue’, sans-serif;
font-size: 1.6rem;
letter-spacing: 0.08em;
color: var(–white);
margin-bottom: 8px;
}

.pkg-desc {
font-size: 0.82rem;
color: var(–grey);
margin-bottom: 24px;
}

.pkg-price {
font-family: ‘Cormorant Garamond’, serif;
font-size: 2.8rem;
font-weight: 600;
color: var(–gold);
margin-bottom: 4px;
}

.pkg-price-sub {
font-size: 0.75rem;
color: var(–grey);
margin-bottom: 32px;
letter-spacing: 0.05em;
}

.pkg-features {
list-style: none;
display: flex;
flex-direction: column;
gap: 12px;
margin-bottom: 36px;
}

.pkg-features li {
font-size: 0.85rem;
color: rgba(245,240,232,0.7);
display: flex;
align-items: center;
gap: 10px;
}

.pkg-features li::before {
content: ‘✦’;
color: var(–gold);
font-size: 0.6rem;
flex-shrink: 0;
}

.pkg-btn {
display: block;
text-align: center;
padding: 14px;
border: 1px solid var(–border);
color: var(–white);
text-decoration: none;
font-size: 0.78rem;
letter-spacing: 0.15em;
text-transform: uppercase;
transition: all 0.3s;
}

.pkg-btn:hover, .pkg-card.featured .pkg-btn {
background: var(–gold);
color: var(–black);
border-color: var(–gold);
}

/* PORTFOLIO */
#portfolio { background: var(–dark); }

.portfolio-grid {
display: grid;
grid-template-columns: repeat(3, 1fr);
grid-template-rows: auto;
gap: 16px;
}

.portfolio-item {
background: var(–card);
aspect-ratio: 4/3;
position: relative;
overflow: hidden;
cursor: pointer;
}

.portfolio-item:first-child {
grid-column: span 2;
aspect-ratio: 16/9;
}

.portfolio-placeholder {
width: 100%; height: 100%;
display: flex;
align-items: center;
justify-content: center;
flex-direction: column;
gap: 12px;
background: linear-gradient(135deg, #161616, #1a1a1a);
transition: all 0.4s;
}

.portfolio-placeholder span {
font-size: 2.5rem;
}

.portfolio-placeholder p {
font-size: 0.75rem;
letter-spacing: 0.15em;
text-transform: uppercase;
color: var(–grey);
}

.portfolio-overlay {
position: absolute; inset: 0;
background: rgba(201,168,76,0.08);
border: 2px solid var(–gold);
opacity: 0;
transition: all 0.4s;
display: flex;
align-items: center;
justify-content: center;
}

.portfolio-item:hover .portfolio-overlay { opacity: 1; }
.portfolio-item:hover .portfolio-placeholder { transform: scale(1.05); }

/* BOOKING */
#booking { background: var(–black); }

.booking-layout {
display: grid;
grid-template-columns: 1fr 1fr;
gap: 80px;
align-items: start;
}

.booking-info h3 {
font-family: ‘Cormorant Garamond’, serif;
font-size: 1.8rem;
font-weight: 300;
color: var(–white);
margin-bottom: 24px;
line-height: 1.4;
}

.booking-info p {
font-size: 0.9rem;
color: var(–grey);
line-height: 1.8;
margin-bottom: 40px;
}

.contact-items {
display: flex;
flex-direction: column;
gap: 20px;
}

.contact-item {
display: flex;
align-items: center;
gap: 16px;
padding: 16px 20px;
border: 1px solid var(–border);
transition: all 0.3s;
}

.contact-item:hover {
border-color: var(–gold);
background: rgba(201,168,76,0.05);
}

.contact-item-icon {
font-size: 1.2rem;
width: 40px;
text-align: center;
}

.contact-item-label {
font-size: 0.72rem;
letter-spacing: 0.15em;
text-transform: uppercase;
color: var(–grey);
}

.contact-item-value {
font-size: 0.9rem;
color: var(–white);
margin-top: 2px;
}

/* FORM */
.booking-form {
display: flex;
flex-direction: column;
gap: 20px;
}

.form-group {
display: flex;
flex-direction: column;
gap: 8px;
}

.form-group label {
font-size: 0.72rem;
letter-spacing: 0.15em;
text-transform: uppercase;
color: var(–gold);
}

.form-group input,
.form-group select,
.form-group textarea {
background: var(–card);
border: 1px solid var(–border);
color: var(–white);
padding: 14px 18px;
font-family: ‘DM Sans’, sans-serif;
font-size: 0.9rem;
outline: none;
transition: border-color 0.3s;
appearance: none;
}

.form-group input:focus,
.form-group select:focus,
.form-group textarea:focus {
border-color: var(–gold);
}

.form-group select option {
background: var(–card);
}

.form-group textarea {
resize: vertical;
min-height: 120px;
}

.form-row {
display: grid;
grid-template-columns: 1fr 1fr;
gap: 16px;
}

.form-submit {
padding: 18px;
background: var(–gold);
color: var(–black);
border: none;
font-family: ‘DM Sans’, sans-serif;
font-weight: 700;
font-size: 0.82rem;
letter-spacing: 0.2em;
text-transform: uppercase;
cursor: pointer;
transition: all 0.3s;
margin-top: 8px;
}

.form-submit:hover {
background: var(–gold-light);
box-shadow: 0 10px 30px rgba(201,168,76,0.3);
}

/* FOOTER */
footer {
background: var(–dark);
padding: 60px 60px 40px;
border-top: 1px solid var(–border);
}

.footer-top {
display: flex;
justify-content: space-between;
align-items: center;
margin-bottom: 40px;
}

.footer-logo {
font-family: ‘Bebas Neue’, sans-serif;
font-size: 3rem;
color: var(–gold);
letter-spacing: 0.15em;
}

.footer-links {
display: flex;
gap: 32px;
list-style: none;
}

.footer-links a {
font-size: 0.78rem;
letter-spacing: 0.12em;
text-transform: uppercase;
color: var(–grey);
text-decoration: none;
transition: color 0.3s;
}

.footer-links a:hover { color: var(–gold); }

.footer-bottom {
display: flex;
justify-content: space-between;
align-items: center;
padding-top: 32px;
border-top: 1px solid var(–border);
}

.footer-copy {
font-size: 0.78rem;
color: var(–grey);
}

.footer-copy span { color: var(–gold); }

.social-links {
display: flex;
gap: 16px;
}

.social-link {
width: 38px; height: 38px;
border: 1px solid var(–border);
display: flex;
align-items: center;
justify-content: center;
font-size: 0.85rem;
color: var(–grey);
text-decoration: none;
transition: all 0.3s;
}

.social-link:hover {
border-color: var(–gold);
color: var(–gold);
background: rgba(201,168,76,0.08);
}

/* ANIMATIONS */
@keyframes fadeUp {
from { opacity: 0; transform: translateY(30px); }
to { opacity: 1; transform: translateY(0); }
}

.reveal {
opacity: 0;
transform: translateY(40px);
transition: all 0.8s ease;
}

.reveal.visible {
opacity: 1;
transform: translateY(0);
}

/* SUCCESS MESSAGE */
.success-msg {
display: none;
background: rgba(201,168,76,0.1);
border: 1px solid var(–gold);
padding: 20px;
text-align: center;
color: var(–gold);
font-size: 0.9rem;
letter-spacing: 0.05em;
}

@media (max-width: 768px) {
nav { padding: 20px 24px; }
.nav-links { display: none; }
section { padding: 80px 24px; }
.hero { padding: 100px 24px 60px; }
.hero-stats { gap: 32px; flex-wrap: wrap; }
.services-grid { grid-template-columns: 1fr; }
.packages-grid { grid-template-columns: 1fr; }
.portfolio-grid { grid-template-columns: 1fr; }
.portfolio-item:first-child { grid-column: span 1; }
.booking-layout { grid-template-columns: 1fr; gap: 40px; }
.form-row { grid-template-columns: 1fr; }
.footer-top { flex-direction: column; gap: 24px; text-align: center; }
.footer-bottom { flex-direction: column; gap: 16px; }
}
</style>

</head>
<body>

<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>

<!-- NAV -->

<nav>
  <div class="logo">OGM</div>
  <ul class="nav-links">
    <li><a href="#services">Services</a></li>
    <li><a href="#packages">Packages</a></li>
    <li><a href="#portfolio">Portfolio</a></li>
    <li><a href="#booking" class="nav-cta">Réserver</a></li>
  </ul>
</nav>

<!-- HERO -->

<section class="hero" id="home">
  <div class="hero-bg"></div>
  <div class="hero-grid"></div>
  <div class="hero-content">
    <div class="hero-tag">Studio Créatif Professionnel</div>
    <h1 class="hero-title">
      OGM
      <span>STUDIO</span>
    </h1>
    <p class="hero-sub">Production • Musique • Danse • Réalisation</p>
    <p class="hero-desc">
      Un écosystème créatif complet sous un même toit. Vous arrivez avec une vision, 
      nous vous livrons un projet d'exception — son, scène et image.
    </p>
    <div class="hero-btns">
      <a href="#packages" class="btn-gold">Voir les packages</a>
      <a href="#booking" class="btn-outline">Prendre contact</a>
    </div>
    <div class="hero-stats">
      <div>
        <div class="stat-num">4</div>
        <div class="stat-label">Expertises</div>
      </div>
      <div>
        <div class="stat-num">1</div>
        <div class="stat-label">Toit</div>
      </div>
      <div>
        <div class="stat-num">∞</div>
        <div class="stat-label">Possibilités</div>
      </div>
    </div>
  </div>
</section>

<!-- SERVICES -->

<section id="services">
  <div class="section-tag reveal">— Nos expertises</div>
  <h2 class="section-title reveal">CE QUE NOUS<br>FAISONS</h2>
  <div class="section-line reveal"></div>
  <div class="services-grid">
    <div class="service-card reveal">
      <div class="service-icon">🎙️</div>
      <div class="service-title">Studio d'enregistrement</div>
      <p class="service-desc">Un espace acoustiquement traité avec des équipements haut de gamme pour capturer votre son avec une précision absolue.</p>
      <ul class="service-features">
        <li>Sessions d'enregistrement professionnelles</li>
        <li>Mixage et mastering de qualité</li>
        <li>Location à l'heure ou en forfait</li>
        <li>Direction artistique disponible</li>
      </ul>
    </div>
    <div class="service-card reveal">
      <div class="service-icon">🎵</div>
      <div class="service-title">Production Musicale</div>
      <p class="service-desc">De la création de beats sur mesure à la production complète, nous donnons vie à votre univers sonore.</p>
      <ul class="service-features">
        <li>Création de beats et instrumentaux</li>
        <li>Arrangements et direction musicale</li>
        <li>Licensing et placement de sons</li>
        <li>Catalogue de productions disponibles</li>
      </ul>
    </div>
    <div class="service-card reveal">
      <div class="service-icon">💃</div>
      <div class="service-title">Groupe de Danse</div>
      <p class="service-desc">Des performances scéniques captivantes pour vos événements. Énergie, précision et spectacle garantis.</p>
      <ul class="service-features">
        <li>Prestations événementielles</li>
        <li>Animations corporate et galas</li>
        <li>Chorégraphies sur mesure</li>
        <li>Workshops et formations</li>
      </ul>
    </div>
    <div class="service-card reveal">
      <div class="service-icon">🎬</div>
      <div class="service-title">Réalisation Vidéo</div>
      <p class="service-desc">Des clips qui marquent les esprits. De la conception à la livraison, une image qui sublime votre musique.</p>
      <ul class="service-features">
        <li>Clips musicaux professionnels</li>
        <li>Publicités et vidéos corporate</li>
        <li>Contenu pour réseaux sociaux</li>
        <li>Courts métrages et documentaires</li>
      </ul>
    </div>
  </div>
</section>

<!-- PACKAGES -->

<section id="packages">
  <div class="section-tag reveal">— Nos offres</div>
  <h2 class="section-title reveal">PACKAGES<br>& TARIFS</h2>
  <div class="section-line reveal"></div>
  <div class="packages-grid">
    <div class="pkg-card reveal">
      <div class="pkg-icon">🎵</div>
      <div class="pkg-name">Pack Artiste</div>
      <p class="pkg-desc">Pour les artistes qui veulent se lancer</p>
      <div class="pkg-price">600€</div>
      <div class="pkg-price-sub">jusqu'à 1 200€ selon le projet</div>
      <ul class="pkg-features">
        <li>Session studio 4h d'enregistrement</li>
        <li>Beat + mixage + mastering</li>
        <li>Clip vidéo (tournage 1 jour + montage)</li>
        <li>Livraison en 7 à 10 jours</li>
      </ul>
      <a href="#booking" class="pkg-btn">Demander un devis</a>
    </div>
    <div class="pkg-card featured reveal">
      <div class="pkg-icon">🚀</div>
      <div class="pkg-name">Pack Full Créatif</div>
      <p class="pkg-desc">La solution complète pour les projets ambitieux</p>
      <div class="pkg-price">1 500€</div>
      <div class="pkg-price-sub">jusqu'à 3 800€ selon le projet</div>
      <ul class="pkg-features">
        <li>Production musicale complète</li>
        <li>Clip professionnel haute qualité</li>
        <li>3 à 5 vidéos réseaux sociaux</li>
        <li>Prestation danse si besoin</li>
        <li>Accompagnement artistique complet</li>
      </ul>
      <a href="#booking" class="pkg-btn">Demander un devis</a>
    </div>
    <div class="pkg-card reveal">
      <div class="pkg-icon">🎉</div>
      <div class="pkg-name">Pack Événement</div>
      <p class="pkg-desc">Pour vos mariages, galas et événements</p>
      <div class="pkg-price">450€</div>
      <div class="pkg-price-sub">jusqu'à 900€ selon l'événement</div>
      <ul class="pkg-features">
        <li>Prestation groupe de danse 30–45 min</li>
        <li>Filmage de l'événement</li>
        <li>Montage vidéo inclus</li>
        <li>Habillage sonore si besoin</li>
      </ul>
      <a href="#booking" class="pkg-btn">Demander un devis</a>
    </div>
  </div>
</section>

<!-- PORTFOLIO -->

<section id="portfolio">
  <div class="section-tag reveal">— Nos réalisations</div>
  <h2 class="section-title reveal">PORTFOLIO</h2>
  <div class="section-line reveal"></div>
  <div class="portfolio-grid">
    <div class="portfolio-item reveal">
      <div class="portfolio-placeholder">
        <span>🎬</span>
        <p>Votre clip phare ici</p>
      </div>
      <div class="portfolio-overlay">
        <span style="color:var(--gold);font-size:0.8rem;letter-spacing:0.2em;text-transform:uppercase;">Voir le projet</span>
      </div>
    </div>
    <div class="portfolio-item reveal">
      <div class="portfolio-placeholder">
        <span>🎵</span>
        <p>Production musicale</p>
      </div>
      <div class="portfolio-overlay">
        <span style="color:var(--gold);font-size:0.8rem;letter-spacing:0.2em;text-transform:uppercase;">Écouter</span>
      </div>
    </div>
    <div class="portfolio-item reveal">
      <div class="portfolio-placeholder">
        <span>💃</span>
        <p>Performance danse</p>
      </div>
      <div class="portfolio-overlay">
        <span style="color:var(--gold);font-size:0.8rem;letter-spacing:0.2em;text-transform:uppercase;">Voir la vidéo</span>
      </div>
    </div>
    <div class="portfolio-item reveal">
      <div class="portfolio-placeholder">
        <span>🎙️</span>
        <p>Session studio</p>
      </div>
      <div class="portfolio-overlay">
        <span style="color:var(--gold);font-size:0.8rem;letter-spacing:0.2em;text-transform:uppercase;">Découvrir</span>
      </div>
    </div>
    <div class="portfolio-item reveal">
      <div class="portfolio-placeholder">
        <span>📸</span>
        <p>Shooting artistique</p>
      </div>
      <div class="portfolio-overlay">
        <span style="color:var(--gold);font-size:0.8rem;letter-spacing:0.2em;text-transform:uppercase;">Voir les photos</span>
      </div>
    </div>
  </div>
</section>

<!-- BOOKING -->

<section id="booking">
  <div class="section-tag reveal">— On vous attend</div>
  <h2 class="section-title reveal">RÉSERVEZ<br>VOTRE SESSION</h2>
  <div class="section-line reveal"></div>
  <div class="booking-layout">
    <div class="booking-info reveal">
      <h3>Votre projet mérite une attention particulière. Parlons-en.</h3>
      <p>Remplissez le formulaire ou contactez-nous directement. Nous vous répondons sous 24h avec un devis personnalisé adapté à votre projet et votre budget.</p>
      <div class="contact-items">
        <div class="contact-item">
          <div class="contact-item-icon">📧</div>
          <div>
            <div class="contact-item-label">Email</div>
            <div class="contact-item-value">contact@ogm-studio.com</div>
          </div>
        </div>
        <div class="contact-item">
          <div class="contact-item-icon">📱</div>
          <div>
            <div class="contact-item-label">Téléphone / WhatsApp</div>
            <div class="contact-item-value">+33 X XX XX XX XX</div>
          </div>
        </div>
        <div class="contact-item">
          <div class="contact-item-icon">📍</div>
          <div>
            <div class="contact-item-label">Localisation</div>
            <div class="contact-item-value">Votre ville, France</div>
          </div>
        </div>
        <div class="contact-item">
          <div class="contact-item-icon">⏰</div>
          <div>
            <div class="contact-item-label">Disponibilités</div>
            <div class="contact-item-value">Lun — Sam, 9h à 22h</div>
          </div>
        </div>
      </div>
    </div>
    <div class="reveal">
      <form class="booking-form" id="bookingForm" onsubmit="submitForm(event)">
        <div class="form-row">
          <div class="form-group">
            <label>Prénom</label>
            <input type="text" placeholder="Votre prénom" required>
          </div>
          <div class="form-group">
            <label>Nom</label>
            <input type="text" placeholder="Votre nom" required>
          </div>
        </div>
        <div class="form-group">
          <label>Email</label>
          <input type="email" placeholder="votre@email.com" required>
        </div>
        <div class="form-group">
          <label>Téléphone</label>
          <input type="tel" placeholder="+33 X XX XX XX XX">
        </div>
        <div class="form-group">
          <label>Type de prestation</label>
          <select required>
            <option value="" disabled selected>Choisissez un service</option>
            <option>🎵 Pack Artiste (600€ – 1 200€)</option>
            <option>🚀 Pack Full Créatif (1 500€ – 3 800€)</option>
            <option>🎉 Pack Événement (450€ – 900€)</option>
            <option>🎙️ Location studio à l'heure</option>
            <option>🎬 Clip vidéo uniquement</option>
            <option>💃 Prestation danse uniquement</option>
            <option>Autre / Sur mesure</option>
          </select>
        </div>
        <div class="form-group">
          <label>Décrivez votre projet</label>
          <textarea placeholder="Parlez-nous de votre projet, vos idées, votre date souhaitée..."></textarea>
        </div>
        <button type="submit" class="form-submit">Envoyer ma demande →</button>
        <div class="success-msg" id="successMsg">
          ✦ Votre demande a bien été envoyée. Nous vous répondons sous 24h !
        </div>
      </form>
    </div>
  </div>
</section>

<!-- FOOTER -->

<footer>
  <div class="footer-top">
    <div class="footer-logo">OGM</div>
    <ul class="footer-links">
      <li><a href="#services">Services</a></li>
      <li><a href="#packages">Packages</a></li>
      <li><a href="#portfolio">Portfolio</a></li>
      <li><a href="#booking">Contact</a></li>
    </ul>
  </div>
  <div class="footer-bottom">
    <p class="footer-copy">© 2026 <span>OGM Studio</span>. Tous droits réservés.</p>
    <div class="social-links">
      <a href="#" class="social-link">ig</a>
      <a href="#" class="social-link">tk</a>
      <a href="#" class="social-link">yt</a>
      <a href="#" class="social-link">fb</a>
    </div>
  </div>
</footer>

<script>
  // Custom cursor
  const cursor = document.getElementById('cursor');
  const ring = document.getElementById('cursorRing');
  let mx = 0, my = 0, rx = 0, ry = 0;

  document.addEventListener('mousemove', e => {
    mx = e.clientX; my = e.clientY;
    cursor.style.left = mx + 'px';
    cursor.style.top = my + 'px';
  });

  function animateRing() {
    rx += (mx - rx) * 0.12;
    ry += (my - ry) * 0.12;
    ring.style.left = rx + 'px';
    ring.style.top = ry + 'px';
    requestAnimationFrame(animateRing);
  }
  animateRing();

  document.querySelectorAll('a, button, .service-card, .pkg-card, .portfolio-item').forEach(el => {
    el.addEventListener('mouseenter', () => {
      ring.style.transform = 'translate(-50%, -50%) scale(2)';
      ring.style.borderColor = 'rgba(201,168,76,0.8)';
    });
    el.addEventListener('mouseleave', () => {
      ring.style.transform = 'translate(-50%, -50%) scale(1)';
      ring.style.borderColor = 'rgba(201,168,76,0.5)';
    });
  });

  // Scroll reveal
  const reveals = document.querySelectorAll('.reveal');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
      if (entry.isIntersecting) {
        setTimeout(() => {
          entry.target.classList.add('visible');
        }, (Array.from(reveals).indexOf(entry.target) % 4) * 100);
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.1 });

  reveals.forEach(el => observer.observe(el));

  // Form submit
  function submitForm(e) {
    e.preventDefault();
    const btn = document.querySelector('.form-submit');
    btn.textContent = 'Envoi en cours...';
    btn.disabled = true;
    setTimeout(() => {
      document.getElementById('bookingForm').style.display = 'none';
      document.getElementById('successMsg').style.display = 'block';
    }, 1200);
  }

  // Smooth scroll
  document.querySelectorAll('a[href^="#"]').forEach(a => {
    a.addEventListener('click', e => {
      e.preventDefault();
      const target = document.querySelector(a.getAttribute('href'));
      if (target) target.scrollIntoView({ behavior: 'smooth' });
    });
  });
</script>

</body>
</html>
