<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Connect with Me</title>
  <style>
    body {
      margin: 0;
      height: 100vh;
      background: linear-gradient(to bottom, #0d0d0d, #1a1a1a);
      overflow: hidden;
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      position: relative;
    }
    .container {
      background-color: rgba(40, 40, 40, 0.8);
      padding: 32px 18px;
      border-radius: 22px;
      text-align: center;
      box-shadow: 0 0 18px rgba(0, 0, 0, 0.48);
      width: 97vw;
      max-width: 480px;
      z-index: 10;
    }
    h1 {
      color: white;
      font-weight: 500;
      font-size: 1.7rem;
      margin-bottom: 28px;
      letter-spacing: 1.3px;
    }
    .icon-row {
      display: flex;
      flex-direction: column;
      gap: 38px;
      align-items: center;
    }
    a {
      color: white;
      text-decoration: none;
    }
    img.social-icon {
      width: 82px;
      height: 82px;
      transition: transform 0.3s, box-shadow 0.3s;
      filter: drop-shadow(0 0 15px #2ba84a); /* WhatsApp green by default */
      box-shadow: 0 0 22px #fff, 0 0 12px #aaa;
      border-radius: 25%;
    }
    /* Glowing colors by platform */
    a[aria-label="Instagram"] img.social-icon {
      filter: drop-shadow(0 0 15px #e1306c);
      box-shadow: 0 0 30px #e1306c60, 0 0 12px #fff;
    }
    a[aria-label="Telegram"] img.social-icon {
      filter: drop-shadow(0 0 15px #0088cc);
      box-shadow: 0 0 30px #0088cc60, 0 0 12px #fff;
    }
    img.social-icon:active, img.social-icon:hover {
      transform: scale(1.22) rotate(-6deg);
      opacity: 0.95;
      box-shadow: 0 0 32px #fff, 0 0 24px #aaa;
    }
    .snowflake {
      position: absolute;
      top: -18px;
      width: 20px;
      height: 20px;
      background: white;
      border-radius: 60%;
      opacity: 0.67;
      animation: fall linear infinite;
      z-index: 1;
      filter: blur(1px);
    }
    @keyframes fall {
      100% {
        transform: translateY(100vh);
        opacity: 0.07;
      }
    }
    /* Responsive tweaks */
    @media only screen and (max-width: 480px) {
      .container {
        max-width: 99vw;
        padding: 18px 2vw;
        border-radius: 16px;
      }
      h1 {
        font-size: 1.17rem;
        margin-bottom: 18px;
      }
      img.social-icon {
        width: 56px;
        height: 56px;
      }
      .icon-row {
        gap: 28px;
      }
    }
  </style>
</head>
<body>
  <script>
    const snowflakeCount = 36;
    for (let i = 0; i < snowflakeCount; i++) {
      const snowflake = document.createElement("div");
      snowflake.classList.add("snowflake");
      const size = Math.random() * 16 + 20; // 20px to 36px snowflakes
      const left = Math.random() * window.innerWidth;
      const duration = Math.random() * 6 + 8;
      const delay = Math.random() * 12;
      snowflake.style.width = `${size}px`;
      snowflake.style.height = `${size}px`;
      snowflake.style.left = `${left}px`;
      snowflake.style.animationDuration = `${duration}s`;
      snowflake.style.animationDelay = `${delay}s`;
      document.body.appendChild(snowflake);
    }
  </script>
  <div class="container">
    <h1>Connect with Me</h1>
    <div class="icon-row">
      <a href="https://wa.me/9897978494" target="_blank" rel="noopener noreferrer" aria-label="WhatsApp">
        <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" alt="WhatsApp" class="social-icon" />
      </a>
      <a href="https://www.instagram.com/rishab_gautam__007" target="_blank" rel="noopener noreferrer" aria-label="Instagram">
        <img src="https://upload.wikimedia.org/wikipedia/commons/e/e7/Instagram_logo_2016.svg" alt="Instagram" class="social-icon" />
      </a>
      <a href="https://t.me/+919897978494" target="_blank" rel="noopener noreferrer" aria-label="Telegram">
        <img src="https://upload.wikimedia.org/wikipedia/commons/8/82/Telegram_logo.svg" alt="Telegram" class="social-icon" />
      </a>
    </div>
  </div>
</body>
</html>
