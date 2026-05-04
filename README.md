<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Ginlly - Tienda Multimarcas</title>
<link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Cormorant+Garamond:ital,wght@0,400;0,600;1,400&family=Nunito:wght@400;600;700&display=swap" rel="stylesheet">

<style>
  :root {
    --gold: #b8932d;
    --gold-light: #f9d77e;
    --gold-pale: #fff5e0;
    --gold-medium: #f9e0b2;
    --text: #3a2a0a;
    --text-light: #7a6030;
    --white: #fffdf7;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    font-family: 'Nunito', sans-serif;
    background-color: var(--white);
    color: var(--text);
    overflow-x: hidden;
  }

  /* ── DECORATIVE BG TEXTURE ── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      radial-gradient(ellipse 60% 40% at 10% 10%, rgba(249,215,126,0.18) 0%, transparent 60%),
      radial-gradient(ellipse 50% 50% at 90% 80%, rgba(184,147,45,0.12) 0%, transparent 60%);
    pointer-events: none;
    z-index: 0;
  }

  /* ── HEADER ── */
  header {
    text-align: center;
    padding: 56px 24px 36px;
    position: relative;
    z-index: 1;
  }

  .logo-wrap {
    display: inline-flex;
    align-items: center;
    gap: 12px;
  }

  header h1 {
    font-family: 'Great Vibes', cursive;
    font-size: clamp(58px, 10vw, 90px);
    color: var(--gold);
    line-height: 1;
    text-shadow: 2px 3px 12px rgba(184,147,45,0.25);
    animation: fadeDown 0.9s ease both;
  }

  .girasol-svg {
    width: 64px;
    height: 64px;
    animation: spin 18s linear infinite, fadeDown 0.9s ease both;
  }

  header h2 {
    font-family: 'Cormorant Garamond', serif;
    font-size: clamp(13px, 2.5vw, 17px);
    letter-spacing: 6px;
    text-transform: uppercase;
    color: var(--gold);
    margin-top: 6px;
    animation: fadeUp 1s 0.2s ease both;
  }

  .tagline {
    margin-top: 20px;
    font-size: clamp(15px, 2.5vw, 19px);
    color: var(--text-light);
    animation: fadeUp 1s 0.35s ease both;
  }

  .sub-text {
    display: inline-block;
    background: linear-gradient(135deg, #f9d77e, #f9c44a);
    padding: 4px 18px;
    border-radius: 30px;
    font-weight: 700;
    color: var(--text);
    box-shadow: 0 2px 8px rgba(184,147,45,0.3);
  }

  .categorias-tag {
    margin-top: 12px;
    font-size: 13px;
    color: var(--gold);
    letter-spacing: 3px;
    text-transform: uppercase;
    font-weight: 600;
    animation: fadeUp 1s 0.5s ease both;
  }

  /* ── DIVIDER ── */
  .divider {
    width: 100%;
    height: 2px;
    background: linear-gradient(90deg, transparent, var(--gold-light), transparent);
    margin: 0;
    position: relative;
    z-index: 1;
  }

  /* ── MAIN CONTENT ── */
  .main-container {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    padding: 48px 32px;
    gap: 48px;
    align-items: flex-start;
    position: relative;
    z-index: 1;
  }

  /* ── CATEGORY LIST ── */
  .categorias-panel {
    flex: 0 0 320px;
  }

  .categorias-panel h3 {
    font-family: 'Cormorant Garamond', serif;
    font-size: 22px;
    color: var(--gold);
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 20px;
    padding-bottom: 10px;
    border-bottom: 2px solid var(--gold-light);
  }

  .categorias {
    list-style: none;
  }

  .categorias li {
    display: flex;
    align-items: center;
    gap: 16px;
    padding: 14px 16px;
    font-size: 15px;
    font-weight: 600;
    border-radius: 12px;
    margin-bottom: 6px;
    cursor: default;
    transition: background 0.25s, transform 0.2s;
  }

  .categorias li:hover {
    background: var(--gold-pale);
    transform: translateX(5px);
  }

  .cat-icon {
    width: 44px;
    height: 44px;
    border-radius: 50%;
    background: linear-gradient(135deg, #fff5e0, #f9e0b2);
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 22px;
    flex-shrink: 0;
    box-shadow: 0 2px 8px rgba(184,147,45,0.2);
  }

  /* ── STORE PHOTO AREA ── */
  .foto-tienda {
    flex: 1 1 380px;
    max-width: 560px;
    position: relative;
    min-height: 380px;
  }

  .foto-placeholder {
    width: 100%;
    aspect-ratio: 4/3;
    background: linear-gradient(135deg, #f9e0b2 0%, #fff5e0 50%, #f9d77e 100%);
    border-radius: 20px;
    border: 4px solid var(--gold-light);
    box-shadow: 0 10px 40px rgba(184,147,45,0.2);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 12px;
    position: relative;
    overflow: hidden;
    z-index: 1;
  }

  .foto-placeholder::before {
    content: '';
    position: absolute;
    inset: 0;
    background: repeating-linear-gradient(
      45deg,
      transparent,
      transparent 20px,
      rgba(249,215,126,0.15) 20px,
      rgba(249,215,126,0.15) 21px
    );
  }

  .foto-placeholder .store-emoji {
    font-size: 64px;
    filter: drop-shadow(0 4px 8px rgba(184,147,45,0.4));
  }

  .foto-placeholder .foto-label {
    font-family: 'Cormorant Garamond', serif;
    font-size: 20px;
    color: var(--gold);
    letter-spacing: 2px;
    font-weight: 600;
  }

  .foto-placeholder .foto-sub {
    font-size: 12px;
    color: var(--text-light);
    letter-spacing: 1px;
  }

  /* Real photo if provided */
  .foto-tienda img.real-photo {
    width: 100%;
    border-radius: 20px;
    border: 4px solid var(--gold-light);
    box-shadow: 0 10px 40px rgba(184,147,45,0.2);
    position: relative;
    z-index: 1;
  }

  /* ── BALLOONS ── */
  .globo {
    width: 36px;
    height: 36px;
    border-radius: 50%;
    position: absolute;
    pointer-events: none;
  }

  .globo.amarillo {
    background: radial-gradient(circle at 30% 28%, #fff9e0 0%, #f9d23c 60%, #c8a020 100%);
    box-shadow: inset -4px -4px 8px rgba(255,255,255,0.35), 0 4px 10px rgba(0,0,0,0.2);
  }

  .globo.blanco {
    background: radial-gradient(circle at 30% 28%, #fff 0%, #f0f0f0 60%, #d8d8d8 100%);
    box-shadow: inset -4px -4px 8px rgba(255,255,255,0.6), 0 4px 10px rgba(0,0,0,0.15);
  }

  .globo.rosado {
    background: radial-gradient(circle at 30% 28%, #ffe8f0 0%, #f9b8cc 60%, #e080a0 100%);
    box-shadow: inset -4px -4px 8px rgba(255,255,255,0.4), 0 4px 10px rgba(0,0,0,0.18);
  }

  /* ── FEATURES STRIP ── */
  .features {
    background: linear-gradient(135deg, #fffbf0, var(--gold-pale));
    border-top: 2px solid var(--gold-light);
    border-bottom: 2px solid var(--gold-light);
    padding: 28px 24px;
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 32px;
    position: relative;
    z-index: 1;
  }

  .feature-item {
    display: flex;
    align-items: center;
    gap: 12px;
    font-weight: 700;
    color: var(--gold);
    font-size: 14px;
    letter-spacing: 0.5px;
  }

  .feature-item .feat-icon {
    font-size: 28px;
  }

  /* ── FOOTER ── */
  footer {
    background: linear-gradient(180deg, var(--gold-pale) 0%, #ffefc0 100%);
    padding: 36px 24px 20px;
    position: relative;
    z-index: 1;
  }

  .footer-grid {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 28px;
    margin-bottom: 28px;
  }

  .footer-item {
    display: flex;
    align-items: center;
    gap: 12px;
    color: var(--text);
    font-weight: 600;
    font-size: 14px;
  }

  .footer-icon {
    width: 42px;
    height: 42px;
    background: white;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 20px;
    box-shadow: 0 3px 10px rgba(184,147,45,0.2);
    flex-shrink: 0;
  }

  .footer-item strong {
    display: block;
    font-size: 12px;
    color: var(--gold);
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-bottom: 2px;
  }

  .social-row {
    text-align: center;
    padding-top: 20px;
    border-top: 1px solid var(--gold-light);
  }

  .social-row p {
    font-size: 12px;
    color: var(--text-light);
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 14px;
    font-weight: 600;
  }

  .social-links {
    display: flex;
    justify-content: center;
    gap: 16px;
    flex-wrap: wrap;
  }

  .social-links a {
    display: inline-flex;
    align-items: center;
    gap: 7px;
    text-decoration: none;
    padding: 8px 20px;
    border-radius: 30px;
    font-weight: 700;
    font-size: 13px;
    background: white;
    color: var(--gold);
    border: 1.5px solid var(--gold-light);
    transition: all 0.25s;
    box-shadow: 0 2px 8px rgba(184,147,45,0.15);
  }

  .social-links a:hover {
    background: var(--gold);
    color: white;
    transform: translateY(-2px);
    box-shadow: 0 6px 16px rgba(184,147,45,0.35);
  }

  .copyright {
    text-align: center;
    margin-top: 20px;
    font-size: 11px;
    color: var(--text-light);
    letter-spacing: 1px;
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeDown {
    from { opacity: 0; transform: translateY(-20px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(14px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  @keyframes spin {
    to { transform: rotate(360deg); }
  }

  /* ── RESPONSIVE ── */
  @media (max-width: 700px) {
    .main-container { padding: 30px 16px; gap: 32px; }
    .categorias-panel { flex: 0 0 100%; }
    .foto-tienda { max-width: 100%; }
    .features { gap: 20px; }
    .footer-grid { gap: 18px; }
  }
</style>
</head>
<body>

<!-- ── HEADER ── -->
<header>
  <div class="logo-wrap">
    <h1>Ginlly</h1>
    <!-- Sunflower SVG (no external image needed) -->
    <svg class="girasol-svg" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" aria-label="Girasol">
      <!-- Petals -->
      <g>
        <ellipse cx="50" cy="18" rx="6" ry="14" fill="#f9c22e" transform="rotate(0 50 50)"/>
        <ellipse cx="50" cy="18" rx="6" ry="14" fill="#f9c22e" transform="rotate(45 50 50)"/>
        <ellipse cx="50" cy="18" rx="6" ry="14" fill="#f9c22e" transform="rotate(90 50 50)"/>
        <ellipse cx="50" cy="18" rx="6" ry="14" fill="#f9c22e" transform="rotate(135 50 50)"/>
        <ellipse cx="50" cy="18" rx="6" ry="14" fill="#f9d760" transform="rotate(22.5 50 50)"/>
        <ellipse cx="50" cy="18" rx="6" ry="14" fill="#f9d760" transform="rotate(67.5 50 50)"/>
        <ellipse cx="50" cy="18" rx="6" ry="14" fill="#f9d760" transform="rotate(112.5 50 50)"/>
        <ellipse cx="50" cy="18" rx="6" ry="14" fill="#f9d760" transform="rotate(157.5 50 50)"/>
      </g>
      <!-- Center -->
      <circle cx="50" cy="50" r="19" fill="#5a3010"/>
      <circle cx="50" cy="50" r="15" fill="#7a4820"/>
      <!-- Seed pattern -->
      <circle cx="50" cy="42" r="2" fill="#3a1808" opacity="0.7"/>
      <circle cx="44" cy="46" r="2" fill="#3a1808" opacity="0.7"/>
      <circle cx="56" cy="46" r="2" fill="#3a1808" opacity="0.7"/>
      <circle cx="42" cy="53" r="2" fill="#3a1808" opacity="0.7"/>
      <circle cx="50" cy="55" r="2" fill="#3a1808" opacity="0.7"/>
      <circle cx="58" cy="53" r="2" fill="#3a1808" opacity="0.7"/>
    </svg>
  </div>
  <h2>Tienda Multimarcas</h2>
  <p class="tagline">Encuentra todo <span class="sub-text">en un solo lugar</span></p>
  <p class="categorias-tag">Moda &bull; Belleza &bull; Accesorios &bull; Hogar &bull; Y más</p>
</header>

<div class="divider"></div>

<!-- ── MAIN CONTENT ── -->
<div class="main-container">

  <!-- Category List -->
  <div class="categorias-panel">
    <h3>Nuestras categorías</h3>
    <ul class="categorias">
      <li><div class="cat-icon">👗</div> Ropa femenina</li>
      <li><div class="cat-icon">🧸</div> Ropa infantil</li>
      <li><div class="cat-icon">💆</div> Productos para el cabello y corporal</li>
      <li><div class="cat-icon">👜</div> Bolsos</li>
      <li><div class="cat-icon">🕶️</div> Accesorios y gafas</li>
      <li><div class="cat-icon">🎠</div> Juguetería</li>
      <li><div class="cat-icon">🧊</div> Termos</li>
      <li><div class="cat-icon">🎁</div> Detalles y mucho más</li>
    </ul>
  </div>

  <!-- Store Photo / Placeholder -->
  <div class="foto-tienda" id="foto-tienda">
    <!-- Replace this div with <img src="foto-local.jpg" class="real-photo" alt="Tienda Ginlly"> when you have the image -->
    <div class="foto-placeholder">
      <div class="store-emoji">🌻</div>
      <div class="foto-label">Ginlly · Tienda Multimarcas</div>
      <div class="foto-sub">Aquí va la foto de tu local</div>
    </div>
  </div>

</div>

<!-- ── FEATURES STRIP ── -->
<div class="features">
  <div class="feature-item"><span class="feat-icon">🌟</span> Productos seleccionados</div>
  <div class="feature-item"><span class="feat-icon">🚚</span> Envíos nacionales seguros</div>
  <div class="feature-item"><span class="feat-icon">💛</span> Atención personalizada</div>
  <div class="feature-item"><span class="feat-icon">🏷️</span> Mejores precios</div>
</div>

<!-- ── FOOTER ── -->
<footer>
  <div class="footer-grid">

    <div class="footer-item">
      <div class="footer-icon">📱</div>
      <div>
        <strong>WhatsApp</strong>
        305 215 7455
      </div>
    </div>

    <div class="footer-item">
      <div class="footer-icon">📍</div>
      <div>
        <strong>Ubicación</strong>
        Kra 24 # 17a-03, Bosconia, César
      </div>
    </div>

    <div class="footer-item">
      <div class="footer-icon">📦</div>
      <div>
        <strong>Envíos</strong>
        Nacionales 100% seguros
      </div>
    </div>

  </div>

  <div class="social-row">
    <p>Síguenos en redes sociales</p>
    <div class="social-links">
      <a href="#" aria-label="Facebook">📘 Facebook</a>
      <a href="#" aria-label="Instagram">📸 Instagram</a>
      <a href="#" aria-label="TikTok">🎵 TikTok</a>
      <a href="#" aria-label="Handle">🌻 @ginlly.tienda</a>
    </div>
  </div>

  <p class="copyright">© 2026 Ginlly Tienda Multimarcas · Bosconia, César, Colombia</p>
</footer>

<!-- ── BALLOON SCRIPT ── -->
<script>
  const container = document.getElementById('foto-tienda');
  const types = ['amarillo', 'blanco', 'rosado'];

  for (let i = 0; i < 14; i++) {
    const g = document.createElement('div');
    g.classList.add('globo', types[Math.floor(Math.random() * types.length)]);
    const size = 28 + Math.random() * 22;
    g.style.width  = size + 'px';
    g.style.height = size + 'px';
    g.style.left   = Math.random() * 88 + '%';
    g.style.top    = 105 + Math.random() * 20 + '%';
    container.appendChild(g);

    (function animate(el) {
      const speed = 0.8 + Math.random() * 1.8;
      const swayAmp = Math.random() * 12 - 6;
      const phase = Math.random() * Math.PI * 2;
      let top = parseFloat(el.style.top);
      let left = parseFloat(el.style.left);

      function tick() {
        top -= speed * 0.04;
        left += Math.sin(Date.now() / 600 + phase) * swayAmp * 0.012;
        el.style.top  = top + '%';
        el.style.left = left + '%';
        if (top < -12) { top = 108; left = Math.random() * 88; }
        requestAnimationFrame(tick);
      }
      tick();
    })(g);
  }
</script>

</body>
</html>
