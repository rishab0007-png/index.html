<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Connect with Me</title>
  <style>
    /* ---------- GLOBAL ---------- */
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      height: 100vh;
      overflow: hidden;
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      display: flex;
      align-items: center;
      justify-content: center;
      background: radial-gradient(circle at top, #1e2140 0, #050510 45%, #000 100%);
      position: relative;
      color: #fff;
    }

    /* Vignette cinematic dark edges */
    .vignette {
      position: fixed;
      inset: 0;
      pointer-events: none;
      background: radial-gradient(circle at center, transparent 0, rgba(0,0,0,0.3) 55%, rgba(0,0,0,0.85) 100%);
      z-index: 1;
    }

    /* Intro black fade like movie */
    .intro-fade {
      position: fixed;
      inset: 0;
      background: #000;
      z-index: 999;
      animation: introFade 1.4s ease-out forwards;
    }

    /* Moving light blobs (parallax style) */
    .light-orbit {
      position: absolute;
      border-radius: 50%;
      filter: blur(40px);
      opacity: 0.7;
      z-index: 0;
      pointer-events: none;
      mix-blend-mode: screen;
    }
    .light-orbit.one {
      width: 520px;
      height: 520px;
      background: radial-gradient(circle, #2ba84a55, transparent 60%);
      animation: orbitOne 32s linear infinite;
    }
    .light-orbit.two {
      width: 420px;
      height: 420px;
      background: radial-gradient(circle, #0088cc70, transparent 60%);
      animation: orbitTwo 40s linear infinite;
    }
    .light-orbit.three {
      width: 360px;
      height: 360px;
      background: radial-gradient(circle, #e1306c70, transparent 60%);
      animation: orbitThree 50s linear infinite;
    }

    /* ---------- GLASS CARD ---------- */
    .container {
      position: relative;
      z-index: 5;
      width: 95vw;
      max-width: 460px;
      padding: 32px 22px 26px;
      border-radius: 22px;
      background: linear-gradient(135deg, rgba(255,255,255,0.08), rgba(10,10,20,0.85));
      border: 1px solid rgba(255, 255, 255, 0.16);
      backdrop-filter: blur(14px);
      -webkit-backdrop-filter: blur(14px);
      box-shadow:
        0 0 30px rgba(0,0,0,0.9),
        0 0 60px rgba(0,0,0,0.9),
        0 0 30px rgba(108, 122, 255, 0.35);

      opacity: 0;
      transform: translateY(32px) scale(0.96);
      animation: cardIn 1.1s cubic-bezier(0.23, 1, 0.32, 1) 0.4s forwards,
                 cardFloat 7s ease-in-out 1.5s infinite;
      overflow: hidden;
    }

    /* Light sweep over card */
    .container::before {
      content: "";
      position: absolute;
      inset: 0;
      background: linear-gradient(115deg, transparent 30%, rgba(255,255,255,0.22) 50%, transparent 70%);
      transform: translateX(-140%);
      opacity: 0.9;
      pointer-events: none;
      animation: lightSweep 4.2s ease-in-out 1.2s infinite;
    }

    h1 {
      font-weight: 500;
      font-size: 1.9rem;
      letter-spacing: 1.5px;
      text-transform: uppercase;
      text-align: center;
      margin-bottom: 8px;
    }

    .subtitle {
      text-align: center;
      font-size: 0.9rem;
      color: #d0d0e5;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      opacity: 0;
      transform: translateY(12px);
      animation: fadeUp 0.9s ease-out 0.7s forwards;
      margin-bottom: 22px;
    }

    .line {
      width: 72px;
      height: 1px;
      margin: 0 auto 22px;
      background: linear-gradient(to right, transparent, #57f5ff, transparent);
      opacity: 0;
      animation: fadeIn 1s ease-out 0.85s forwards;
    }

    .icon-row {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 28px;
      margin-bottom: 12px;
    }

    a {
      text-decoration: none;
      color: inherit;
    }

    .icon-wrapper {
      position: relative;
      padding: 8px;
      border-radius: 28%;
      cursor: pointer;
      opacity: 0;
      transform: translateY(18px) scale(0.9);
    }

    .icon-wrapper:nth-child(1) {
      animation: fadeUp 0.85s ease-out 0.9s forwards;
    }
    .icon-wrapper:nth-child(2) {
      animation: fadeUp 0.85s ease-out 1.05s forwards;
    }
    .icon-wrapper:nth-child(3) {
      animation: fadeUp 0.85s ease-out 1.2s forwards;
    }

    .icon-pulse {
      position: absolute;
      inset: 8%;
      border-radius: 30%;
      border: 1px solid rgba(255, 255, 255, 0.5);
      opacity: 0.7;
      transform: scale(0.7);
      pointer-events: none;
      animation: pulseRing 2.9s ease-out infinite;
    }

    img.social-icon {
      width: 80px;
      height: 80px;
      border-radius: 25%;
      transition: transform 0.25s ease, box-shadow 0.25s ease, filter 0.25s ease;
      box-shadow: 0 0 22px rgba(255, 255, 255, 0.65);
    }
    a[aria-label="WhatsApp"] img.social-icon {
      filter: drop-shadow(0 0 18px #2ba84a);
    }
    a[aria-label="Instagram"] img.social-icon {
      filter: drop-shadow(0 0 18px #e1306c);
    }
    a[aria-label="Telegram"] img.social-icon {
      filter: drop-shadow(0 0 18px #0088cc);
    }

    .icon-wrapper:hover img.social-icon,
    .icon-wrapper:active img.social-icon {
      transform: scale(1.16) translateY(-4px);
      box-shadow: 0 0 30px #fff, 0 0 26px rgba(255,255,255,0.9);
      filter: brightness(1.05);
    }

    .note {
      font-size: 0.78rem;
      text-align: center;
      color: #b6b6d6;
      opacity: 0;
      transform: translateY(10px);
      animation: fadeUp 0.9s ease-out 1.4s forwards;
    }

    /* ---------- PARTICLES (like cinematic dust) ---------- */
    .particle {
      position: absolute;
      width: 3px;
      height: 3px;
      border-radius: 50%;
      background: rgba(255, 255, 255, 0.7);
      opacity: 0.6;
      filter: blur(0.7px);
      animation: particleDrift linear infinite;
      z-index: 0;
      pointer-events: none;
    }

    @keyframes particleDrift {
      0% {
        transform: translate3d(0, 0, 0);
        opacity: 0;
      }
      10% {
        opacity: 0.7;
      }
      90% {
        opacity: 0.7;
      }
      100% {
        transform: translate3d(40px, -120px, 0);
        opacity: 0;
      }
    }

    /* ---------- KEYFRAMES ---------- */
    @keyframes introFade {
      0% { opacity: 1; }
      60% { opacity: 1; }
      100% { opacity: 0; visibility: hidden; }
    }

    @keyframes cardIn {
      0% {
        opacity: 0;
        transform: translateY(32px) scale(0.9);
      }
      100% {
        opacity: 1;
        transform: translateY(0) scale(1);
      }
    }

    @keyframes cardFloat {
      0%   { transform: translateY(0) scale(1); }
      50%  { transform: translateY(-8px) scale(1.01); }
      100% { transform: translateY(0) scale(1); }
    }

    @keyframes fadeUp {
      0% {
        opacity: 0;
        transform: translateY(16px) scale(0.96);
      }
      100% {
        opacity: 1;
        transform: translateY(0) scale(1);
      }
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to   { opacity: 1; }
    }

    @keyframes pulseRing {
      0% {
        opacity: 0.8;
        transform: scale(0.7);
      }
      70% {
        opacity: 0;
        transform: scale(1.2);
      }
      100% {
        opacity: 0;
        transform: scale(1.2);
      }
    }

    @keyframes lightSweep {
      0% {
        transform: translateX(-140%);
      }
      50% {
        transform: translateX(0);
      }
      100% {
        transform: translateX(140%);
      }
    }

    @keyframes orbitOne {
      0%   { transform: translate(-120px, -120px) rotate(0deg); }
      50%  { transform: translate(40px, 30px) rotate(180deg); }
      100% { transform: translate(-120px, -120px) rotate(360deg); }
    }

    @keyframes orbitTwo {
      0%   { transform: translate(120px, 160px) rotate(0deg); }
      50%  { transform: translate(-40px, 40px) rotate(180deg); }
      100% { transform: translate(120px, 160px) rotate(360deg); }
    }

    @keyframes orbitThree {
      0%   { transform: translate(0px, 40px) rotate(0deg); }
      50%  { transform: translate(-80px, -40px) rotate(180deg); }
      100% { transform: translate(0px, 40px) rotate(360deg); }
    }

    /* ---------- MOBILE ---------- */
    @media (max-width: 480px) {
      .container {
        width: 94vw;
        padding: 28px 6vw 22px;
        border-radius: 18px;
      }
      h1 {
        font-size: 1.5rem;
      }
      .subtitle {
        font-size: 0.78rem;
      }
      img.social-icon {
        width: 74px;
        height: 74px;
      }
      .icon-row {
        gap: 22px;
      }
    }
  </style>
</head>
<body>
  <!-- Cinematic overlays -->
  <div class="intro-fade"></div>
  <div class="vignette"></div>

  <!-- Moving lights -->
  <div class="light-orbit one"></div>
  <div class="light-orbit two"></div>
  <div class="light-orbit three"></div>

  <!-- Glass card -->
  <div class="container">
    <h1>Connect with Me</h1>
    <div class="subtitle">Tap any icon to start a conversation</div>
    <div class="line"></div>

    <div class="icon-row">
      <a href="https://wa.me/9897978494" target="_blank" rel="noopener noreferrer" aria-label="WhatsApp" class="icon-wrapper">
        <span class="icon-pulse"></span>
        <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" alt="WhatsApp" class="social-icon">
      </a>

      <a href="https://www.instagram.com/rishab_gautam__007" target="_blank" rel="noopener noreferrer" aria-label="Instagram" class="icon-wrapper">
        <span class="icon-pulse"></span>
        <img src="https://upload.wikimedia.org/wikipedia/commons/e/e7/Instagram_logo_2016.svg" alt="Instagram" class="social-icon">
      </a>

      <a href="https://t.me/+919897978494" target="_blank" rel="noopener noreferrer" aria-label="Telegram" class="icon-wrapper">
        <span class="icon-pulse"></span>
        <img src="https://upload.wikimedia.org/wikipedia/commons/8/82/Telegram_logo.svg" alt="Telegram" class="social-icon">
      </a>
    </div>

    <div class="note">Available on WhatsApp, Instagram and Telegram for quick replies.</div>
  </div>

  <script>
    // Small floating particles for cinematic feel
    const particleCount = 40;
    for (let i = 0; i < particleCount; i++) {
      const p = document.createElement("div");
      p.classList.add("particle");
      const startX = Math.random() * window.innerWidth;
      const startY = Math.random() * window.innerHeight;
      const duration = 8000 + Math.random() * 8000;

      p.style.left = startX + "px";
      p.style.top = startY + "px";
      p.style.animationDuration = duration + "ms";
      p.style.animationDelay = Math.random() * 8000 + "ms";

      document.body.appendChild(p);
    }
  </script>
</body>
</html>
