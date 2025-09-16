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
      background-color: rgba(40, 40, 40, 0.85);
      padding: 36px 28px;
      border-radius: 22px;
      text-align: center;
      box-shadow: 0 0 15px rgba(0, 0, 0, 0.5);
      width: 95vw;
      max-width: 500px;
      z-index: 10;
    }

    h1 {
      color: white;
      font-weight: 500;
      font-size: 1.8rem;
      margin-bottom: 30px;
      letter-spacing: 1px;
    }

    .icon-row {
      display: flex;
      flex-direction: row;         /* <-- horizontal layout */
      gap: 36px;                   /* spacing between icons */
      justify-content: center;
      flex-wrap: wrap;             /* wrap on small screens */
    }

    a {
      color: white;
      text-decoration: none;
    }

    img.social-icon {
      width: 70px;
      height: 70px;
      transition: transform 0.3s, filter 0.3s;
      filter: drop-shadow(0 0 6px rgba(0, 0, 0, 0.6));
      border-radius: 50%;
      background-color: white;
      padding: 10px;
    }

    img.social-icon:active,
    img.social-icon:hover {
      transform: scale(1.2);
      filter: brightness(1.1) drop-shadow(0 0 10px white);
      background-color: #e0e0e0;
    }

    /* Snowflake styling */
    .snowflake {
      position: absolute;
      top: -10px;
      background: white;
      border-radius: 50%;
      opacity: 0.7;
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
        padding: 24px 18px;
        border-radius: 18px;
      }

      h1 {
        font-size: 1.4rem;
        margin-bottom: 24px;
      }

      img.social-icon {
        width: 58px;
        height: 58px;
        padding: 8px;
      }

      .icon-row {
        gap: 24px;
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
      
      const size = Math.random() * 10 + 6; // Between 6px and 16px
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
