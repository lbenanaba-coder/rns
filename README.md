<!DOCTYPE html>

<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Accueil — Productivité Entrepôt</title>
<link href="https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800;900&family=Open+Sans:wght@400;500;600&display=swap" rel="stylesheet">
<style>
:root {
--auchan-red: #e2001a;
--auchan-orange: #f07800;
--green: #3da84a;
--green-light: #e8f6ea;
--blue: #2a7fc1;
--blue-light: #deeef8;
--bg: #f0f4f8;
--white: #ffffff;
--card-shadow: 0 2px 12px rgba(0,0,0,0.08);
--card-shadow-hover: 0 6px 24px rgba(0,0,0,0.13);
--text: #1a2533;
--muted: #6b7a8d;
--border: #dde3ea;
--prev-bg: #eaf4fb;
--prev-border: #2a7fc1;
--real-bg: #e8f6ea;
--real-border: #3da84a;
--budget-bg: #fff8e6;
--budget-border: #f0a500;
}

- { margin: 0; padding: 0; box-sizing: border-box; }

body {
background: var(–bg);
color: var(–text);
font-family: ‘Open Sans’, sans-serif;
min-height: 100vh;
}

/* ── TOP NAV ── */
.topnav {
background: var(–white);
border-bottom: 2px solid var(–border);
padding: 0 32px;
display: flex;
align-items: center;
justify-content: space-between;
height: 56px;
box-shadow: 0 1px 6px rgba(0,0,0,0.06);
}

.brand {
display: flex;
align-items: center;
gap: 10px;
}

.brand-logo {
font-family: ‘Nunito’, sans-serif;
font-weight: 900;
font-size: 22px;
color: var(–auchan-red);
letter-spacing: -0.5px;
}

.brand-logo span { color: var(–auchan-orange); }

.brand-site {
font-size: 13px;
font-weight: 700;
color: var(–text);
background: var(–bg);
border: 1px solid var(–border);
border-radius: 6px;
padding: 3px 10px;
letter-spacing: 0.03em;
}

.nav-tabs {
display: flex;
align-items: center;
gap: 4px;
height: 100%;
}

.nav-tab {
display: flex;
align-items: center;
gap: 6px;
padding: 0 16px;
height: 100%;
font-size: 13px;
font-weight: 600;
color: var(–muted);
cursor: pointer;
border-bottom: 3px solid transparent;
transition: color 0.2s, border-color 0.2s;
position: relative;
text-decoration: none;
white-space: nowrap;
}

.nav-tab:hover { color: var(–blue); }

.nav-tab.active {
color: var(–blue);
border-bottom-color: var(–blue);
}

.nav-tab .tab-icon { font-size: 14px; }
.nav-tab .chevron { font-size: 10px; opacity: 0.6; }

/* dropdown */
.dropdown { position: relative; }

.dropdown-menu {
display: none;
position: absolute;
top: calc(100% + 2px);
left: 0;
background: var(–white);
border: 1px solid var(–border);
border-radius: 10px;
box-shadow: 0 8px 24px rgba(0,0,0,0.12);
z-index: 100;
overflow: hidden;
min-width: 180px;
}

.dropdown:hover .dropdown-menu { display: block; }

.dropdown-menu a {
display: flex;
align-items: center;
gap: 10px;
padding: 10px 18px;
font-size: 13px;
color: var(–text);
text-decoration: none;
transition: background 0.15s;
font-weight: 500;
}

.dropdown-menu a:hover { background: var(–bg); color: var(–blue); }
.dropdown-menu a .dm-icon { font-size: 14px; }

/* ── WRAPPER ── */
.wrapper {
max-width: 1080px;
margin: 0 auto;
padding: 36px 24px 56px;
}

/* ── HERO ── */
.hero {
background: var(–white);
border-radius: 18px;
padding: 36px 40px;
box-shadow: var(–card-shadow);
margin-bottom: 28px;
display: flex;
align-items: center;
gap: 32px;
border-left: 5px solid var(–auchan-red);
animation: fadeUp 0.5s ease both;
}

.hero-icon-wrap {
flex-shrink: 0;
width: 72px; height: 72px;
background: linear-gradient(135deg, #fde8e8, #fff2e0);
border-radius: 18px;
display: flex; align-items: center; justify-content: center;
font-size: 34px;
}

.hero-text h1 {
font-family: ‘Nunito’, sans-serif;
font-size: 26px;
font-weight: 900;
color: var(–text);
margin-bottom: 8px;
}

.hero-text h1 em {
font-style: normal;
color: var(–auchan-red);
}

.hero-text p {
font-size: 14px;
color: var(–muted);
line-height: 1.7;
max-width: 580px;
}

/* ── KPI STRIP ── */
.kpi-strip {
display: grid;
grid-template-columns: repeat(3, 1fr);
gap: 16px;
margin-bottom: 28px;
animation: fadeUp 0.5s 0.1s ease both;
}

.kpi-card {
background: var(–white);
border-radius: 14px;
padding: 20px 24px;
box-shadow: var(–card-shadow);
display: flex;
align-items: center;
gap: 16px;
border-top: 3px solid transparent;
transition: box-shadow 0.2s, transform 0.2s;
}

.kpi-card:hover { box-shadow: var(–card-shadow-hover); transform: translateY(-2px); }
.kpi-card.prev { border-top-color: var(–prev-border); }
.kpi-card.real { border-top-color: var(–real-border); }
.kpi-card.budget{ border-top-color: var(–budget-border); }

.kpi-dot {
width: 42px; height: 42px;
border-radius: 12px;
display: flex; align-items: center; justify-content: center;
font-size: 20px;
flex-shrink: 0;
}

.kpi-card.prev .kpi-dot { background: var(–prev-bg); }
.kpi-card.real .kpi-dot { background: var(–real-bg); }
.kpi-card.budget .kpi-dot { background: var(–budget-bg); }

.kpi-label {
font-size: 11px;
font-weight: 700;
letter-spacing: 0.1em;
text-transform: uppercase;
color: var(–muted);
margin-bottom: 3px;
}

.kpi-desc { font-size: 13px; font-weight: 600; color: var(–text); }

/* ── SECTION TITLE ── */
.sec-title {
font-family: ‘Nunito’, sans-serif;
font-size: 13px;
font-weight: 800;
letter-spacing: 0.1em;
text-transform: uppercase;
color: var(–muted);
margin-bottom: 14px;
}

/* ── PAGES GRID ── */
.pages-grid {
display: grid;
grid-template-columns: repeat(3, 1fr);
gap: 16px;
margin-bottom: 28px;
animation: fadeUp 0.5s 0.2s ease both;
}

.page-card {
background: var(–white);
border-radius: 14px;
padding: 22px;
box-shadow: var(–card-shadow);
transition: box-shadow 0.2s, transform 0.2s;
border-bottom: 3px solid transparent;
}

.page-card:hover { box-shadow: var(–card-shadow-hover); transform: translateY(-3px); }

.page-card:nth-child(1) { border-bottom-color: #2a7fc1; }
.page-card:nth-child(2) { border-bottom-color: #3da84a; }
.page-card:nth-child(3) { border-bottom-color: #9b59b6; }
.page-card:nth-child(4) { border-bottom-color: #e74c3c; }
.page-card:nth-child(5) { border-bottom-color: #f07800; }

.page-header {
display: flex;
align-items: center;
gap: 10px;
margin-bottom: 12px;
}

.page-emoji {
width: 38px; height: 38px;
border-radius: 10px;
background: var(–bg);
display: flex; align-items: center; justify-content: center;
font-size: 18px;
flex-shrink: 0;
}

.page-card h3 {
font-family: ‘Nunito’, sans-serif;
font-size: 15px;
font-weight: 800;
color: var(–text);
}

.page-card p {
font-size: 12.5px;
color: var(–muted);
line-height: 1.65;
margin-bottom: 14px;
}

.tags { display: flex; flex-wrap: wrap; gap: 6px; }

.tag {
font-size: 11px;
font-weight: 600;
padding: 3px 9px;
border-radius: 100px;
background: var(–bg);
color: var(–muted);
border: 1px solid var(–border);
}

/* ── GUIDE ── */
.guide {
background: var(–white);
border-radius: 14px;
padding: 28px 32px;
box-shadow: var(–card-shadow);
margin-bottom: 28px;
animation: fadeUp 0.5s 0.3s ease both;
}

.guide h2 {
font-family: ‘Nunito’, sans-serif;
font-size: 18px;
font-weight: 900;
margin-bottom: 22px;
color: var(–text);
}

.steps {
display: grid;
grid-template-columns: repeat(4, 1fr);
gap: 20px;
}

.step {
position: relative;
padding-left: 0;
}

.step-num-wrap {
display: flex;
align-items: center;
gap: 10px;
margin-bottom: 10px;
}

.step-num {
width: 32px; height: 32px;
border-radius: 50%;
background: linear-gradient(135deg, var(–auchan-red), var(–auchan-orange));
color: white;
font-family: ‘Nunito’, sans-serif;
font-size: 14px;
font-weight: 900;
display: flex; align-items: center; justify-content: center;
flex-shrink: 0;
}

.step h4 {
font-size: 13px;
font-weight: 700;
color: var(–text);
}

.step p {
font-size: 12.5px;
color: var(–muted);
line-height: 1.6;
}

/* ── LEGEND ── */
.legend-row {
display: grid;
grid-template-columns: repeat(3, 1fr);
gap: 14px;
animation: fadeUp 0.5s 0.4s ease both;
}

.legend-card {
background: var(–white);
border-radius: 12px;
padding: 18px 20px;
box-shadow: var(–card-shadow);
display: flex;
gap: 14px;
align-items: flex-start;
}

.legend-stripe {
width: 4px;
border-radius: 4px;
align-self: stretch;
flex-shrink: 0;
}

.legend-card h4 {
font-family: ‘Nunito’, sans-serif;
font-size: 14px;
font-weight: 800;
margin-bottom: 4px;
}

.legend-card p { font-size: 12px; color: var(–muted); line-height: 1.55; }

/* ── FOOTER ── */
.footer {
margin-top: 40px;
display: flex;
justify-content: space-between;
align-items: center;
font-size: 12px;
color: var(–muted);
animation: fadeUp 0.5s 0.5s ease both;
}

.footer-live {
display: flex; align-items: center; gap: 6px;
}

.live-dot {
width: 7px; height: 7px;
background: var(–green);
border-radius: 50%;
animation: pulse 2s infinite;
}

@keyframes pulse {
0%,100% { opacity:1; }
50% { opacity: 0.35; }
}

@keyframes fadeUp {
from { opacity:0; transform:translateY(18px); }
to { opacity:1; transform:translateY(0); }
}

@media(max-width:720px){
.pages-grid, .steps { grid-template-columns: 1fr 1fr; }
.kpi-strip, .legend-row { grid-template-columns: 1fr; }
.hero { flex-direction: column; gap: 16px; }
.nav-tabs { display: none; }
}
</style>

</head>
<body>

<!-- ── CONTENT ── -->

<div class="wrapper">

<!-- HERO -->

<div class="hero">
<div class="hero-icon-wrap">📦</div>
<div class="hero-text">
<h1>Bienvenue sur le dashboard <em>Productivité</em></h1>
<p>
Ce tableau de bord vous permet de suivre en temps réel la performance de vos entrepôts logistiques,
d'anticiper les besoins en ressources humaines et de comparer les réalisations aux objectifs
<strong>Prévisionnels</strong> et au <strong>Budget</strong> annuel.
</p>
</div>
</div>

<!-- KPI STRIP -->

<div class="kpi-strip">
<div class="kpi-card prev">
<div class="kpi-dot">🔵</div>
<div>
<div class="kpi-label">Prévisionnel</div>
<div class="kpi-desc">Objectifs calculés selon le volume et la productivité cibles</div>
</div>
</div>
<div class="kpi-card real">
<div class="kpi-dot">🟢</div>
<div>
<div class="kpi-label">Réalisé</div>
<div class="kpi-desc">Données opérationnelles réelles extraites du SI entrepôt</div>
</div>
</div>
<div class="kpi-card budget">
<div class="kpi-dot">🟡</div>
<div>
<div class="kpi-label">Budget</div>
<div class="kpi-desc">Référence posée lors de la construction budgétaire annuelle</div>
</div>
</div>
</div>

<!-- PAGES -->

<p class="sec-title">📄 Les pages disponibles</p>
<div class="pages-grid">

```
<div class="page-card">
<div class="page-header">
<div class="page-emoji">🔍</div>
<h3>Synthèse Globale</h3>
</div>
<p>Vue consolidée de la productivité et des ECS. Comparez d'un coup d'œil le Prévisionnel, le Réalisé et le Budget sur la période sélectionnée.</p>
<div class="tags">
<span class="tag">ECS</span>
<span class="tag">PROD TTE</span>
<span class="tag">PROD VAR</span>
</div>
</div>

<div class="page-card">
<div class="page-header">
<div class="page-emoji">📦</div>
<h3>Prépa Stock</h3>
</div>
<p>Suivi détaillé de l'activité de préparation de stock : volumes traités, productivité par opérateur et écarts vs objectifs.</p>
<div class="tags">
<span class="tag">Colis/h</span>
<span class="tag">Écart budget</span>
</div>
</div>

<div class="page-card">
<div class="page-header">
<div class="page-emoji">🚛</div>
<h3>Transit</h3>
</div>
<p>Analyse des flux de transit entre entrepôts. Suivi des volumes et de la performance logistique sur les mouvements internes.</p>
<div class="tags">
<span class="tag">Flux</span>
<span class="tag">Volume</span>
</div>
</div>

<div class="page-card">
<div class="page-header">
<div class="page-emoji">📤</div>
<h3>Expédition</h3>
</div>
<p>Pilotage des sorties entrepôt : nombre de colis expédiés, productivité des équipes et comparaison aux prévisions hebdomadaires.</p>
<div class="tags">
<span class="tag">Sorties</span>
<span class="tag">Planification</span>
</div>
</div>

<div class="page-card">
<div class="page-header">
<div class="page-emoji">📥</div>
<h3>Réception</h3>
</div>
<p>Suivi des entrées marchandises : volumes réceptionnés, délais de traitement et productivité des équipes de réception.</p>
<div class="tags">
<span class="tag">Entrées</span>
<span class="tag">Délais</span>
</div>
</div>
```

</div>

<!-- GUIDE -->

<div class="guide">
<h2>🚀 Comment utiliser ce dashboard ?</h2>
<div class="steps">
<div class="step">
<div class="step-num-wrap">
<div class="step-num">1</div>
<h4>Choisissez l'entrepôt</h4>
</div>
<p>Sélectionnez <strong>Nîmes 12</strong> ou <strong>Nîmes 3</strong> dans le menu de navigation en haut.</p>
</div>
<div class="step">
<div class="step-num-wrap">
<div class="step-num">2</div>
<h4>Filtrez la période</h4>
</div>
<p>Utilisez le sélecteur de dates pour analyser une semaine, un mois ou une période personnalisée.</p>
</div>
<div class="step">
<div class="step-num-wrap">
<div class="step-num">3</div>
<h4>Naviguez par activité</h4>
</div>
<p>Explorez les pages <strong>Prépa Stock</strong>, <strong>Transit</strong>, <strong>Expédition</strong> ou <strong>Réception</strong> selon votre besoin.</p>
</div>
<div class="step">
<div class="step-num-wrap">
<div class="step-num">4</div>
<h4>Analysez les écarts</h4>
</div>
<p>Comparez <strong>Réalisé vs Budget</strong> et <strong>Réalisé vs Prévisionnel</strong> pour piloter vos actions correctives.</p>
</div>
</div>
</div>

<!-- LEGEND -->

<p class="sec-title">📌 Légende des indicateurs clés</p>
<div class="legend-row">
<div class="legend-card">
<div class="legend-stripe" style="background:#2a7fc1"></div>
<div>
<h4 style="color:#2a7fc1">ECS (Equivalent Colis Standard)</h4>
<p>Unité de mesure du volume de travail normalisé, permettant de comparer des activités de nature différente.</p>
</div>
</div>
<div class="legend-card">
<div class="legend-stripe" style="background:#3da84a"></div>
<div>
<h4 style="color:#3da84a">PROD TTE (Productivité Toutes Tâches)</h4>
<p>Productivité globale calculée sur l'ensemble des heures travaillées, toutes activités confondues.</p>
</div>
</div>
<div class="legend-card">
<div class="legend-stripe" style="background:#f07800"></div>
<div>
<h4 style="color:#f07800">PROD VAR (Productivité Variable)</h4>
<p>Productivité calculée uniquement sur les heures directement liées aux opérations de manutention variable.</p>
</div>
</div>
</div>

<!-- FOOTER -->

<div class="footer">
<p>© RNS Campus Saint Cesaire — Tableau de bord Productivité Entrepôt</p>
<div class="footer-live">
<div class="live-dot"></div>
Données actualisées automatiquement
</div>
</div>

</div>
</body>
</html>
