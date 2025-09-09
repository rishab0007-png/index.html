<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Connect with Me</title>
<style>
  @keyframes backgroundAnimation {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
  }

  body {
    margin: 0;
    height: 100vh;
    background: linear-gradient(-45deg, #555555, #777777, #555555, #777777);
    background-size: 400% 400%;
    animation: backgroundAnimation 20s ease infinite;
    display: flex;
    justify-content: center;
    align-items: center;
    font-family: Arial, sans-serif;
  }

  .container {
    background-color: rgba(40, 40, 40, 0.7);
    padding: 30px;
    border-radius: 20px;
    text-align: center;
    box-shadow: 0 0 15px rgba(0,0,0,0.5);
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
