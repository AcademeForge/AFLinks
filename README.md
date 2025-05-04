
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>AcademeForge Links</title>
  <style>
    body {
      margin: 0;
      background: linear-gradient(to bottom, #0f0f0f, #1a1a1a);
      font-family: 'Segoe UI', sans-serif;
      color: white;
      text-align: center;
      overflow-x: hidden;
    }

    header {
      padding: 20px 0;
      animation: fadeInDown 2s ease;
    }

    .logo {
      width: 100px;
      height: 100px;
      border-radius: 50%;
      margin: 0 auto 20px;
      box-shadow: 0 0 25px #00e5ff;
      animation: glow 2s infinite alternate;
    }

    h1 {
      margin: 0 auto 40px;
      font-size: 2.5rem;
      color: #ff4081;
    }

    .link-button {
      display: inline-block;
      margin: 15px;
      padding: 15px 30px;
      background: #292929;
      border: none;
      border-radius: 8px;
      color: white;
      font-size: 18px;
      text-decoration: none;
      transition: background 0.3s, transform 0.3s;
      box-shadow: 0 5px 15px rgba(0, 255, 255, 0.2);
      animation: floatIn 2s ease forwards;
    }

    .link-button:hover {
      background: #00e5ff;
      color: black;
      transform: scale(1.05);
    }

    .sky {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 150px;
      background: #111;
      z-index: 0;
      overflow: hidden;
    }

    .cloud {
      width: 200px;
      height: 60px;
      background: #ccc;
      border-radius: 100px;
      position: absolute;
      top: 40px;
      animation: moveClouds 10s linear infinite;
      opacity: 0.3;
    }

    .cloud::before,
    .cloud::after {
      content: '';
      position: absolute;
      background: #ccc;
      width: 100px;
      height: 100px;
      border-radius: 50%;
      top: -30px;
    }

    .cloud::before {
      left: 10px;
    }

    .cloud::after {
      right: 10px;
    }

    .lightning {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100vh;
      background: white;
      opacity: 0;
      z-index: 1;
      pointer-events: none;
    }

    @keyframes moveClouds {
      0% { left: -250px; }
      100% { left: 100%; }
    }

    @keyframes flash {
      0%, 100% { opacity: 0; }
      10% { opacity: 0.8; }
      20% { opacity: 0; }
    }

    @keyframes fadeInDown {
      0% { opacity: 0; transform: translateY(-50px); }
      100% { opacity: 1; transform: translateY(0); }
    }

    @keyframes floatIn {
      0% { transform: translateY(30px); opacity: 0; }
      100% { transform: translateY(0); opacity: 1; }
    }

    @keyframes glow {
      0% { box-shadow: 0 0 15px #00e5ff; }
      100% { box-shadow: 0 0 35px #00e5ff, 0 0 10px #00bcd4 inset; }
    }
  </style>
</head>
<body>

  <!-- Sky and clouds -->
  <div class="sky">
    <div class="cloud" style="left: 10%;"></div>
    <div class="cloud" style="left: 40%; animation-delay: 5s;"></div>
    <div class="cloud" style="left: 70%; animation-delay: 10s;"></div>
  </div>

  <!-- Lightning flash overlay -->
  <div class="lightning" id="lightning"></div>

  <!-- Logo + Heading -->
  <header>
    <a href="https://ibb.co/23qH49sJ"><img src="https://i.ibb.co/k2KvC79Z/IMG-20250320-164334-559.jpg" alt="IMG-20250320-164334-559" border="0" /></a> alt="AcademeForge Logo" class="logo"/>
    <h1>Follow AcademeForge</h1>
  </header>

  <!-- Link Buttons -->
  <a href="https://t.me/AcademeForge" class="link-button" target="_blank">Telegram</a>
  <a href="https://x.com/AcademeForge?t=Q4TXzMVYC9BZDXGEICxQ5w&s=09" class="link-button" target="_blank">Twitter</a>
  <a href="https://www.youtube.com/@AcademeForgePro" class="link-button" target="_blank">YouTube</a>
  <a href="https://www.instagram.com/academeforgee" class="link-button" target="_blank">Instagram</a>

  <!-- Audio Element -->
  <audio id="thunder-sound" src="https://www.soundjay.com/nature/thunder-1.mp3" preload="auto"></audio>

  <!-- Lightning & Thunder Script -->
  <script>
    const lightning = document.getElementById('lightning');
    const thunder = document.getElementById('thunder-sound');

    function triggerLightning() {
      lightning.style.animation = 'flash 1s ease';
      thunder.currentTime = 0;
      thunder.play();
      setTimeout(() => {
        lightning.style.animation = 'none';
      }, 1000);
    }

    setInterval(() => {
      triggerLightning();
    }, 1500); // Lightning happens every 1.5 seconds
  </script>

</body>
</html>