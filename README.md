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
      animation: moveClouds 5s linear infinite;
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
  </style>
</head>
<body>

  <!-- Sky and clouds -->
  <div class="sky">
    <div class="cloud" style="left: 10%;"></div>
    <div class="cloud" style="left: 30%; animation-delay: 1s;"></div>
    <div class="cloud" style="left: 60%; animation-delay: 2s;"></div>
  </div>

  <!-- Lightning flash overlay -->
  <div class="lightning" id="lightning"></div>

  <!-- Heading -->
  <header>
    <h1>Follow AcademeForge</h1>
  </header>

  <!-- Link Buttons -->
  <a href="https://t.me/AcademeForge" class="link-button" target="_blank">Telegram</a>
  <a href="https://x.com/AcademeForge?t=Q4TXzMVYC9BZDXGEICxQ5w&s=09" class="link-button" target="_blank">Twitter</a>
  <a href="https://www.youtube.com/@AcademeForgePro" class="link-button" target="_blank">YouTube</a>
  <a href="https://www.instagram.com/academeforgee" class="link-button" target="_blank">Instagram</a>
<a href="https://academeforge.github.io/AcademeForge/" class="link-button" target="_blank">Official Website</a>
<a href="http://academeforge.wordpress.com/" class="link-button" target="_blank">About AST</a>


  <!-- Thunder Sound -->
  <audio id="thunder-sound" src="thunder.mp3" preload="auto"></audio>

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

    setInterval(triggerLightning, 1500);
  </script>

</body>
</html>