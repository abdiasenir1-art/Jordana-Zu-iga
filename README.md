<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Jordana-Zuñiga</title>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400&family=Lato:wght@300;400;700&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --rose: #9f1239;
      --rose-light: #fdf2f5;
      --rose-border: rgba(159,18,57,0.14);
      --rose-muted: #7a5c60;
      --bg: #faf7f4;
      --ink: #1c1410;
      --ink-soft: #4b3035;
    }

    html { scroll-behavior: smooth; font-size: 16px; }
    body { background: var(--bg); color: var(--ink); font-family: 'Lato', sans-serif; }

    ::-webkit-scrollbar { width: 5px; }
    ::-webkit-scrollbar-track { background: var(--bg); }
    ::-webkit-scrollbar-thumb { background: var(--rose); border-radius: 3px; }

    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(24px); }
      to   { opacity: 1; transform: none; }
    }
    @keyframes drawLine {
      from { width: 0; }
      to   { width: 80px; }
    }
    @keyframes rotateSlow {
      from { transform: translate(-50%,-50%) rotate(0deg); }
      to   { transform: translate(-50%,-50%) rotate(360deg); }
    }
    @keyframes cardIn {
      from { opacity: 0; transform: translateY(48px); }
      to   { opacity: 1; transform: none; }
    }

    /* ── NAV ───────────────────────────────── */
    nav {
      position: sticky; top: 0; z-index: 50;
      display: flex; align-items: center; justify-content: space-between;
      padding: 1rem 2rem;
      transition: all 0.3s ease;
      border-bottom: 1px solid transparent;
    }
    nav.scrolled {
      background: rgba(250,247,244,0.94);
      backdrop-filter: blur(16px);
      border-bottom-color: var(--rose-border);
    }
    .nav-logo {
      font-family: 'Playfair Display', serif;
      font-weight: 700; font-size: 1.1rem;
      color: var(--rose); text-decoration: none;
      letter-spacing: 0.06em;
    }
    .nav-links { display: flex; gap: 0.3rem; flex-wrap: wrap; justify-content: flex-end; }
    .nav-link {
      font-size: 0.72rem; font-weight: 700;
      padding: 0.3rem 0.9rem; border-radius: 9999px;
      text-decoration: none; letter-spacing: 0.08em;
      text-transform: uppercase; transition: all 0.2s;
      color: var(--rose-muted);
      border: 1px solid var(--rose-border);
      font-family: 'Lato', sans-serif;
    }
    .nav-link:hover, .nav-link.active {
      color: #fff;
      background: var(--rose);
      border-color: var(--rose);
    }

    /* ── HERO ──────────────────────────────── */
    header {
      position: relative; text-align: center;
      padding: 5rem 2rem 7rem; overflow: hidden;
    }
    .deco-ring {
      position: absolute; top: 50%; left: 50%;
      border-radius: 50%;
      border: 1px solid var(--rose-border);
      pointer-events: none; transform: translate(-50%,-50%);
    }
    .deco-orbit {
      position: absolute; top: 22%; right: 10%;
      width: 70px; height: 70px;
      border-radius: 50%;
      border: 1px solid var(--rose-border);
      animation: rotateSlow 22s linear infinite;
    }
    .hero-eyebrow {
      font-size: 0.75rem; font-weight: 700;
      letter-spacing: 0.45em; text-transform: uppercase;
      color: var(--rose); margin-bottom: 1.25rem;
      animation: fadeUp 0.7s ease both;
    }
    .hero-name-1 {
      font-family: 'Playfair Display', serif;
      font-size: clamp(3.5rem, 9vw, 7rem);
      font-weight: 900; line-height: 1.05;
      letter-spacing: -0.02em; color: var(--ink);
      animation: fadeUp 0.8s ease both 0.05s;
    }
    .hero-name-2 {
      font-family: 'Playfair Display', serif;
      font-size: clamp(2.4rem, 7vw, 5.5rem);
      font-weight: 400; font-style: italic;
      line-height: 1.1; letter-spacing: -0.01em;
      color: var(--rose); margin-bottom: 2rem;
      animation: fadeUp 0.8s ease both 0.12s;
    }
    .hero-bar {
      width: 80px; height: 2px;
      background: var(--rose);
      margin: 0 auto 2rem;
      animation: drawLine 1s ease both 0.4s;
    }
    .hero-sub {
      color: var(--rose-muted); font-size: 1rem;
      max-width: 460px; margin: 0 auto 3rem;
      line-height: 1.8; font-weight: 300;
      animation: fadeUp 0.9s ease both 0.2s;
    }
    .hero-grid {
      display: grid; grid-template-columns: repeat(2,1fr);
      gap: 1rem; max-width: 480px; margin: 0 auto;
      animation: fadeUp 1s ease both 0.3s;
    }
    .hero-card {
      display: flex; align-items: center; gap: 0.75rem;
      padding: 1rem 1.25rem;
      border: 1px solid var(--rose-border);
      border-radius: 1rem; background: #fff;
      text-decoration: none; transition: all 0.25s;
      box-shadow: 0 2px 12px rgba(159,18,57,0.05);
    }
    .hero-card:hover {
      background: var(--rose-light);
      border-color: var(--rose);
      transform: translateY(-2px);
    }
    .hero-card-icon {
      font-size: 1.3rem; width: 2rem; text-align: center;
      color: var(--rose); font-family: 'Playfair Display', serif;
    }
    .hero-card-label {
      font-size: 0.82rem; font-weight: 700;
      color: var(--ink); text-align: left;
    }

    /* ── DIVIDER ───────────────────────────── */
    .divider {
      max-width: 900px; margin: 0 auto 5rem; padding: 0 2rem;
    }
    .divider::after {
      content: ''; display: block; height: 1px;
      background: linear-gradient(90deg, transparent, var(--rose-border), transparent);
    }

    /* ── CARDS ─────────────────────────────── */
    main { max-width: 1050px; margin: 0 auto; padding: 0 1.5rem 6rem; }

    .subject-wrap {
      position: relative; margin-bottom: 5rem;
      opacity: 0; transform: translateY(48px);
      transition: opacity 0.75s ease, transform 0.75s ease;
    }
    .subject-wrap.visible { opacity: 1; transform: none; }

    .subject-label {
      position: absolute; top: -1.4rem; left: 0;
      font-size: 0.7rem; font-weight: 700;
      letter-spacing: 0.3em; text-transform: uppercase;
      color: var(--rose); background: var(--rose-light);
      border: 1px solid var(--rose-border);
      padding: 0.25rem 0.75rem; border-radius: 9999px;
      font-family: 'Lato', sans-serif;
    }
    .subject-card {
      border-radius: 1.25rem; overflow: hidden;
      border: 1px solid var(--rose-border); background: #fff;
      box-shadow: 0 8px 40px rgba(159,18,57,0.07), 0 2px 8px rgba(0,0,0,0.04);
      display: flex; flex-direction: column;
    }
    @media (min-width: 860px) {
      .subject-card { flex-direction: row; }
      .subject-card.flip { flex-direction: row-reverse; }
    }

    .card-img-wrap {
      position: relative; overflow: hidden;
      min-height: 280px; flex-shrink: 0;
    }
    @media (min-width: 860px) { .card-img-wrap { width: 42%; min-height: 360px; } }

    .card-img-wrap img {
      width: 100%; height: 100%; object-fit: cover;
      display: block; min-height: 280px;
      transition: transform 0.8s ease;
    }
    @media (min-width: 860px) { .card-img-wrap img { min-height: 360px; } }
    .card-img-wrap:hover img { transform: scale(1.04); }

    .card-img-overlay {
      position: absolute; inset: 0;
      background: linear-gradient(to bottom, transparent 50%, rgba(159,18,57,0.55) 100%);
    }
    .card-badge {
      position: absolute; bottom: 1.25rem; right: 1.25rem;
      width: 3.25rem; height: 3.25rem; border-radius: 50%;
      display: flex; align-items: center; justify-content: center;
      font-family: 'Playfair Display', serif;
      font-size: 1.1rem; font-weight: 700;
      background: var(--rose); color: #fff;
      box-shadow: 0 4px 20px rgba(159,18,57,0.4);
    }

    .card-body { flex: 1; padding: 2.5rem 3rem; display: flex; flex-direction: column; justify-content: center; }
    @media (max-width: 859px) { .card-body { padding: 2rem 1.75rem; } }

    .card-eyebrow {
      font-size: 0.7rem; font-weight: 700;
      letter-spacing: 0.35em; text-transform: uppercase;
      color: var(--rose); margin-bottom: 0.75rem;
    }
    .card-title {
      font-family: 'Playfair Display', serif;
      font-size: clamp(1.8rem, 3vw, 2.6rem);
      font-weight: 700; color: var(--ink);
      line-height: 1.15; margin-bottom: 1.25rem;
    }
    .card-rule { width: 3rem; height: 2px; background: var(--rose); margin-bottom: 1.25rem; }
    .card-desc {
      color: var(--ink-soft); font-size: 0.97rem;
      line-height: 1.85; font-weight: 300; margin-bottom: 1.75rem;
    }
    .card-tags { display: flex; flex-wrap: wrap; gap: 0.5rem; }
    .tag {
      font-size: 0.68rem; font-weight: 700;
      padding: 0.3rem 0.9rem; border-radius: 9999px;
      text-transform: uppercase; letter-spacing: 0.12em;
      color: var(--rose); background: var(--rose-light);
      border: 1px solid var(--rose-border);
    }

    /* ── FOOTER ────────────────────────────── */
    footer {
      text-align: center; padding: 3rem 2rem;
      border-top: 1px solid var(--rose-border);
    }
    .footer-name {
      font-family: 'Playfair Display', serif;
      font-size: 1.4rem; font-weight: 700;
      color: var(--rose); letter-spacing: 0.06em; margin-bottom: 0.5rem;
    }
    .footer-sub {
      font-size: 0.75rem; color: var(--rose-muted);
      letter-spacing: 0.15em; text-transform: uppercase;
    }
  </style>
</head>
<body>

<!-- NAV -->
<nav id="nav">
  <a href="#top" class="nav-logo">J·Z</a>
  <div class="nav-links">
    <a href="#matematicas"      class="nav-link">Matemáticas</a>
    <a href="#informatica"      class="nav-link">Informática</a>
    <a href="#educacion-fisica" class="nav-link">Ed. Física</a>
    <a href="#ciencias"         class="nav-link">Cs. Naturales</a>
  </div>
</nav>

<!-- HERO -->
<header id="top">
  <div class="deco-ring" style="width:600px;height:600px;"></div>
  <div class="deco-ring" style="width:380px;height:380px;opacity:0.6;"></div>
  <div class="deco-orbit"></div>

  <p class="hero-eyebrow">Temario de Examen · 2026</p>
  <h1 class="hero-name-1">Jordana</h1>
  <h1 class="hero-name-2">Zuñiga</h1>
  <div class="hero-bar"></div>
  <p class="hero-sub">Cuatro materias, cuatro miradas al conocimiento. Selecciona una materia para explorar su contenido.</p>

  <div class="hero-grid">
    <a href="#matematicas"      class="hero-card"><span class="hero-card-icon">∑</span><span class="hero-card-label">Matemáticas</span></a>
    <a href="#informatica"      class="hero-card"><span class="hero-card-icon">&lt;/&gt;</span><span class="hero-card-label">Informática</span></a>
    <a href="#educacion-fisica" class="hero-card"><span class="hero-card-icon">◎</span><span class="hero-card-label">Educación Física</span></a>
    <a href="#ciencias"         class="hero-card"><span class="hero-card-icon">✦</span><span class="hero-card-label">Cs. Naturales</span></a>
  </div>
</header>

<div class="divider"></div>

<!-- CARDS -->
<main>

  <!-- 01 MATEMÁTICAS -->
  <div class="subject-wrap" style="transition-delay:0ms;">
    <span class="subject-label">01 / Matemáticas</span>
    <div class="subject-card" id="matematicas">
      <div class="card-img-wrap">
        <img src="https://images.unsplash.com/photo-1509228468518-180dd4864904?w=900&h=600&fit=crop&auto=format" alt="Cuaderno con fórmulas matemáticas"/>
        <div class="card-img-overlay"></div>
        <div class="card-badge">∑</div>
      </div>
      <div class="card-body">
        <p class="card-eyebrow">El lenguaje del universo</p>
        <h2 class="card-title">Matemáticas</h2>
        <div class="card-rule"></div>
        <p class="card-desc">Las Matemáticas son el arte de dar sentido a los patrones ocultos del mundo. A través del álgebra, la geometría y el cálculo, aprendemos a resolver problemas con rigor y precisión. Más que números, es una forma de pensar con claridad y elegancia.</p>
        <div class="card-tags">
          <span class="tag">Álgebra</span>
          <span class="tag">Geometría</span>
          <span class="tag">Funciones</span>
          <span class="tag">Probabilidad</span>
        </div>
      </div>
    </div>
  </div>

  <!-- 02 INFORMÁTICA -->
  <div class="subject-wrap" style="transition-delay:100ms;">
    <span class="subject-label">02 / Informática</span>
    <div class="subject-card flip" id="informatica">
      <div class="card-img-wrap">
        <img src="https://images.unsplash.com/photo-1461749280684-dccba630e2f6?w=900&h=600&fit=crop&auto=format" alt="Código de programación en pantalla"/>
        <div class="card-img-overlay"></div>
        <div class="card-badge">&lt;/&gt;</div>
      </div>
      <div class="card-body">
        <p class="card-eyebrow">La ciencia que transforma el futuro</p>
        <h2 class="card-title">Informática</h2>
        <div class="card-rule"></div>
        <p class="card-desc">La Informática es la disciplina que estudia el procesamiento inteligente de la información. Desde el hardware hasta los algoritmos, nos enseña a construir soluciones digitales que mejoran la vida cotidiana y abren puertas a mundos antes inimaginables.</p>
        <div class="card-tags">
          <span class="tag">Hardware</span>
          <span class="tag">Programación</span>
          <span class="tag">Redes</span>
          <span class="tag">Sistemas Operativos</span>
        </div>
      </div>
    </div>
  </div>

  <!-- 03 EDUCACIÓN FÍSICA -->
  <div class="subject-wrap" style="transition-delay:200ms;">
    <span class="subject-label">03 / Educación Física</span>
    <div class="subject-card" id="educacion-fisica">
      <div class="card-img-wrap">
        <img src="https://images.unsplash.com/photo-1461896836934-ffe607ba8211?w=900&h=600&fit=crop&auto=format" alt="Pista de atletismo vista desde arriba"/>
        <div class="card-img-overlay"></div>
        <div class="card-badge">◎</div>
      </div>
      <div class="card-body">
        <p class="card-eyebrow">Cuerpo, mente y movimiento</p>
        <h2 class="card-title">Educación Física</h2>
        <div class="card-rule"></div>
        <p class="card-desc">La Educación Física cultiva el bienestar integral del ser humano mediante el movimiento consciente. Deporte, disciplina y trabajo en equipo forman personas equilibradas, resilientes y capaces de afrontar cualquier desafío con energía y determinación.</p>
        <div class="card-tags">
          <span class="tag">Atletismo</span>
          <span class="tag">Deportes de Equipo</span>
          <span class="tag">Salud</span>
          <span class="tag">Coordinación</span>
        </div>
      </div>
    </div>
  </div>

  <!-- 04 CIENCIAS NATURALES -->
  <div class="subject-wrap" style="transition-delay:300ms;">
    <span class="subject-label">04 / Ciencias Naturales</span>
    <div class="subject-card flip" id="ciencias">
      <div class="card-img-wrap">
        <img src="https://images.unsplash.com/photo-1532094349884-543559b6d40a?w=900&h=600&fit=crop&auto=format" alt="Microscopio de laboratorio"/>
        <div class="card-img-overlay"></div>
        <div class="card-badge">✦</div>
      </div>
      <div class="card-body">
        <p class="card-eyebrow">Descubriendo los secretos de la vida</p>
        <h2 class="card-title">Ciencias Naturales</h2>
        <div class="card-rule"></div>
        <p class="card-desc">Las Ciencias Naturales nos invitan a explorar el mundo con asombro y método. Biología, Química y Física se unen para explicar desde la estructura del átomo hasta el comportamiento de los ecosistemas, revelando el orden detrás de toda la naturaleza.</p>
        <div class="card-tags">
          <span class="tag">Biología</span>
          <span class="tag">Química</span>
          <span class="tag">Física</span>
          <span class="tag">Ecología</span>
        </div>
      </div>
    </div>
  </div>

</main>

<!-- FOOTER -->
<footer>
  <p class="footer-name">Jordana-Zuñiga</p>
  <p class="footer-sub">Examen Final · 2026</p>
</footer>

<script>
  // Nav scroll behavior
  const nav = document.getElementById('nav');
  const navLinks = document.querySelectorAll('.nav-link');
  const sectionIds = ['matematicas','informatica','educacion-fisica','ciencias'];

  window.addEventListener('scroll', () => {
    // Sticky style
    nav.classList.toggle('scrolled', window.scrollY > 40);

    // Active nav link
    let active = '';
    for (const id of [...sectionIds].reverse()) {
      const el = document.getElementById(id);
      if (el && el.getBoundingClientRect().top <= 180) { active = id; break; }
    }
    navLinks.forEach(link => {
      const href = link.getAttribute('href').replace('#','');
      link.classList.toggle('active', href === active);
    });
  });

  // Scroll reveal
  const wraps = document.querySelectorAll('.subject-wrap');
  const obs = new IntersectionObserver((entries) => {
    entries.forEach(e => {
      if (e.isIntersecting) { e.target.classList.add('visible'); obs.unobserve(e.target); }
    });
  }, { threshold: 0.1 });
  wraps.forEach(w => obs.observe(w));
</script>
</body>
</html>
