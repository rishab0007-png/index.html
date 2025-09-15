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
      padding: 18px 8px;
      border-radius: 18px;
      text-align: center;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.4);
      width: 95vw;
      max-width: 350px;
      z-index: 10;
    }
    h1 {
      color: white;
      font-weight: 500;
      font-size: 1.4rem;
      margin-bottom: 18px;
      letter-spacing: 1px;
    }
    .icon-row {
      display: flex;
      flex-direction: column;
      gap: 28px;
      align-items: center;
    }
    a {
      color: white;
      text-decoration: none;
    }
    img.social-icon {
      width: 52px;
      height: 52px;
      transition: transform 0.3s;
      filter: drop-shadow(0 0 3px black);
    }
    img.social-icon:active, img.social-icon:hover {
      transform: scale(1.13);
      opacity: 0.9;
    }

    /* Snowflake styling - minimal for mobile */
    .snowflake {
      position: absolute;
      top: -10px;
      width: 8px;
      height: 8px;
      background: white;
      border-radius: 50%;
      opacity: 0.8;
      animation: fall linear infinite;
      z-index: 1;
    }
    @keyframes fall {
      to {
        transform: translateY(100vh);
        opacity: 0;
      }
    }

    /* Responsive tweaks */
    @media only screen and (max-width: 480px) {
      .container {
        max-width: 95vw;
        padding: 12px 3vw;
        border-radius: 15px;
      }
      h1 {
        font-size: 1.13rem;
        margin-bottom: 14px;
      }
      img.social-icon {
        width: 43px;
        height: 43px;
      }
      .icon-row {
        gap: 22px;
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
      const size = Math.random() * 4 + 2;
      const left = Math.random() * window.innerWidth;
      const duration = Math.random() * 6 + 6;
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
