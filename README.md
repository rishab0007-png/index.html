<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Connect with Me</title>
  <style>
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

    .vignette {
      position: fixed;
      inset: 0;
      pointer-events: none;
      background: radial-gradient(circle at center, transparent 0, rgba(0,0,0,0.35) 55%, rgba(0,0,0,0.9) 100%);
      z-index: 1;
    }

    .container {
      position: relative;
      z-index: 5;
      width: 95vw;
      max-width: 460px;
      padding: 30px 22px 26px;
      border-radius: 22px;
      background: linear-gradient(135deg, rgba(255,255,255,0.08), rgba(10,10,20,0.85));
      border: 1px solid rgba(255, 255, 255, 0.16);
      backdrop-filter: blur(14px);
      -webkit-backdrop-filter: blur(14px);
      box-shadow:
        0 0 30px rgba(0,0,0,0.9),
        0 0 60px rgba(0,0,0,0.9),
        0 0 30px rgba(108, 122, 255, 0.35);
      animation: cardFloat 7s ease-in-out 1.5s infinite;
      overflow: hidden;
    }

    .container::before {
      content: "";
      position: absolute;
      inset: 0;
      background: linear-gradient(115deg, transparent 30%, rgba(255,255,255,0.16) 50%, transparent 70%);
      transform: translateX(-140%);
      opacity: 0.9;
      pointer-events: none;
      animation: lightSweep 4.5s ease-in-out 1.4s infinite;
    }

    h1 {
      font-weight: 500;
      font-size: 1.8rem;
      letter-spacing: 1.4px;
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
      margin-bottom: 20px;
    }

    .line {
      width: 72px;
      height: 1px;
      margin: 0 auto 20px;
      background: linear-gradient(to right, transparent, #57f5ff, transparent);
    }

    .icon-row {
      display: flex;
      justify-content: center;
      align-items: flex-end;
      gap: 28px;
      margin-bottom: 12px;
      position: relative;
      padding-top: 40px;
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
      /* start high and invisible; JS will trigger fall animation */
      opacity: 0;
      transform: translateY(-220px);
    }

    .icon-pulse {
      position: absolute;
      inset: 10%;
      border-radius: 30%;
      border: 1px solid rgba(255, 255, 255, 0.5);
      opacity: 0;
      transform: scale(0.7);
      pointer-events: none;
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
      transform: scale(1.12) translateY(-4px);
      box-shadow: 0 0 30px #fff, 0 0 26px rgba(255,255,255,0.9);
      filter: brightness(1.05);
    }

    .note {
      font-size: 0.78rem;
      text-align: center;
      color: #b6b6d6;
      margin-top: 6px;
    }

    /* Snowflakes in background */
    .snowflake {
      position: fixed;
      top: -20px;
      width: 8px;
      height: 8px;
      background: white;
      border-radius: 50%;
      opacity: 0.7;
      filter: blur(1px);
      z-index: 0;
      animation: snowFall linear infinite;
    }

    /* Small cinematic dust particles */
    .particle {
      position: fixed;
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

    /* KEYFRAMES */

    @keyframes cardFloat {
      0%   { transform: translateY(0); }
      50%  { transform: translateY(-6px); }
      100% { transform: translateY(0); }
    }

    @keyframes lightSweep {
      0%   { transform: translateX(-140%); }
      50%  { transform: translateX(0); }
      100% { transform: translateX(140%); }
    }

    /* icon falling with bounce and settling */
    @keyframes iconFall {
      0% {
        opacity: 0;
        transform: translateY(-220px);
      }
      40% {
        opacity: 1;
      }
      70% {
        transform: translateY(10px);
      }
      85% {
        transform: translateY(-6px);
      }
      100% {
        transform: translateY(0);
      }
    }

    @keyframes pulseRing {
      0% {
        opacity: 0.7;
        transform: scale(0.7);
      }
      70% {
        opacity: 0;
        transform: scale(1.3);
      }
      100% {
        opacity: 0;
        transform: scale(1.3);
      }
    }

    @keyframes snowFall {
      0% {
        transform: translate3d(0, -20px, 0);
        opacity: 0;
      }
      10% {
        opacity: 0.8;
      }
      100% {
        transform: translate3d(-30px, 110vh, 0);
        opacity: 0;
      }
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

    @media (max-width: 480px) {
      .container {
        width: 94vw;
        padding: 26px 6vw 22px;
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
  <div class="vignette"></div>

  <div class="container">
    <h1>Connect with Me</h1>
    <div class="subtitle">Icons fall like snow, then wait for you</div>
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

    <div class="note">Available on WhatsApp, Instagram, and Telegram.</div>
  </div>

  <script>
    // Make icons fall from top with staggered timing
    const iconWrappers = document.querySelectorAll(".icon-wrapper");

    iconWrappers.forEach((icon, index) => {
      const delay = 400 + index * 250; // ms
      setTimeout(() => {
        icon.style.animation = `iconFall 1.2s cubic-bezier(0.25, 0.9, 0.3, 1.2) forwards`;
        // start pulse a bit after landing
        const pulse = icon.querySelector(".icon-pulse");
        setTimeout(() => {
          pulse.style.opacity = "0.7";
          pulse.style.animation = "pulseRing 2.6s ease-out infinite";
        }, 900);
      }, delay);
    });

    // Background snow falling from top
    const snowCount = 45;
    for (let i = 0; i < snowCount; i++) {
      const s = document.createElement("div");
      s.classList.add("snowflake");
      const size = Math.random() * 6 + 4; // 4–10px
      const left = Math.random() * window.innerWidth;
      const duration = 8000 + Math.random() * 6000;

      s.style.width = size + "px";
      s.style.height = size + "px";
      s.style.left = left + "px";
      s.style.animationDuration = duration + "ms";
      s.style.animationDelay = Math.random() * 8000 + "ms";

      document.body.appendChild(s);
    }

    // Cinematic small particles drifting
    const particleCount = 30;
    for (let i = 0; i < particleCount; i++) {
      const p = document.createElement("div");
      p.classList.add("particle");
      const startX = Math.random() * window.innerWidth;
      const startY = Math.random() * window.innerHeight;
      const duration = 9000 + Math.random() * 9000;

      p.style.left = startX + "px";
      p.style.top = startY + "px";
      p.style.animationDuration = duration + "ms";
      p.style.animationDelay = Math.random() * 9000 + "ms";

      document.body.appendChild(p);
    }
  </script>
</body>
</html>
