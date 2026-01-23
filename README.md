<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Suchtaufklärung – Information & Hilfe</title>
  <link href="https://fonts.googleapis.com" rel="stylesheet">
  <style>
    /* Design-System & Variablen */
    :root {
      --bg-gradient: radial-gradient(circle at top right, #1e293b, #030712);
      --glass-bg: rgba(15, 23, 42, 0.8);
      --card-bg: rgba(30, 41, 59, 0.6);
      --text-main: #f8fafc;
      --text-muted: #94a3b8;
      --primary: #6ea8ff;
      --secondary: #7af0d1;
      --border: rgba(255, 255, 255, 0.1);
    }

    [data-theme="light"] {
      --bg-gradient: radial-gradient(circle at top right, #f1f5f9, #e2e8f0);
      --glass-bg: rgba(255, 255, 255, 0.8);
      --card-bg: rgba(255, 255, 255, 0.5);
      --text-main: #0f172a;
      --text-muted: #475569;
      --primary: #2563eb;
      --secondary: #0d9488;
      --border: rgba(0, 0, 0, 0.05);
    }

    * { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      font-family: 'Inter', sans-serif;
      background: var(--bg-gradient);
      background-attachment: fixed;
      color: var(--text-main);
      line-height: 1.6;
      overflow-x: hidden;
      padding-top: 80px;
      transition: background 0.4s ease, color 0.4s ease;
    }

    /* Header & Navigation */
    header {
      position: fixed;
      top: 0; width: 100%; height: 70px;
      display: flex; justify-content: space-between; align-items: center;
      padding: 0 5%;
      background: var(--glass-bg);
      backdrop-filter: blur(15px);
      z-index: 1000;
      border-bottom: 1px solid var(--border);
    }

    header h1 { 
      font-weight: 800; font-size: 1.4rem; 
      background: linear-gradient(to right, var(--primary), var(--secondary)); 
      -webkit-background-clip: text; -webkit-text-fill-color: transparent;
      cursor: pointer; /* Zeigt, dass es anklickbar ist */
      user-select: none;
    }

    .nav-container { display: flex; align-items: center; gap: 20px; }
    
    nav { display: flex; gap: 15px; }
    nav a { text-decoration: none; color: var(--text-main); font-weight: 500; font-size: 0.85rem; cursor: pointer; opacity: 0.7; transition: 0.3s; }
    nav a:hover { opacity: 1; color: var(--primary); }

    #theme-toggle {
      background: none; border: 1px solid var(--border);
      color: var(--text-main); padding: 6px 12px; border-radius: 8px;
      cursor: pointer; font-size: 1rem; transition: 0.3s;
    }

    .menu-toggle { display: none; flex-direction: column; gap: 6px; cursor: pointer; border: none; background: none; }
    .menu-toggle span { width: 25px; height: 2px; background: var(--text-main); border-radius: 2px; }

    .container { max-width: 1100px; margin: 0 auto; padding: 20px; }
    section { display: none; animation: fadeIn 0.4s ease forwards; }
    section.active { display: block; }

    @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }

    h2 { font-size: 2.2rem; font-weight: 800; margin-bottom: 15px; letter-spacing: -1px; }
    .subtitle { color: var(--text-muted); margin-bottom: 35px; font-size: 1.1rem; }

    .grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 20px; }
    .card { 
      background: var(--card-bg); padding: 25px; border-radius: 20px; 
      border: 1px solid var(--border); transition: 0.3s ease;
      box-shadow: 0 4px 6px rgba(0,0,0,0.05);
    }
    .card:hover { transform: translateY(-5px); border-color: var(--primary); background: var(--glass-bg); }
    .card h3 { color: var(--primary); margin-bottom: 12px; font-size: 1.2rem; }

    .test-box { background: var(--card-bg); padding: 30px; border-radius: 24px; max-width: 550px; margin: 0 auto; border: 1px solid var(--border); }
    .question { margin-bottom: 25px; }
    label { display: block; margin-bottom: 8px; font-weight: 600; font-size: 0.95rem; }
    input[type=range] { width: 100%; accent-color: var(--primary); cursor: pointer; }

    .btn-action { 
      width: 100%; padding: 14px; border-radius: 12px; border: none; 
      background: linear-gradient(90deg, var(--primary), var(--secondary)); 
      color: #fff; font-weight: 700; cursor: pointer; transition: 0.3s; margin-top: 15px;
    }

    #result { margin-top: 20px; padding: 15px; border-radius: 10px; text-align: center; font-weight: 600; display: none; }

    @media (max-width: 950px) {
      .menu-toggle { display: flex; order: 3; }
      nav {
        position: fixed; top: 70px; left: -100%; width: 100%; height: calc(100vh - 70px);
        background: var(--glass-bg); backdrop-filter: blur(20px); flex-direction: column; 
        align-items: center; padding-top: 40px; transition: 0.4s ease;
      }
      nav.active { left: 0; }
      nav a { font-size: 1.3rem; padding: 10px; }
      #theme-toggle { order: 2; margin-left: auto; margin-right: 15px; }
    }
  </style>
</head>
<body data-theme="dark">

<header>
  <!-- Überschrift führt jetzt zur Startseite -->
  <h1 onclick="showPage('start')">Suchtaufklärung</h1>
  
  <div class="nav-container">
    <button id="theme-toggle" onclick="toggleTheme()">🌓</button>
    
    <button class="menu-toggle" onclick="toggleMenu()">
      <span></span><span></span><span></span>
    </button>

    <nav id="mainNav">
      <a onclick="showPage('start')">Start</a>
      <a onclick="showPage('test')">Selbsttest</a>
      <a onclick="showPage('alkohol')">Alkohol</a>
      <a onclick="showPage('drogen')">Drogen</a>
      <a onclick="showPage('medien')">Medien</a>
      <a onclick="showPage('gluecksspiel')">Glücksspiel</a>
      <a onclick="showPage('hilfe')">Hilfe</a>
    </nav>
  </div>
</header>

<main class="container">
  
  <section id="start" class="active">
    <h2>Wissen ist Schutz.</h2>
    <p class="subtitle">Informiere dich über Abhängigkeiten und finde Wege zu einem bewussten Leben. Wir klären auf – sachlich und modern.</p>
    <div class="grid">
      <div class="card">
        <h3>Prävention</h3>
        <p>Erkenne Warnsignale frühzeitig. Sucht beginnt oft schleichend und unbemerkt im Alltag.</p>
      </div>
      <div class="card">
        <h3>Selbsttest</h3>
        <p>Nutze unsere interaktiven Fragen, um dein eigenes Konsumverhalten anonym zu prüfen.</p>
      </div>
    </div>
  </section>

  <section id="test">
    <h2>Selbsttest</h2>
    <p class="subtitle">Ehrliche Antworten helfen dir, dein Risiko besser einzuschätzen.</p>
    <div class="test-box">
      <div class="question">
        <label>Gedanken an den Konsum im Alltag:</label>
        <input type="range" id="q1" min="0" max="10" value="0">
      </div>
      <div class="question">
        <label>Vernachlässigung von Pflichten/Hobbys:</label>
        <input type="range" id="q2" min="0" max="10" value="0">
      </div>
      <div class="question">
        <label>Heimlicher Konsum oder Verstecken:</label>
        <input type="range" id="q3" min="0" max="10" value="0">
      </div>
      <button class="btn-action" onclick="evaluateTest()">Auswerten</button>
      <div id="result"></div>
    </div>
  </section>

  <section id="alkohol">
    <h2>Alkohol</h2>
    <div class="grid">
      <div class="card"><h3>Gesundheit</h3><p>Alkohol schädigt fast jedes Organ, besonders Leber und Gehirn.</p></div>
      <div class="card"><h3>Abhängigkeit</h3><p>Regelmäßigkeit ist das größte Warnsignal für eine schleichende Sucht.</p></div>
    </div>
  </section>

  <section id="drogen">
    <h2>Drogen</h2>
    <div class="grid">
      <div class="card"><h3>Risiken</h3><p>Illegale Substanzen bergen unvorhersehbare Gefahren für die Psyche.</p></div>
      <div class="card"><h3>Hilfe</h3><p>Ein Ausstieg ist jederzeit möglich – mit der richtigen Unterstützung.</p></div>
    </div>
  </section>

  <section id="medien">
    <h2>Mediensucht</h2>
    <div class="grid">
      <div class="card"><h3>Social Media</h3><p>Ständiger Vergleich mit anderen kann die psychische Gesundheit belasten.</p></div>
      <div class="card"><h3>Gaming</h3><p>Wenn das Spiel die reale Welt ersetzt, ist Vorsicht geboten.</p></div>
    </div>
  </section>

  <section id="gluecksspiel">
    <h2>Glücksspiel</h2>
    <div class="grid">
      <div class="card"><h3>Verlust</h3><p>Glücksspiel führt oft zu schneller Verschuldung und sozialem Rückzug.</p></div>
      <div class="card"><h3>Falle</h3><p>Beinahe-Gewinne halten das Gehirn künstlich in Erwartung.</p></div>
    </div>
  </section>

  <section id="hilfe">
    <h2>Hilfe finden</h2>
    <div class="grid">
      <div class="card"><h3>Hotline</h3><p>Anonyme Hilfe unter 0800 1110111 (Telefonseelsorge).</p></div>
      <div class="card"><h3>Beratung</h3><p>Suchtfachstellen vor Ort bieten diskrete Unterstützung an.</p></div>
    </div>
  </section>

</main>

<script>
  function initTheme() {
    const savedTheme = localStorage.getItem('theme') || 'dark';
    document.body.setAttribute('data-theme', savedTheme);
  }

  function toggleTheme() {
    const currentTheme = document.body.getAttribute('data-theme');
    const newTheme = currentTheme === 'dark' ? 'light' : 'dark';
    document.body.setAttribute('data-theme', newTheme);
    localStorage.setItem('theme', newTheme);
  }

  function showPage(id) {
    document.querySelectorAll('section').forEach(s => s.classList.remove('active'));
    document.getElementById(id).classList.add('active');
    
    const nav = document.getElementById('mainNav');
    if(nav.classList.contains('active')) toggleMenu();
    window.scrollTo(0,0);
  }

  function toggleMenu() {
    document.getElementById('mainNav').classList.toggle('active');
  }

  function evaluateTest() {
    const total = parseInt(document.getElementById('q1').value) + 
                  parseInt(document.getElementById('q2').value) + 
                  parseInt(document.getElementById('q3').value);
    const resDiv = document.getElementById('result');
    resDiv.style.display = 'block';
    if(total < 10) { resDiv.textContent = "Unauffällig."; resDiv.style.color = "var(--secondary)"; }
    else if(total < 22) { resDiv.textContent = "Achtung: Erste Anzeichen."; resDiv.style.color = "var(--primary)"; }
    else { resDiv.textContent = "Hohes Risiko: Suche Hilfe auf."; resDiv.style.color = "#f472b6"; }
  }

  initTheme();
</script>

</body>
</html>
