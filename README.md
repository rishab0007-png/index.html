<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Connect with Me</title>
  <style>
    /* ---------- BASE LAYOUT ---------- */
    body {
      margin: 0;
      height: 100vh;
      background: radial-gradient(circle at top, #222 0, #000 55%, #050505 100%);
      overflow: hidden;
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      position: relative;
      color: #fff;
    }

    /* Subtle moving gradient glow behind card */
    .bg-orbit {
      position: absolute;
      width: 520px;
      height: 520px;
      border-radius: 50%;
      background: conic-gradient(
        from 0deg,
        #2ba84a55,
        #0088cc55,
        #e1306c55,
        #2ba84a55
      );
      filter: blur(40px);
      opacity: 0.6;
      animation: orbitGlow 22s linear infinite;
      z-index: 1;
    }

    .container {
      background: linear-gradient(145deg, rgba(30, 30, 30, 0.96), rgba(12, 12, 12, 0.96));
      padding: 34px 20px;
      border-radius: 22px;
      text-align: center;
      box-shadow: 0 0 20px rgba(0, 0, 0, 0.7), 0 0 55px rgba(0, 0, 0, 0.9);
      width: 95vw;
      max-width: 460px;
      box-sizing: border-box;
      z-index: 10;
      border: 1px solid rgba(255, 255, 255, 0.08);

      /* Card entrance + subtle float */
      opacity: 0;
      transform: translateY(30px) scale(0.96);
      animation: cardIn 0.9s ease-out forwards, cardFloat 6s ease-in-out 0.9s infinite;
    }

    h1 {
      font-weight: 500;
      font-size: 1.8rem;
      margin: 0 0 10px;
      letter-spacing: 1.4px;
    }

    .subtitle {
      font-size: 0.9rem;
      color: #c7c7c7;
      margin-bottom: 24px;
      opacity: 0;
      transform: translateY(8px);
      animation: fadeUp 0.9s ease-out 0.15s forwards;
    }

    .icon-row {
      display: flex;
      flex-direction: row;
      gap: 32px;
      justify-content: center;
      align-items: center;
      margin-top: 10px;
    }

    a {
      color: white;
      text-decoration: none;
    }

    /* ---------- ICONS + ANIMATIONS ---------- */
    .icon-wrapper {
      position: relative;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      padding: 6px;
      border-radius: 28%;
      overflow: visible;
      cursor: pointer;

      opacity: 0;
      transform: translateY(18px) scale(0.9);
    }
    .icon-wrapper:nth-child(1) {
      animation: fadeUp 0.8s ease-out 0.25s forwards;
    }
    .icon-wrapper:nth-child(2) {
      animation: fadeUp 0.8s ease-out 0.4s forwards;
    }
    .icon-wrapper:nth-child(3) {
      animation: fadeUp 0.8s ease-out 0.55s forwards;
    }

    /* Pulsing ring behind icons */
    .icon-pulse {
      position: absolute;
      width: 120%;
      height: 120%;
      border-radius: 32%;
      border: 1px solid rgba(255, 255, 255, 0.35);
      opacity: 0.6;
      transform: scale(0.8);
      animation: pulseRing 2.7s ease-out infinite;
      pointer-events: none;
    }

    img.social-icon {
      width: 78px;
      height: 78px;
      transition: transform 0.26s ease, box-shadow 0.26s ease, filter 0.26s ease;
      border-radius: 25%;
      box-shadow: 0 0 18px rgba(255, 255, 255, 0.6), 0 0 12px rgba(255, 255, 255, 0.4);
    }

    a[aria-label="WhatsApp"] img.social-icon {
      filter: drop-shadow(0 0 14px #2ba84a);
    }
    a[aria-label="Instagram"] img.social-icon {
      filter: drop-shadow(0 0 14px #e1306c);
    }
    a[aria-label="Telegram"] img.social-icon {
      filter: drop-shadow(0 0 14px #0088cc);
    }

    /* Hover / tap effect */
    .icon-wrapper:hover img.social-icon,
    .icon-wrapper:active img.social-icon {
      transform: scale(1.14) translateY(-4px) rotate(-4deg);
      box-shadow: 0 0 26px #fff, 0 0 20px rgba(255, 255, 255, 0.85);
      filter: brightness(1.08);
    }

    /* ---------- SNOWFALL ---------- */
    .snowflake {
      position: absolute;
      top: -18px;
      width: 14px;
      height: 14px;
      background: white;
      border-radius: 60%;
      opacity: 0.7;
      animation: fall linear infinite;
      z-index: 1;
      filter: blur(1px);
    }

    @keyframes fall {
      100% {
        transform: translateY(100vh);
        opacity: 0.06;
      }
    }

    /* ---------- KEYFRAMES ---------- */
    @keyframes cardIn {
      0% {
        opacity: 0;
        transform: translateY(30px) scale(0.94);
      }
      100% {
        opacity: 1;
        transform: translateY(0) scale(1);
      }
    }

    @keyframes cardFloat {
      0% {
        transform: translateY(0) scale(1);
      }
      50% {
        transform: translateY(-6px) scale(1.01);
      }
      100% {
        transform: translateY(0) scale(1);
      }
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

    @keyframes pulseRing {
      0% {
        opacity: 0.65;
        transform: scale(0.8);
      }
      70% {
        opacity: 0;
        transform: scale(1.25);
      }
      100% {
        opacity: 0;
        transform: scale(1.25);
      }
    }

    @keyframes orbitGlow {
      0% {
        transform: translate(-14px, -10px) rotate(0deg);
      }
      50% {
        transform: translate(10px, 4px) rotate(180deg);
      }
      100% {
        transform: translate(-14px, -10px) rotate(360deg);
      }
    }

    /* ---------- MOBILE ---------- */
    @media only screen and (max-width: 480px) {
      .bg-orbit {
        width: 360px;
        height: 360px;
        filter: blur(32px);
      }
      .container {
        max-width: 100vw !important;
        width: 96vw !important;
        padding: 32px 5vw !important;
        border-radius: 18px;
      }
      h1 {
        font-size: 1.6rem;
      }
      .subtitle {
        font-size: 0.86rem;
      }
      img.social-icon {
        width: 94px;
        height: 94px;
      }
      .icon-row {
        gap: 26px;
      }
    }
  </style>
</head>
<body>
  <!-- moving glow background -->
  <div class="bg-orbit"></div>

  <!-- snow is added by JS below -->

  <div class="container">
    <h1>Connect with Me</h1>
    <div class="subtitle">Tap any icon to reach me instantly</div>

    <div class="icon-row">
      <a href="https://wa.me/9897978494" target="_blank" rel="noopener noreferrer" aria-label="WhatsApp" class="icon-wrapper">
        <span class="icon-pulse"></span>
        <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" alt="WhatsApp" class="social-icon" />
      </a>

      <a href="https://www.instagram.com/rishab_gautam__007" target="_blank" rel="noopener noreferrer" aria-label="Instagram" class="icon-wrapper">
        <span class="icon-pulse"></span>
        <img src="https://upload.wikimedia.org/wikipedia/commons/e/e7/Instagram_logo_2016.svg" alt="Instagram" class="social-icon" />
      </a>

      <a href="https://t.me/+919897978494" target="_blank" rel="noopener noreferrer" aria-label="Telegram" class="icon-wrapper">
        <span class="icon-pulse"></span>
        <img src="https://upload.wikimedia.org/wikipedia/commons/8/82/Telegram_logo.svg" alt="Telegram" class="social-icon" />
      </a>
    </div>
  </div>

  <script>
    // Snowfall with random horizontal drift for more life
    const snowflakeCount = 110;
    for (let i = 0; i < snowflakeCount; i++) {
      const snowflake = document.createElement("div");
      snowflake.classList.add("snowflake");

      const size = Math.random() * 8 + 6; // 6px to 14px
      const left = Math.random() * window.innerWidth;
      const duration = Math.random() * 7 + 7; // 7s to 14s
      const delay = Math.random() * 14;
      const horizontalDrift = Math.random() * 60 - 30; // -30px to 30px

      snowflake.style.width = `${size}px`;
      snowflake.style.height = `${size}px`;
      snowflake.style.left = `${left}px`;
      snowflake.style.animationDuration = `${duration}s`;
      snowflake.style.animationDelay = `${delay}s`;

      // add small horizontal drift using inline animation
      snowflake.style.animationTimingFunction = "linear";
      snowflake.style.animationName = "fall";

      // extra transform using JS for slight X move
      snowflake.animate(
        [
          { transform: `translate(${horizontalDrift}px, 0)` },
          { transform: `translate(${-horizontalDrift}px, 100vh)` }
        ],
        {
          duration: (duration + Math.random() * 3) * 1000,
          delay: delay * 1000,
          iterations: Infinity
        }
      );

      document.body.appendChild(snowflake);
    }
  </script>
</body>
</html>
