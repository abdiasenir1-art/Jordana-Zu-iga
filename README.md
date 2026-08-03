<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>ABDIAS URRUTIA</title>
  <link href="https://fonts.googleapis.com/css2?family=Roboto+Slab:wght@400;700;900&family=Nunito:wght@400;600;700;800&family=Orbitron:wght@700;900&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    html { scroll-behavior: smooth; font-size: 16px; }
    body {
      background: linear-gradient(180deg, #060a14 0%, #0a0e1a 30%, #0d1220 100%);
      color: #f0f4ff;
      font-family: 'Nunito', sans-serif;
      min-height: 100vh;
    }

    ::-webkit-scrollbar { width: 6px; }
    ::-webkit-scrollbar-track { background: #0a0e1a; }
    ::-webkit-scrollbar-thumb { background: #6366f1; border-radius: 3px; }

    @keyframes float {
      from { transform: translateY(0px) scale(1); }
      to   { transform: translateY(-30px) scale(1.1); }
    }
    @keyframes shimmer {
      0%   { background-position: -200% center; }
      100% { background-position:  200% center; }
    }
    @keyframes pulse-ring {
      0%   { transform: scale(0.9); opacity: 1; }
      100% { transform: scale(1.6); opacity: 0; }
    }
    @keyframes fadeSlideUp {
      from { opacity: 0; transform: translateY(30px); }
      to   { opacity: 1; transform: translateY(0); }
    }
    @keyframes cardIn {
      from { opacity: 0; transform: translateY(60px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    /* ---- PARTICLES ---- */
    .particles { position: fixed; inset: 0; pointer-events: none; overflow: hidden; z-index: 0; }
    .particle {
      position: absolute;
      border-radius: 50%;
      opacity: 0.13;
      animation: float 4s ease-in-out infinite alternate;
    }
    .grid-bg {
      position: absolute; inset: 0;
      background-image:
        linear-gradient(rgba(99,102,241,0.03) 1px, transparent 1px),
        linear-gradient(90deg, rgba(99,102,241,0.03) 1px, transparent 1px);
      background-size: 60px 60px;
    }

    /* ---- NAV ---- */
    nav {
      position: sticky; top: 0; z-index: 50;
      display: flex; align-items: center; justify-content: space-between;
      padding: 1rem 1.5rem;
      background: rgba(6,10,20,0.88);
      backdrop-filter: blur(20px);
      border-bottom: 1px solid rgba(255,255,255,0.06);
    }
    .nav-logo {
      font-family: 'Orbitron', sans-serif;
      font-weight: 900; font-size: 1.1rem;
      letter-spacing: 0.2em; text-transform: uppercase;
      background: linear-gradient(135deg, #a5b4fc, #818cf8);
      -webkit-background-clip: text; -webkit-text-fill-color: transparent;
      text-decoration: none;
    }
    .nav-links { display: flex; gap: 0.5rem; flex-wrap: wrap; justify-content: flex-end; }
    .nav-link {
      font-size: 0.75rem; font-weight: 700;
      padding: 0.35rem 0.85rem; border-radius: 9999px;
      text-decoration: none; transition: all 0.2s;
      border: 1px solid transparent;
      color: #64748b;
    }
    .nav-link:hover { color: #c7d2fe; background: rgba(99,102,241,0.1); border-color: rgba(99,102,241,0.4); }

    /* ---- HERO ---- */
    header {
      position: relative; z-index: 10;
      text-align: center; padding: 5rem 1.5rem 6rem;
      overflow: hidden;
    }
    .ring {
      position: absolute; inset: 0;
      display: flex; align-items: center; justify-content: center;
      pointer-events: none;
    }
    .ring-circle {
      width: 500px; height: 500px; border-radius: 50%;
      border: 1px solid rgba(99,102,241,0.07);
      animation: pulse-ring 5s ease-out infinite;
    }
    .hero-label {
      font-size: 0.8rem; font-weight: 700;
      text-transform: uppercase; letter-spacing: 0.4em;
      color: #6366f1; margin-bottom: 1rem;
      animation: fadeSlideUp 0.7s ease both;
    }
    .hero-title {
      font-family: 'Roboto Slab', serif;
      font-size: clamp(3.5rem, 10vw, 7rem);
      font-weight: 900; text-transform: uppercase;
      line-height: 1; letter-spacing: -0.02em;
      margin-bottom: 1.5rem;
      background: linear-gradient(135deg, #ffffff 0%, #c7d2fe 40%, #818cf8 70%, #6366f1 100%);
      background-size: 200% auto;
      -webkit-background-clip: text; -webkit-text-fill-color: transparent;
      animation: shimmer 4s linear infinite, fadeSlideUp 0.8s ease both;
    }
    .hero-sub {
      font-size: 1.05rem; color: #94a3b8;
      max-width: 520px; margin: 0 auto 2.5rem;
      animation: fadeSlideUp 0.9s ease both 0.1s;
    }
    .hero-buttons { display: flex; flex-wrap: wrap; gap: 1rem; justify-content: center; }
    .hero-btn {
      display: flex; align-items: center; gap: 0.5rem;
      padding: 0.75rem 1.4rem; border-radius: 1rem;
      font-weight: 700; font-size: 0.9rem;
      color: #fff; text-decoration: none;
      transition: transform 0.25s, box-shadow 0.25s;
      font-family: 'Nunito', sans-serif;
    }
    .hero-btn:hover { transform: scale(1.06); }
    .hero-btn .icon { font-size: 1.15rem; }

    /* ---- DIVIDER ---- */
    .rainbow-divider {
      position: relative; z-index: 10;
      max-width: 900px; margin: 0 auto 4rem; padding: 0 1.5rem;
    }
    .rainbow-divider::after {
      content: ''; display: block; height: 1px; width: 100%;
      background: linear-gradient(90deg,
        transparent,
        rgba(99,102,241,0.5),
        rgba(16,185,129,0.5),
        rgba(249,115,22,0.5),
        rgba(34,197,94,0.5),
        transparent);
    }

    /* ---- CARDS ---- */
    main { position: relative; z-index: 10; max-width: 1100px; margin: 0 auto; padding: 0 1.5rem 6rem; }

    .subject-card {
      position: relative; overflow: hidden; border-radius: 1.75rem;
      margin-bottom: 4rem;
      border: 1px solid;
      background: linear-gradient(135deg, #0f172a 0%, #111827 100%);
      opacity: 0; transform: translateY(60px);
      transition: opacity 0.7s ease, transform 0.7s ease;
    }
    .subject-card.visible { opacity: 1; transform: translateY(0); }

    .card-top-bar { height: 6px; width: 100%; }

    .card-inner {
      display: flex; flex-direction: column;
    }
    @media (min-width: 900px) {
      .card-inner { flex-direction: row; }
      .card-inner.reverse { flex-direction: row-reverse; }
    }

    .card-image-wrap {
      position: relative; overflow: hidden;
      flex-shrink: 0;
    }
    @media (min-width: 900px) {
      .card-image-wrap { width: 40%; min-height: 420px; }
    }
    .card-image-wrap img {
      width: 100%; height: 300px; object-fit: cover;
      transition: transform 0.7s ease;
      display: block;
    }
    @media (min-width: 900px) {
      .card-image-wrap img { height: 100%; min-height: 420px; }
    }
    .card-image-wrap:hover img { transform: scale(1.05); }
    .card-img-overlay { position: absolute; inset: 0; }
    .card-emoji {
      position: absolute; bottom: 1.5rem; left: 1.5rem;
      width: 3.5rem; height: 3.5rem; border-radius: 1rem;
      display: flex; align-items: center; justify-content: center;
      font-size: 1.75rem;
    }

    .card-content {
      flex: 1; padding: 2.5rem 3rem;
      display: flex; flex-direction: column; justify-content: center;
    }
    @media (max-width: 899px) { .card-content { padding: 2rem 1.75rem; } }

    .card-title {
      font-family: 'Roboto Slab', serif;
      font-size: clamp(2rem, 4vw, 3rem);
      font-weight: 900; margin-bottom: 0.5rem;
      line-height: 1.1;
    }
    .card-tags { display: flex; flex-wrap: wrap; gap: 0.5rem; margin-bottom: 1.5rem; margin-top: 0.75rem; }
    .tag {
      font-size: 0.7rem; font-weight: 700;
      padding: 0.3rem 0.85rem; border-radius: 9999px;
      text-transform: uppercase; letter-spacing: 0.15em;
      border: 1px solid;
    }
    .card-desc p { line-height: 1.75; margin-bottom: 0.9rem; }
    .card-desc p:last-child { margin-bottom: 0; }
    .card-desc p.lead { color: #e2e8f0; font-weight: 600; font-size: 1rem; }
    .card-desc p.body { color: #94a3b8; font-size: 0.95rem; }

    /* ---- FOOTER ---- */
    footer {
      position: relative; z-index: 10;
      text-align: center; padding: 3rem 1.5rem;
      border-top: 1px solid rgba(255,255,255,0.06);
    }
    .footer-name {
      font-family: 'Orbitron', sans-serif;
      font-size: 1.5rem; font-weight: 900;
      text-transform: uppercase; letter-spacing: 0.2em;
      background: linear-gradient(135deg, #818cf8, #6366f1);
      -webkit-background-clip: text; -webkit-text-fill-color: transparent;
      margin-bottom: 0.5rem;
    }
    .footer-sub { font-size: 0.85rem; color: #475569; }
  </style>
</head>
<body>

<!-- Particles -->
<div class="particles">
  <div class="grid-bg"></div>
  <div class="particle" style="left:5%;top:10%;width:80px;height:80px;background:#6366f1;animation-delay:0s;animation-duration:4s;"></div>
  <div class="particle" style="left:85%;top:20%;width:60px;height:60px;background:#10b981;animation-delay:1.2s;animation-duration:5s;"></div>
  <div class="particle" style="left:70%;top:65%;width:100px;height:100px;background:#f97316;animation-delay:0.6s;animation-duration:3.5s;"></div>
  <div class="particle" style="left:15%;top:75%;width:70px;height:70px;background:#22c55e;animation-delay:1.8s;animation-duration:4.5s;"></div>
  <div class="particle" style="left:50%;top:5%;width:50px;height:50px;background:#6366f1;animation-delay:2.4s;animation-duration:3s;"></div>
  <div class="particle" style="left:95%;top:50%;width:40px;height:40px;background:#f59e0b;animation-delay:0.9s;animation-duration:5.5s;"></div>
</div>

<!-- Nav -->
<nav>
  <a href="#top" class="nav-logo">A·U</a>
  <div class="nav-links">
    <a href="#matematicas"      class="nav-link">📐 Matemáticas</a>
    <a href="#informatica"      class="nav-link">💻 Informática</a>
    <a href="#educacion-fisica" class="nav-link">⚽ Ed. Física</a>
    <a href="#ciencias"         class="nav-link">🌿 Cs. Naturales</a>
  </div>
</nav>

<!-- Hero -->
<header id="top">
  <div class="ring"><div class="ring-circle"></div></div>
  <p class="hero-label">Examen Final · 2026</p>
  <h1 class="hero-title">ABDIAS<br>URRUTIA</h1>
  <p class="hero-sub">Temario completo de materias para el examen. Explora cada sección con su descripción detallada.</p>
  <div class="hero-buttons">
    <a href="#matematicas"      class="hero-btn" style="background:linear-gradient(135deg,#4338ca,#6366f1);box-shadow:0 4px 20px rgba(99,102,241,0.35);"><span class="icon">📐</span> Matemáticas</a>
    <a href="#informatica"      class="hero-btn" style="background:linear-gradient(135deg,#059669,#10b981);box-shadow:0 4px 20px rgba(16,185,129,0.35);"><span class="icon">💻</span> Informática</a>
    <a href="#educacion-fisica" class="hero-btn" style="background:linear-gradient(135deg,#ea580c,#f97316);box-shadow:0 4px 20px rgba(249,115,22,0.35);"><span class="icon">⚽</span> Ed. Física</a>
    <a href="#ciencias"         class="hero-btn" style="background:linear-gradient(135deg,#16a34a,#22c55e);box-shadow:0 4px 20px rgba(34,197,94,0.35);"><span class="icon">🌿</span> Cs. Naturales</a>
  </div>
</header>

<div class="rainbow-divider"></div>

<main>

  <!-- MATEMÁTICAS -->
  <article id="matematicas" class="subject-card" style="border-color:rgba(99,102,241,0.45);box-shadow:0 0 60px rgba(99,102,241,0.12),0 25px 50px rgba(0,0,0,0.5);">
    <div class="card-top-bar" style="background:linear-gradient(90deg,#4338ca,#6366f1,#818cf8);"></div>
    <div class="card-inner">
      <div class="card-image-wrap">
        <img src="https://images.unsplash.com/photo-1635070041078-e363dbe005cb?w=800&h=500&fit=crop&auto=format" alt="Ecuaciones matemáticas en una pizarra"/>
        <div class="card-img-overlay" style="background:linear-gradient(to right,transparent 40%,#111827 100%),linear-gradient(to top,rgba(67,56,202,0.6) 0%,transparent 60%);"></div>
        <div class="card-emoji" style="background:#6366f1;box-shadow:0 0 30px rgba(99,102,241,0.4);">📐</div>
      </div>
      <div class="card-content">
        <h2 class="card-title" style="background:linear-gradient(135deg,#818cf8,#6366f1);-webkit-background-clip:text;-webkit-text-fill-color:transparent;">Matemáticas</h2>
        <div class="card-tags">
          <span class="tag" style="background:rgba(99,102,241,0.12);color:#818cf8;border-color:rgba(99,102,241,0.4);">Álgebra</span>
          <span class="tag" style="background:rgba(99,102,241,0.12);color:#818cf8;border-color:rgba(99,102,241,0.4);">Geometría</span>
          <span class="tag" style="background:rgba(99,102,241,0.12);color:#818cf8;border-color:rgba(99,102,241,0.4);">Trigonometría</span>
          <span class="tag" style="background:rgba(99,102,241,0.12);color:#818cf8;border-color:rgba(99,102,241,0.4);">Estadística</span>
          <span class="tag" style="background:rgba(99,102,241,0.12);color:#818cf8;border-color:rgba(99,102,241,0.4);">Cálculo</span>
          <span class="tag" style="background:rgba(99,102,241,0.12);color:#818cf8;border-color:rgba(99,102,241,0.4);">Probabilidad</span>
        </div>
        <div class="card-desc">
          <p class="lead">Las Matemáticas son la ciencia que estudia las propiedades de los números, las figuras geométricas, las estructuras abstractas y las relaciones entre ellas mediante el uso del razonamiento lógico y deductivo. Es considerada el lenguaje universal de la ciencia, ya que permite describir con precisión los fenómenos del mundo natural y social.</p>
          <p class="body">En el nivel secundario, las Matemáticas abarcan un amplio espectro de temas fundamentales como el álgebra, que estudia las operaciones con variables y expresiones simbólicas; la geometría, que analiza las formas, ángulos, áreas y volúmenes en el espacio; la aritmética, que trabaja con las operaciones básicas y propiedades de los números enteros, racionales e irracionales; y las funciones matemáticas, que describen relaciones entre conjuntos de valores.</p>
          <p class="body">El estudio de la trigonometría nos permite comprender las relaciones entre los ángulos y los lados de los triángulos, herramienta clave en la arquitectura, la ingeniería y la navegación. La estadística y la probabilidad nos enseñan a recolectar, organizar e interpretar datos, habilidades esenciales en el mundo moderno donde la toma de decisiones basada en evidencia es prioritaria.</p>
          <p class="body">Las Matemáticas desarrollan habilidades cognitivas de alto nivel como el pensamiento crítico, la resolución sistemática de problemas, el razonamiento abstracto y la capacidad de argumentar con lógica. Estas destrezas trascienden las aulas y son aplicables en todas las áreas del conocimiento humano, desde la física y la química hasta la economía, la música y las artes.</p>
        </div>
      </div>
    </div>
  </article>

  <!-- INFORMÁTICA -->
  <article id="informatica" class="subject-card" style="border-color:rgba(16,185,129,0.45);box-shadow:0 0 60px rgba(16,185,129,0.12),0 25px 50px rgba(0,0,0,0.5);">
    <div class="card-top-bar" style="background:linear-gradient(90deg,#059669,#10b981,#34d399);"></div>
    <div class="card-inner reverse">
      <div class="card-image-wrap">
        <img src="https://images.unsplash.com/photo-1517694712202-14dd9538aa97?w=800&h=500&fit=crop&auto=format" alt="Pantalla de computadora con código"/>
        <div class="card-img-overlay" style="background:linear-gradient(to left,transparent 40%,#111827 100%),linear-gradient(to top,rgba(5,150,105,0.6) 0%,transparent 60%);"></div>
        <div class="card-emoji" style="background:#10b981;box-shadow:0 0 30px rgba(16,185,129,0.4);">💻</div>
      </div>
      <div class="card-content">
        <h2 class="card-title" style="background:linear-gradient(135deg,#34d399,#10b981);-webkit-background-clip:text;-webkit-text-fill-color:transparent;">Informática</h2>
        <div class="card-tags">
          <span class="tag" style="background:rgba(16,185,129,0.12);color:#34d399;border-color:rgba(16,185,129,0.4);">Hardware</span>
          <span class="tag" style="background:rgba(16,185,129,0.12);color:#34d399;border-color:rgba(16,185,129,0.4);">Software</span>
          <span class="tag" style="background:rgba(16,185,129,0.12);color:#34d399;border-color:rgba(16,185,129,0.4);">Programación</span>
          <span class="tag" style="background:rgba(16,185,129,0.12);color:#34d399;border-color:rgba(16,185,129,0.4);">Redes</span>
          <span class="tag" style="background:rgba(16,185,129,0.12);color:#34d399;border-color:rgba(16,185,129,0.4);">Bases de Datos</span>
          <span class="tag" style="background:rgba(16,185,129,0.12);color:#34d399;border-color:rgba(16,185,129,0.4);">Inteligencia Artificial</span>
        </div>
        <div class="card-desc">
          <p class="lead">La Informática es la ciencia que se ocupa del tratamiento automático de la información mediante el uso de computadoras y sistemas digitales. Integra conocimientos de matemáticas, ingeniería eléctrica, lógica y comunicación para diseñar sistemas capaces de procesar, almacenar y transmitir datos de manera eficiente y confiable.</p>
          <p class="body">El estudio de la Informática comienza con la comprensión de los componentes físicos del computador, llamados hardware: el procesador (CPU), la memoria RAM, el disco duro, la tarjeta gráfica, la placa madre y los dispositivos de entrada y salida. Cada componente cumple una función específica dentro del sistema y trabaja de forma coordinada para ejecutar las instrucciones del usuario.</p>
          <p class="body">El software es la contraparte lógica del hardware. Los sistemas operativos como Windows, Linux o macOS son programas que administran los recursos del computador y permiten ejecutar otras aplicaciones. Los lenguajes de programación como Python, Java, JavaScript, C++ y muchos más permiten a los desarrolladores escribir instrucciones que las máquinas pueden interpretar y ejecutar.</p>
          <p class="body">En la era digital actual, la Informática es transversal a todas las profesiones. La inteligencia artificial, el aprendizaje automático, la ciberseguridad, el desarrollo web y las aplicaciones móviles son áreas de frontera que transforman continuamente nuestra forma de vivir, trabajar y comunicarnos. Aprender Informática hoy es prepararse para el futuro del trabajo y la innovación global.</p>
        </div>
      </div>
    </div>
  </article>

  <!-- EDUCACIÓN FÍSICA -->
  <article id="educacion-fisica" class="subject-card" style="border-color:rgba(249,115,22,0.45);box-shadow:0 0 60px rgba(249,115,22,0.12),0 25px 50px rgba(0,0,0,0.5);">
    <div class="card-top-bar" style="background:linear-gradient(90deg,#ea580c,#f97316,#fb923c);"></div>
    <div class="card-inner">
      <div class="card-image-wrap">
        <img src="https://images.unsplash.com/photo-1571019613454-1cb2f99b2d8b?w=800&h=500&fit=crop&auto=format" alt="Estudiantes practicando deportes"/>
        <div class="card-img-overlay" style="background:linear-gradient(to right,transparent 40%,#111827 100%),linear-gradient(to top,rgba(234,88,12,0.6) 0%,transparent 60%);"></div>
        <div class="card-emoji" style="background:#f97316;box-shadow:0 0 30px rgba(249,115,22,0.4);">⚽</div>
      </div>
      <div class="card-content">
        <h2 class="card-title" style="background:linear-gradient(135deg,#fb923c,#f97316);-webkit-background-clip:text;-webkit-text-fill-color:transparent;">Educación Física</h2>
        <div class="card-tags">
          <span class="tag" style="background:rgba(249,115,22,0.12);color:#fb923c;border-color:rgba(249,115,22,0.4);">Atletismo</span>
          <span class="tag" style="background:rgba(249,115,22,0.12);color:#fb923c;border-color:rgba(249,115,22,0.4);">Deportes Colectivos</span>
          <span class="tag" style="background:rgba(249,115,22,0.12);color:#fb923c;border-color:rgba(249,115,22,0.4);">Gimnasia</span>
          <span class="tag" style="background:rgba(249,115,22,0.12);color:#fb923c;border-color:rgba(249,115,22,0.4);">Salud y Nutrición</span>
          <span class="tag" style="background:rgba(249,115,22,0.12);color:#fb923c;border-color:rgba(249,115,22,0.4);">Natación</span>
          <span class="tag" style="background:rgba(249,115,22,0.12);color:#fb923c;border-color:rgba(249,115,22,0.4);">Primeros Auxilios</span>
        </div>
        <div class="card-desc">
          <p class="lead">La Educación Física es una disciplina educativa que promueve el desarrollo integral del ser humano a través del movimiento, el ejercicio físico, el deporte y el juego. Más allá de la actividad corporal, busca formar personas saludables, disciplinadas, cooperativas y con valores éticos que les permitan desenvolverse exitosamente en la sociedad.</p>
          <p class="body">El cuerpo humano es una máquina extraordinaria que requiere cuidado y ejercicio constante para mantenerse en óptimas condiciones. A través de la Educación Física se trabajan las capacidades físicas condicionales: la resistencia cardiovascular y muscular, la fuerza, la velocidad y la flexibilidad. Estas capacidades se complementan con las habilidades coordinativas como el equilibrio, la orientación espacial, el ritmo y la reacción.</p>
          <p class="body">Los deportes colectivos como el fútbol, el baloncesto, el voleibol y el béisbol enseñan valores fundamentales como el trabajo en equipo, el respeto por las reglas, la comunicación efectiva, la solidaridad y el manejo de la victoria y la derrota con dignidad. Los deportes individuales como el atletismo, la natación y la gimnasia fortalecen la autodisciplina, la perseverancia y la confianza en uno mismo.</p>
          <p class="body">La actividad física regular tiene comprobados beneficios para la salud física y mental. Reduce el riesgo de enfermedades cardiovasculares, diabetes y obesidad; mejora la postura, la coordinación y la agilidad; libera endorfinas que reducen el estrés y la ansiedad; y favorece un sueño reparador. La Educación Física forma el hábito de vida activa que acompañará a los estudiantes durante toda su vida adulta.</p>
        </div>
      </div>
    </div>
  </article>

  <!-- CIENCIAS NATURALES -->
  <article id="ciencias" class="subject-card" style="border-color:rgba(34,197,94,0.45);box-shadow:0 0 60px rgba(34,197,94,0.12),0 25px 50px rgba(0,0,0,0.5);">
    <div class="card-top-bar" style="background:linear-gradient(90deg,#16a34a,#22c55e,#4ade80);"></div>
    <div class="card-inner reverse">
      <div class="card-image-wrap">
        <img src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=800&h=500&fit=crop&auto=format" alt="Laboratorio de ciencias con microscopio"/>
        <div class="card-img-overlay" style="background:linear-gradient(to left,transparent 40%,#111827 100%),linear-gradient(to top,rgba(22,163,74,0.6) 0%,transparent 60%);"></div>
        <div class="card-emoji" style="background:#22c55e;box-shadow:0 0 30px rgba(34,197,94,0.4);">🌿</div>
      </div>
      <div class="card-content">
        <h2 class="card-title" style="background:linear-gradient(135deg,#4ade80,#22c55e);-webkit-background-clip:text;-webkit-text-fill-color:transparent;">Ciencias Naturales</h2>
        <div class="card-tags">
          <span class="tag" style="background:rgba(34,197,94,0.12);color:#4ade80;border-color:rgba(34,197,94,0.4);">Biología Celular</span>
          <span class="tag" style="background:rgba(34,197,94,0.12);color:#4ade80;border-color:rgba(34,197,94,0.4);">Química Orgánica</span>
          <span class="tag" style="background:rgba(34,197,94,0.12);color:#4ade80;border-color:rgba(34,197,94,0.4);">Física Clásica</span>
          <span class="tag" style="background:rgba(34,197,94,0.12);color:#4ade80;border-color:rgba(34,197,94,0.4);">Ecología</span>
          <span class="tag" style="background:rgba(34,197,94,0.12);color:#4ade80;border-color:rgba(34,197,94,0.4);">Genética</span>
          <span class="tag" style="background:rgba(34,197,94,0.12);color:#4ade80;border-color:rgba(34,197,94,0.4);">Astronomía</span>
        </div>
        <div class="card-desc">
          <p class="lead">Las Ciencias Naturales constituyen un conjunto de disciplinas científicas dedicadas al estudio de la naturaleza y sus fenómenos desde una perspectiva empírica y experimental. Comprenden la Biología, la Física, la Química, la Geología y la Astronomía, y utilizan el método científico como herramienta principal para generar conocimiento validado y reproducible.</p>
          <p class="body">La Biología estudia los seres vivos en toda su diversidad y complejidad, desde las moléculas que forman las células hasta los ecosistemas completos. Abarca la genética y la herencia de características, la evolución de las especies, la fisiología de los organismos, la ecología de las poblaciones y la taxonomía que clasifica a los millones de especies que habitan la Tierra. La célula es la unidad básica de la vida, y su estudio revela los secretos del funcionamiento de todo ser vivo.</p>
          <p class="body">La Química es la ciencia de la materia y sus transformaciones. Estudia la composición, estructura y propiedades de las sustancias, así como los cambios que experimentan durante las reacciones químicas. La tabla periódica de los elementos organiza los 118 elementos conocidos según sus propiedades, y es una de las herramientas más poderosas de la ciencia moderna. Los conceptos de ácidos, bases, soluciones, enlaces químicos y reacciones orgánicas son pilares de esta disciplina.</p>
          <p class="body">La Física describe las leyes fundamentales que gobiernan el universo: el movimiento, la gravedad, la electricidad, el magnetismo, el calor, el sonido y la luz. Las leyes de Newton explican por qué los planetas orbitan el sol y por qué caen los objetos. La física cuántica revela el comportamiento extraño de las partículas subatómicas. Las Ciencias Naturales en su conjunto nos invitan a observar el mundo con curiosidad y a formular preguntas que expanden los límites del conocimiento humano.</p>
        </div>
      </div>
    </div>
  </article>

</main>

<!-- Footer -->
<footer>
  <p class="footer-name">ABDIAS URRUTIA</p>
  <p class="footer-sub">Examen Final 2026 · Matemáticas · Informática · Educación Física · Ciencias Naturales</p>
</footer>

<script>
  // Scroll reveal animation
  const cards = document.querySelectorAll('.subject-card');
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry, i) => {
      if (entry.isIntersecting) {
        setTimeout(() => entry.target.classList.add('visible'), i * 80);
        observer.unobserve(entry.target);
      }
    });
  }, { threshold: 0.1 });
  cards.forEach(card => observer.observe(card));

  // Nav active state
  const navLinks = document.querySelectorAll('.nav-link');
  window.addEventListener('scroll', () => {
    const ids = ['matematicas','informatica','educacion-fisica','ciencias'];
    let active = '';
    for (const id of ids.slice().reverse()) {
      const el = document.getElementById(id);
      if (el && el.getBoundingClientRect().top <= 200) { active = id; break; }
    }
    navLinks.forEach(link => {
      const href = link.getAttribute('href').replace('#','');
      if (href === active) {
        link.style.color = '#c7d2fe';
        link.style.background = 'rgba(99,102,241,0.12)';
        link.style.borderColor = 'rgba(99,102,241,0.4)';
      } else {
        link.style.color = '#64748b';
        link.style.background = 'transparent';
        link.style.borderColor = 'transparent';
      }
    });
  });
</script>
</body>
</html>
Cómo usarlo en VS Code:

Abre VS Code
Crea un nuevo archivo → ABDIAS_URRUTIA.html
Pega TODO el código de arriba
Guarda con Ctrl + S
Abre el archivo en el navegador (clic derecho → Open with Live Server, o simplemente arrastra el archivo al navegador)
La página incluye:

Título "ABDIAS URRUTIA" en grande con animación de brillo
4 tarjetas con colores únicos: Matemáticas (morado/índigo), Informática (verde esmeralda), Ed. Física (naranja), Ciencias Naturales (verde lima)
Imágenes reales de Unsplash por materia
Animaciones: partículas flotantes, aparición al hacer scroll, efecto shimmer en el título
Navegación sticky que resalta la sección activa
Descripciones largas con subtemas destacados en etiquetas
Necesito una pagina web de HTML, que el titulo diga "Jordana-Zuñiga ", la pagina web también se llamara así, el tema en si, despues de mi nombre (Jordana-Zuñiga), es de un tema de examen, las materias que van son; Matemáticas, Informática, Educación Física, Ciencias Naturales. todas las materias van con una descripción corta que nadie te haya pedido, con imágenes y un solo color elegante representativo, de ahí luego me das el código completo para pegarlo en el visual studio code.

Voy a leer los archivos antes de construir la nueva página con una estética completamente distinta y elegante.

Actualizando el canvas con la estética de Jordana — un solo color elegante, fondo claro y tipografía serif refinada.

Perfecto. Aquí tienes el código HTML completo para pegar en VS Code:

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
