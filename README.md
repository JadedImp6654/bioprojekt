<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Suchtaufklärung – Information & Hilfe</title>
  <meta name="description" content="Moderne, statische Website zur Suchtaufklärung mit interaktivem Selbsttest. Informationen zu Alkohol-, Drogen-, Medien- und Glücksspielsucht." />
  <meta name="author" content="Darian Müller" />
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --primary: #6ea8ff;
      --secondary: #7af0d1;
      --dark-bg: #0f172a;
      --light-bg: #f8fafc;
      --text-dark: #f8fafc;
      --text-light: #0f172a;
      --card-dark: rgba(15,23,42,0.85);
      --card-light: rgba(248,250,252,0.85);
      --header-dark: rgba(15,23,42,0.9);
      --header-light: rgba(248,250,252,0.9);
      --footer-dark: #020617;
      --footer-light: #e5e7eb;
      --section-dark: rgba(15,23,42,0.8);
      --section-light: rgba(248,250,252,0.8);
    }

    body {
      font-family: 'Inter', sans-serif;
      background: var(--dark-bg);
      color: var(--text-dark);
      line-height: 1.7;
      font-size: 18px;
      overflow-x: hidden;
      transition: background 0.3s, color 0.3s;
    }

    header {
      position: fixed;
      top: 0;
      width: 100%;
      padding: 20px 60px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: var(--header-dark);
      backdrop-filter: blur(12px);
      z-index: 1000;
      transition: background 0.3s, color 0.3s;
    }
    header h1 { font-size: 1.2rem; font-weight: 700; color: var(--secondary); }
    nav a { margin-left: 24px; text-decoration: none; color: inherit; font-weight: 400; cursor: pointer; }

    section {
      display: none;
      padding: 140px 12% 80px;
      border-radius: 12px;
      background: var(--section-dark);
      color: var(--text-dark);
      transition: background 0.3s, color 0.3s;
    }
    section.active { display: block; }

    h2 { font-size: clamp(2rem, 3vw, 2.4rem); margin-bottom: 20px; }
    p { max-width: 800px; margin-bottom: 18px; }

    .card-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)); gap: 24px; margin-top: 40px; }
    .card { border-radius: 24px; padding: 36px; font-size: 1rem; line-height: 1.6; transition: transform 0.4s ease, box-shadow 0.4s ease, background 0.3s, color 0.3s; background: var(--card-dark); color: var(--text-dark); }
    .card:hover { transform: translateY(-10px) scale(1.02); box-shadow: 0 30px 60px rgba(0,0,0,0.5); }

    .test-question { margin-bottom: 20px; }
    input[type=range] { width: 100%; }
    button { padding: 16px 32px; border: none; border-radius: 999px; background: linear-gradient(90deg, var(--primary), var(--secondary)); color: #020617; font-weight: 600; font-size: 1rem; cursor: pointer; margin-top: 24px; }

    footer { text-align: center; padding: 40px 20px; font-size: 0.9rem; margin-top: 40px; background: var(--footer-dark); color: var(--text-dark); transition: background 0.3s, color 0.3s; }

    #darkModeToggle {
      position: fixed;
      bottom: 20px;
      right: 20px;
      z-index: 1001;
      padding: 12px 18px;
      border: none;
      border-radius: 999px;
      background: var(--primary);
      color: #020617;
      cursor: pointer;
      font-weight: 600;
    }
  </style>
</head>
<body data-mode="dark" onload="showPage('start')">

<header>
  <h1>Suchtaufklärung</h1>
  <nav>
    <a onclick="showPage('start')">Start</a>
    <a onclick="showPage('test')">Selbsttest</a>
    <a onclick="showPage('alkohol')">Alkohol</a>
    <a onclick="showPage('drogen')">Drogen</a>
    <a onclick="showPage('medien')">Medien</a>
    <a onclick="showPage('gluecksspiel')">Glücksspiel</a>
    <a onclick="showPage('hilfe')">Hilfe</a>
    <a href="https://jadedimp6654.github.io" target="_blank">Externe Seite</a>
  </nav>
</header>

<!-- Sections -->
<section id="start">
  <h2>Sucht verstehen – wissenschaftlich fundiert</h2>
  <p>Sucht stellt ein komplexes biopsychosoziales Phänomen dar...</p>
</section>

<section id="test">
  <h2>Interaktiver Selbsttest</h2>
  <p>Dieser Selbsttest dient der Selbstreflexion.</p>
  <div class="card">
    <div class="test-question"><p>Hast du das Gefühl, dein Konsum ist schwer kontrollierbar?</p><input type="range" min="0" max="10" id="q1" /></div>
    <div class="test-question"><p>Beeinflusst dein Verhalten deinen Alltag oder Beziehungen negativ?</p><input type="range" min="0" max="10" id="q2" /></div>
    <div class="test-question"><p>Greifst du auf das Verhalten zurück, um Stress zu bewältigen?</p><input type="range" min="0" max="10" id="q3" /></div>
    <div class="test-question"><p>Hast du schon versucht, dein Verhalten zu reduzieren – ohne Erfolg?</p><input type="range" min="0" max="10" id="q4" /></div>
    <button onclick="evaluateTest()">Auswerten</button>
    <p id="result" role="status"></p>
  </div>
</section>

<section id="alkohol">
  <h2>Alkoholkonsum und Abhängigkeit</h2>
  <div class="card-grid">
    <div class="card">Alkoholsucht ist eine chronische Erkrankung, die durch Kontrollverlust und Entzugssymptome gekennzeichnet ist.</div>
    <div class="card">Langfristiger Konsum kann zu Lebererkrankungen und neurokognitiven Beeinträchtigungen führen.</div>
    <div class="card">Therapie umfasst psychotherapeutische, medikamentöse und soziale Maßnahmen.</div>
  </div>
</section>

<section id="drogen">
  <h2>Drogenabhängigkeit</h2>
  <div class="card-grid">
    <div class="card">Illegale Substanzen greifen direkt in das Belohnungssystem des Gehirns ein.</div>
    <div class="card">Abhängigkeit hängt von genetischen, psychologischen und sozialen Faktoren ab.</div>
    <div class="card">Therapie erfordert Entzugsbehandlung, Psychotherapie und soziale Reintegration.</div>
  </div>
</section>

<section id="medien">
  <h2>Medien- und Verhaltenssüchte</h2>
  <div class="card-grid">
    <div class="card">Problematische Mediennutzung zeigt ähnliche neuronale Muster wie Substanzabhängigkeit.</div>
    <div class="card">Variable Belohnungen und soziale Bestätigung verstärken die Nutzung.</div>
    <div class="card">Prävention: Medienkompetenz, Selbstregulation, strukturierte Rahmenbedingungen.</div>
  </div>
</section>

<section id="gluecksspiel">
  <h2>Glücksspielbezogene Störungen</h2>
  <div class="card-grid">
    <div class="card">Glücksspielsucht ist eine Verhaltenssucht, charakterisiert durch persistentes dysfunktionales Spiel.</div>
    <div class="card">Folgen: finanzielle Probleme, soziale Isolation, psychische Komorbidität.</div>
    <div class="card">Therapie: kognitive Verhaltenstherapie, Schuldenberatung, Rückfallprävention.</div>
  </div>
</section>

<section id="hilfe">
  <h2>Professionelle Hilfe</h2>
  <div class="card-grid">
    <div class="card">Frühzeitige Intervention ist entscheidend. Beratungsstellen, Therapie und medizinische Unterstützung helfen individuell.</div>
  </div>
</section>

<footer>
  © 2026 Darian Müller – Alle Rechte vorbehalten
</footer>

<button id="darkModeToggle" onclick="toggleDarkMode()">Toggle Mode</button>

<script>
  function showPage(id) {
    const pages = document.querySelectorAll('section');
    pages.forEach(p => p.classList.remove('active'));
    document.getElementById(id).classList.add('active');
  }

  function evaluateTest() {
    const score = Number(q1.value) + Number(q2.value) + Number(q3.value) + Number(q4.value);
    const result = document.getElementById('result');
    if (score < 15) result.textContent = 'Geringes Risiko – Verhalten unauffällig.';
    else if (score < 30) result.textContent = 'Mittleres Risiko – bewusst handeln, ggf. Beratung.';
    else result.textContent = 'Hohes Risiko – professionelle Hilfe empfohlen.';
  }

  function toggleDarkMode() {
    const body = document.body;
    const isDark = body.dataset.mode === 'dark';
    body.dataset.mode = isDark ? 'light' : 'dark';

    body.style.backgroundColor = isDark ? 'var(--light-bg)' : 'var(--dark-bg)';
    body.style.color = isDark ? 'var(--text-light)' : 'var(--text-dark)';

    const header = document.querySelector('header');
    header.style.background = isDark ? 'var(--header-light)' : 'var(--header-dark)';
    header.style.color = isDark ? 'var(--text-light)' : 'var(--text-dark)';

    const footer = document.querySelector('footer');
    footer.style.background = isDark ? 'var(--footer-light)' : 'var(--footer-dark)';
    footer.style.color = isDark ? 'var(--text-light)' : 'var(--text-dark)';

    document.querySelectorAll('section').forEach(section => {
      section.style.background = isDark ? 'var(--section-light)' : 'var(--section-dark)';
      section.style.color = isDark ? 'var(--text-light)' : 'var(--text-dark)';
    });

    document.querySelectorAll('.card').forEach(card => {
      card.style.background = isDark ? 'var(--card-light)' : 'var(--card-dark)';
      card.style.color = isDark ? 'var(--text-light)' : 'var(--text-dark)';
    });
  }
</script>

</body>
</html>
