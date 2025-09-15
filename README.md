<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Connect with Me</title>
  <style>
    /* General body styles */
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

    /* Snowflake styling */
    .snowflake {
      position: absolute;
      top: -10px;
      width: 10px;
      height: 10px;
      background: white;
      border-radius: 50%;
      opacity: 0.8;
      animation: fall linear infinite;
    }

    @keyframes fall {
      to {
        transform: translateY(100vh);
        opacity: 0;
      }
    }

    /* Container styles */
    .container {
      background-color: rgba(40, 40, 40, 0.7);
      padding: 30px;
      border-radius: 20px;
      text-align: center;
      box-shadow: 0 0 15px rgba(0, 0, 0, 0.5);
      z-index: 10;
    }

    .icon-row {
      display: flex;
      justify-content: center;
      gap: 40px;
    }

    a {
      color: white;
      text-decoration: none;
    }

    a:hover {
      opacity: 0.8;
    }

    img.social-icon {
      width: 70px;
      height: 70px;
      transition: transform 0.3s;
      filter: drop-shadow(0 0 3px black);
    }

    img.social-icon:hover {
      transform: scale(1.2);
    }

    h1 {
      color: white;
      margin-bottom: 20px;
      font-weight: 400;
    }
  </style>
</head>
<body>
  <!-- Snowflakes (you can generate more dynamically with JavaScript) -->
  <script>
    const snowflakeCount = 100;
    for (let i = 0; i < snowflakeCount; i++) {
      const snowflake = document.createElement("div");
      snowflake.classList.add("snowflake");

      const size = Math.random() * 5 + 2;
      const left = Math.random() * window.innerWidth;
      const duration = Math.random() * 5 + 5;
      const delay = Math.random() * 10;

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
