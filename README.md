
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>AcademeForge Links</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(to bottom right, #e0f7fa, #fce4ec);
      color: #222;
      display: flex;
      flex-direction: column;
      align-items: center;
      min-height: 100vh;
      overflow-x: hidden;
    }
    header {
      margin-top: 60px;
      font-size: 2.5rem;
      font-weight: bold;
      color: #4b0082;
      text-align: center;
      animation: fadeDown 1s ease-out;
    }
    .tagline {
      margin-top: 10px;
      font-size: 1.2rem;
      color: #555;
      text-align: center;
      animation: fadeUp 1.2s ease-out;
    }
    .link-container {
      margin-top: 40px;
      width: 90%;
      max-width: 500px;
      display: flex;
      flex-direction: column;
      gap: 15px;
      animation: slideIn 1.3s ease-out;
    }
    a.button {
      text-align: center;
      padding: 14px 20px;
      background: linear-gradient(135deg, #6a5acd, #00bfff);
      color: white;
      text-decoration: none;
      border-radius: 10px;
      font-size: 1.1rem;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
      animation: pulse 2s infinite;
    }
    a.button:hover {
      transform: scale(1.05);
      box-shadow: 0 6px 16px rgba(0, 0, 0, 0.3);
    }
    footer {
      margin-top: auto;
      padding: 20px;
      font-size: 0.9rem;
      color: #888;
      text-align: center;
      animation: fadeIn 1.5s ease-in;
    }.floating-object {
  position: absolute;
  animation: float 6s ease-in-out infinite;
}

.floating-object img {
  width: 60px;
}

.book {
  top: 10%;
  left: 15%;
  animation-delay: 0s;
}
.pencil {
  top: 20%;
  left: 40%;
  animation-delay: 2s;
}
.eraser {
  top: 30%;
  left: 70%;
  animation-delay: 4s;
}
.sharpener {
  top: 50%;
  left: 50%;
  animation-delay: 6s;
}

@keyframes fadeDown {
  0% { opacity: 0; transform: translateY(-20px); }
  100% { opacity: 1; transform: translateY(0); }
}

@keyframes fadeUp {
  0% { opacity: 0; transform: translateY(20px); }
  100% { opacity: 1; transform: translateY(0); }
}

@keyframes slideIn {
  0% { opacity: 0; transform: translateX(-100px); }
  100% { opacity: 1; transform: translateX(0); }
}

@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

@keyframes pulse {
  0% { transform: scale(1); }
  50% { transform: scale(1.03); }
  100% { transform: scale(1); }
}

@keyframes float {
  0% { transform: translateY(0); }
  50% { transform: translateY(-30px); }
  100% { transform: translateY(0); }
}

  </style>
</head>
<body>
  <audio autoplay loop hidden>
    <source src="https://www.bensound.com/bensound-music/bensound-ukulele.mp3" type="audio/mpeg">
    Your browser does not support the audio element.
  </audio>  <header>AcademeForge</header>
  <div class="tagline">Empowering Students, Building Futures</div>
  <div class="link-container">
    <a class="button" href="http://academeforge.wordpress.com" target="_blank">WordPress Blog</a>
    <a class="button" href="https://www.youtube.com/@AcademeForgePro" target="_blank">YouTube Channel</a>
    <a class="button" href="https://www.instagram.com/academeforgee" target="_blank">Instagram</a>
    <a class="button" href="https://x.com/AcademeForge?t=Q4TXzMVYC9BZDXGEICxQ5w&s=09" target="_blank">Twitter (X)</a>
    <a class="button" href="https://t.me/addlist/CVX57k_dpG4wNGJl" target="_blank">All Telegram Groups/Channels</a>
    <a class="button" href="https://t.me/+DYChuLLgL-83MThl" target="_blank">Main Telegram Chat Group</a>
    <a class="button" href="https://academeforge.github.io/AcademeForge/" target="_blank">Notes Website</a>
    <a class="button" href="https://academeforge.github.io/TimeTable/" target="_blank">Time Tables Website</a>
    <a class="button" href="https://academeforge.github.io/AST/" target="_blank">AST Registration Form</a>
    <a class="button" href="https://academeforge.pages.dev/" target="_blank">Extra Study Material</a>
  </div>
  <footer>
    Made with love by AcademeForge Team
  </footer>
  <div class="floating-object book">
    <img src="https://cdn-icons-png.flaticon.com/512/149/149660.png" alt="Book">
  </div>
  <div class="floating-object pencil">
    <img src="https://cdn-icons-png.flaticon.com/512/2956/2956975.png" alt="Pencil">
  </div>
  <div class="floating-object eraser">
    <img src="https://cdn-icons-png.flaticon.com/512/3082/3082762.png" alt="Eraser">
  </div>
  <div class="floating-object sharpener">
    <img src="https://cdn-icons-png.flaticon.com/512/2099/2099131.png" alt="Sharpener">
  </div>
</body>
