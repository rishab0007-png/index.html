<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Connect with Me</title>
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  height: 100vh;
  background: linear-gradient(135deg, #0c0c0c 0%, #1a1a2e 50%, #16213e 100%);
  overflow: hidden;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}

body::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: 
    radial-gradient(circle at 20% 80%, rgba(120, 119, 198, 0.3) 0%, transparent 50%),
    radial-gradient(circle at 80% 20%, rgba(255, 119, 198, 0.3) 0%, transparent 50%),
    radial-gradient(circle at 40% 40%, rgba(120, 219, 255, 0.2) 0%, transparent 50%);
  animation: aurora 8s ease-in-out infinite alternate;
  z-index: 1;
}

@keyframes aurora {
  0% { opacity: 0.6; transform: scale(1); }
  100% { opacity: 1; transform: scale(1.05); }
}

.container {
  background: rgba(15, 15, 25, 0.85);
  backdrop-filter: blur(20px);
  padding: 50px 30px;
  border-radius: 30px;
  text-align: center;
  box-shadow: 
    0 25px 50px rgba(0, 0, 0, 0.5),
    0 0 100px rgba(120, 119, 198, 0.2),
    inset 0 1px 0 rgba(255, 255, 255, 0.1);
  position: relative;
  z-index: 10;
  max-width: 500px;
  width: 95vw;
  border: 1px solid rgba(255, 255, 255, 0.1);
}

h1 {
  color: #ffffff;
  font-size: 2.2rem;
  font-weight: 600;
  margin-bottom: 40px;
  letter-spacing: 2px;
  text-shadow: 0 0 30px rgba(255, 255, 255, 0.5);
  position: relative;
}

h1::after {
  content: '';
  position: absolute;
  bottom: -10px;
  left: 50%;
  transform: translateX(-50%);
  width: 60px;
  height: 3px;
  background: linear-gradient(90deg, #78f7f7, #4facfe);
  border-radius: 2px;
  box-shadow: 0 0 20px #78f7f7;
}

.icon-container {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 50px;
  flex-wrap: wrap;
  margin-top: 20px;
  min-height: 120px;
}

.social-link {
  position: relative;
  cursor: pointer;
}

img.social-icon {
  width: 90px;
  height: 90px;
  border-radius: 25px;
  transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
  filter: drop-shadow(0 10px 30px rgba(0, 0, 0, 0.5));
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  border: 2px solid rgba(255, 255, 255, 0.2);
  pointer-events: none;
}

.social-link.whatsapp img.social-icon {
  filter: drop-shadow(0 0 25px #25D366);
  box-shadow: 0 15px 40px rgba(37, 211, 102, 0.4);
}

.social-link.instagram img.social-icon {
  filter: drop-shadow(0 0 25px #E4405F);
  box-shadow: 0 15px 40px rgba(228, 64, 95, 0.4);
}

.social-link.telegram img.social-icon {
  filter: drop-shadow(0 0 25px #0088CC);
  box-shadow: 0 15px 40px rgba(0, 136, 204, 0.4);
}

/* Cinematic Drop Animation */
.social-link {
  opacity: 0;
  transform: translateY(-200px) scale(0.3) rotateY(180deg);
}

.social-link.drop1 { animation: cinematicDrop 1.8s 0.3s forwards cubic-bezier(0.25, 0.46, 0.45, 0.94); }
.social-link.drop2 { animation: cinematicDrop 1.8s 0.6s forwards cubic-bezier(0.25, 0.46, 0.45, 0.94); }
.social-link.drop3 { animation: cinematicDrop 1.8s 0.9s forwards cubic-bezier(0.25, 0.46, 0.45, 0.94); }

@keyframes cinematicDrop {
  0% {
    opacity: 0;
    transform: translateY(-200px) scale(0.3) rotateY(180deg);
  }
  30% {
    opacity: 1;
    transform: translateY(30px) scale(1.1) rotateY(10deg);
  }
  60% {
    transform: translateY(-10px) scale(0.95) rotateY(-5deg);
  }
  80% {
    transform: translateY(5px) scale(1.02);
  }
  100% {
    opacity: 1;
    transform: translateY(0) scale(1) rotateY(0deg);
  }
}

/* Hover Effects */
.social-link:hover img.social-icon {
  transform: scale(1.15) translateY(-8px) rotate(5deg);
  box-shadow: 0 25px 60px rgba(0, 0, 0, 0.7), 0 0 50px currentColor;
}

.social-link:active img.social-icon {
  transform: scale(1.05) translateY(-4px);
}

/* Enhanced Snow */
.snowflake {
  position: absolute;
  background: linear-gradient(45deg, #ffffff, #f0f8ff);
  border-radius: 50%;
  opacity: 0.8;
  animation: snowfall linear infinite;
  z-index: 2;
  filter: blur(0.5px);
  box-shadow: 0 0 8px rgba(255, 255, 255, 0.8);
}

@keyframes snowfall {
  0% { transform: translateY(-10px) rotate(0deg); opacity: 0.8; }
  100% { 
    transform: translateY(100vh) rotate(360deg); 
    opacity: 0; 
  }
}

@media (max-width: 480px) {
  .container {
    padding: 40px 25px;
    margin: 20px;
    border-radius: 25px;
  }
  
  h1 {
    font-size: 1.9rem;
    margin-bottom: 35px;
  }
  
  img.social-icon {
    width: 80px;
    height: 80px;
  }
  
  .icon-container {
    gap: 40px;
  }
}
</style>
</head>
<body>
<!-- Enhanced Snow Effect -->
<div id="snow-container"></div>

<div class="container">
  <h1>Connect with Me</h1>
  <div class="icon-container">
    <a href="https://wa.me/919897978494" target="_blank" rel="noopener noreferrer" class="social-link drop1 whatsapp" aria-label="WhatsApp">
      <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" alt="WhatsApp" class="social-icon" loading="lazy" />
    </a>
    
    <a href="https://www.instagram.com/rishab_gautam__007" target="_blank" rel="noopener noreferrer" class="social-link drop2 instagram" aria-label="Instagram">
      <img src="https://upload.wikimedia.org/wikipedia/commons/e/e7/Instagram_logo_2016.svg" alt="Instagram" class="social-icon" loading="lazy" />
    </a>
    
    <a href="https://t.me/+919897978494" target="_blank" rel="noopener noreferrer" class="social-link drop3 telegram" aria-label="Telegram">
      <img src="https://upload.wikimedia.org/wikipedia/commons/8/82/Telegram_logo.svg" alt="Telegram" class="social-icon" loading="lazy" />
    </a>
  </div>
</div>

<script>
// Enhanced Cinematic Snow
function createSnowflakes() {
  const snowContainer = document.getElementById('snow-container');
  const snowflakeCount = 120;
  
  for (let i = 0; i < snowflakeCount; i++) {
    const snowflake = document.createElement('div');
    snowflake.className = 'snowflake';
    
    const size = Math.random() * 8 + 4;
    const speed = Math.random() * 4 + 2;
    const left = Math.random() * 100;
    
    snowflake.style.width = size + 'px';
    snowflake.style.height = size + 'px';
    snowflake.style.left = left + '%';
    snowflake.style.animationDuration = speed + 's';
    snowflake.style.animationDelay = Math.random() * 5 + 's';
    
    snowContainer.appendChild(snowflake);
    
    // Respawn snowflakes
    setTimeout(() => {
      snowflake.style.animation = 'none';
      snowflake.offsetHeight; // Trigger reflow
      snowflake.style.animation = `snowfall ${speed}s linear infinite`;
    }, speed * 1000);
  }
}

// Initialize cinematic effects
document.addEventListener('DOMContentLoaded', () => {
  createSnowflakes();
  
  // Add pulse effect to title
  const title = document.querySelector('h1');
  setInterval(() => {
    title.style.textShadow = 
      '0 0 30px rgba(255, 255, 255, 0.8), 0 0 60px #78f7f7, 0 0 90px #4facfe';
  }, 3000);
});
</script>
</body>
</html>
