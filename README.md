<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Aufklärung Suchtverhalten</title>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
:root {
  --bg:#f7f9fc;
  --card:#ffffff;
  --text:#1f2937;
  --muted:#6b7280;
  --accent:#2563eb;
  --accent-soft:#e0e7ff;
}
* {box-sizing:border-box;margin:0;padding:0;transition:all 0.3s ease}
body {font-family:'Inter',sans-serif;background:var(--bg);color:var(--text);line-height:1.7;overflow-x:hidden}
header {position:fixed;top:0;width:100%;z-index:1000;background:rgba(255,255,255,.95);backdrop-filter:blur(12px);border-bottom:1px solid #e5e7eb;transition:background .3s}
nav {max-width:1200px;margin:auto;display:flex;justify-content:flex-end;gap:1.5rem;padding:0.8rem 1rem}
nav a {color:var(--muted);text-decoration:none;font-weight:500;position:relative}
nav a::after {content:'';position:absolute;left:0;bottom:-4px;width:0;height:2px;background:var(--accent);transition:.3s}
nav a:hover {color:var(--accent)}
nav a:hover::after {width:100%}
.container {max-width:900px;margin:100px auto 80px auto;padding:0 1rem}
section {display:none;background:var(--card);border-radius:20px;padding:3rem 2.5rem;box-shadow:0 20px 40px rgba(0,0,0,.06);animation:fade .8s ease}
section.active {display:block}
@keyframes fade {from{opacity:0;transform:translateY(30px)}to{opacity:1;transform:none}}
h2{font-size:2rem;margin-bottom:1.5rem;color:var(--accent);transition:color .3s}
h3{margin-top:2.5rem;margin-bottom:.8rem;color:#1e40af;transition:color .3s}
p{margin-bottom:1rem;color:#374151;transition:color .3s}
ul{padding-left:1.2rem;margin-bottom:1.2rem}
li{margin-bottom:.6rem}
.card{background:var(--accent-soft);border-radius:14px;padding:1.5rem;margin:1.5rem 0;transition:transform .3s,background .3s}
.card:hover{transform:translateY(-5px);box-shadow:0 20px 40px rgba(0,0,0,.15)}
blockquote{border-left:4px solid var(--accent);padding-left:1rem;color:#1e3a8a;margin:1.5rem 0;transition:color .3s}
footer{background:#111827;color:#e5e7eb;text-align:center;padding:2rem 1rem;transition:background .3s,color .3s}
footer p{font-size:.9rem}
@media(max-width:700px){section{padding:2rem 1.5rem}}
/* Dark Mode */
body.dark {--bg:#0f172a;--card:#020617;--text:#ffffff;--muted:#94a3b8;--accent:#60a5fa;--accent-soft:#1e293b}
body.dark header {background:rgba(2,6,23,.95)}
body.dark footer {background:#020617}
.toggle{position:fixed;right:16px;bottom:16px;background:var(--accent);color:#fff;border:none;border-radius:999px;padding:.7rem 1rem;font-size:.9rem;cursor:pointer;box-shadow:0 10px 20px rgba(0,0,0,.25)}
/* Diagramme */
.chart{margin:2rem 0}
.bar{height:32px;background:#c7d2fe;border-radius:999px;margin:1rem 0;position:relative;width:0%;transition:width 1.5s ease, background .3s}
.bar span{position:absolute;left:12px;top:6px;font-size:.9rem;font-weight:600;color:#1e3a8a;transition:color .3s}
.bar:hover{background:var(--accent);cursor:pointer}
</style>
</head>
<body>
<div id="progress"></div>
<header>
<nav>
<a onclick="show('start')">Start</a>
<a onclick="show('arten')">Suchtarten</a>
<a onclick="show('warnsignale')">Warnsignale</a>
<a onclick="show('selbsttest')">Selbsttest</a>
<a onclick="show('ausstieg')">Ausstieg</a>
<a onclick="show('praevention')">Prävention</a>
<a onclick="show('quellen')">Quellen</a>
<a onclick="show('handlungsplan')">Handlungsplan</a>
<a onclick="show('hilfe')">Hilfe</a>
<a href="https://jadedimp6654.github.io" target="_blank">Externer Link</a>
</nav>
</header>
<div class="container">
<section id="start" class="active">
<h2>Startseite & Einführung</h2>
<p>Willkommen zur interaktiven Informationsplattform über Suchtverhalten. Alles hier ist animiert, dynamisch und interaktiv gestaltet.</p>
<p>Entdecken Sie die Seiten, klicken Sie auf Diagramme, interagieren Sie mit dem Selbsttest, und lernen Sie Schritt für Schritt.</p>
<p>Die Website bietet fundierte Inhalte über stoffgebundene und Verhaltenssüchte, mit wissenschaftlich belegten Informationen.</p>
<p>Sie können jederzeit in den Dark Mode wechseln und sehen, wie sich Farben, Text und Diagramme dynamisch anpassen.</p>
</section>
<section id="arten">
<h2>Suchtarten</h2>
<h3>Stoffgebundene Süchte</h3>
<p>Alkohol, Nikotin, Medikamente und Drogen wirken direkt auf das Belohnungssystem des Gehirns und können zu physischer und psychischer Abhängigkeit führen.</p>
<p>Jede Substanz hat spezifische Risiken, Nebenwirkungen und Rückfallwahrscheinlichkeiten. Animierte Diagramme auf dieser Seite zeigen die relativen Risiken.</p>
<h3>Verhaltenssüchte</h3>
<p>Gaming, Social Media, Glücksspiel, Kaufsucht und Arbeitssucht beeinflussen das Belohnungssystem ähnlich stark wie Drogen.</p>
<p>Hier gibt es interaktive Grafiken, die beim Scrollen wachsen und beim Hovern Details anzeigen.</p>
</section>
<section id="warnsignale">
<h2>Warnsignale erkennen</h2>
<p>Erkennen Sie Warnsignale frühzeitig. Scrollen Sie nach unten, um die Balkendiagramme zu animieren.</p>
<div class="card">
<h3>Statistische Übersicht</h3>
<div class="chart">
<div class="bar" data-value="72"><span>Alkohol</span></div>
<div class="bar" data-value="58"><span>Nikotin</span></div>
<div class="bar" data-value="46"><span>Gaming</span></div>
<div class="bar" data-value="39"><span>Social Media</span></div>
<div class="bar" data-value="22"><span>Glücksspiel</span></div>
</div>
<p>Hover über die Balken, um mehr Details zu sehen. Die Balken bauen sich beim Scrollen dynamisch auf.</p>
</div>
</section>
<section id="selbsttest">
<h2>Interaktiver Selbsttest</h2>
<div class="card">
<form id="testForm">
<p>1. Denkst du häufig an eine Substanz oder ein Verhalten?</p>
<label><input type="radio" name="q1" value="2"> Ja</label><br>
<label><input type="radio" name="q1" value="1"> Manchmal</label><br>
<label><input type="radio" name="q1" value="0"> Nein</label>
<p>2. Hast du versucht zu reduzieren?</p>
<label><input type="radio" name="q2" value="2"> Mehrmals ohne Erfolg</label><br>
<label><input type="radio" name="q2" value="1"> Einmal</label><br>
<label><input type="radio" name="q2" value="0"> Nie</label>
<p>3. Vernachlässigst du Verpflichtungen?</p>
<label><input type="radio" name="q3" value="2"> Häufig</label><br>
<label><input type="radio" name="q3" value="1"> Gelegentlich</label><br>
<label><input type="radio" name="q3" value="0"> Nie</label>
<p>4. Erlebst du Unruhe ohne Konsum?</p>
<label><input type="radio" name="q4" value="2"> Stark</label><br>
<label><input type="radio" name="q4" value="1"> Leicht</label><br>
<label><input type="radio" name="q4" value="0"> Gar nicht</label>
<p>5. Konsumierst du trotz negativer Folgen?</p>
<label><input type="radio" name="q5" value="2"> Ja</label><br>
<label><input type="radio" name="q5" value="1"> Unsicher</label><br>
<label><input type="radio" name="q5" value="0"> Nein</label>
<button type="button" onclick="auswerten()">Auswerten</button>
</form>
<p id="ergebnis"></p>
</div>
</section>
<section id="ausstieg"><h2>Wege aus der Sucht</h2><p>Therapie, Selbsthilfe und kleine Schritte.</p></section>
<section id="praevention"><h2>Prävention</h2><p>Aufklärung, soziale Kompetenz, Resilienz.</p></section>
<section id="quellen"><h2>Quellen & Studien</h2><ul><li>WHO</li><li>BZgA</li><li>DHS</li><li>RKI</li><li>EMCDDA</li></ul></section>
<section id="handlungsplan"><h2>Handlungsplan</h2><p>Anerkennen, informieren, Unterstützung, kleine Schritte, Rückfälle verstehen.</p></section>
<section id="hilfe"><h2>Hilfe & Unterstützung</h2><p>Beratungsstellen, Hotlines, Online-Angebote.</p></section>
</div>
<footer><p>&copy; 2026 Darian Müller · Aufklärung über Suchtverhalten</p></footer>
<button class="toggle" onclick="toggleDark()">Dark Mode</button>
<script>
function show(id){document.querySelectorAll('section').forEach(s=>s.classList.remove('active'));document.getElementById(id).classList.add('active');window.scrollTo({top:0,behavior:'smooth'});}
window.addEventListener('scroll',()=>{const h=document.documentElement;const sc=(h.scrollTop)/(h.scrollHeight-h.clientHeight)*100;document.getElementById('progress').style.width=sc+'%'});
function toggleDark(){document.body.classList.toggle('dark');}
const bars=document.querySelectorAll('.bar');
const observer=new IntersectionObserver(entries=>{entries.forEach(e=>{if(e.isIntersecting){const val=e.target.getAttribute('data-value');e.target.style.width=val+'%';}});},{threshold:.6});
bars.forEach(b=>observer.observe(b));
function auswerten(){let score=0;for(let i=1;i<=5;i++){const q=document.querySelector('input[name=q'+i+']:checked');if(q) score+=parseInt(q.value);}const out=document.getElementById('ergebnis');if(score<=3){out.innerText='Geringes Risiko: Kaum Anzeichen.'}else if(score<=6){out.innerText='Mittleres Risiko: Erste Warnsignale erkennbar.'}else{out.innerText='Erhöhtes Risiko: Professionelle Beratung empfohlen.'}}
</script>
</body>
</html>
