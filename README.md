
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AcademeForge</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            height: 100vh;
            background-color: #0e0e0e;
            font-family: 'Arial', sans-serif;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            color: #fff;
        }
        
        .logo {
            width: 200px;
            margin-bottom: 20px;
            animation: fadeIn 2s ease-in-out;
        }

        .button-container {
            z-index: 2;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 10px;
            margin-top: 50px;
        }

        .access-button {
            background-color: #00e5ff;
            color: white;
            padding: 15px 30px;
            border: none;
            border-radius: 10px;
            font-size: 18px;
            font-weight: bold;
            cursor: pointer;
            transition: background-color 0.3s ease, transform 0.3s ease;
        }

        .access-button:hover {
            background-color: #ff4081;
            transform: scale(1.1);
        }

        /* Lightning Animation */
        .lightning {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: linear-gradient(transparent, transparent 50%, #fff 50%, transparent);
            background-size: 100% 20px;
            animation: lightningAnimation 1.5s infinite;
            z-index: 5;
            pointer-events: none;
        }

        @keyframes lightningAnimation {
            0%, 100% {
                background-position: 0 0;
            }
            50% {
                background-position: 0 100%;
            }
        }

        /* Cloud Animation */
        .clouds {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('https://cdn.pixabay.com/photo/2017/08/30/01/57/clouds-2695564_960_720.jpg') repeat-x;
            animation: cloudAnimation 15s linear infinite;
            z-index: 2;
        }

        @keyframes cloudAnimation {
            0% {
                left: -100%;
            }
            100% {
                left: 100%;
            }
        }

        /* Dancing Character */
        .dancing-character {
            position: absolute;
            bottom: 10px;
            width: 120px;
            animation: danceAnimation 2s ease-in-out infinite;
        }

        @keyframes danceAnimation {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-20px);
            }
        }

        /* Top Banner */
        .banner-container {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            background-color: #ffcc00;
            color: black;
            text-align: center;
            font-weight: bold;
            font-size: 18px;
            padding: 10px 0;
            z-index: 999;
        }

    </style>
</head>
<body>

    <!-- Banner at the top -->
    <div class="banner-container">
        Stay Tuned For more updates. <a href="https://t.me/AcademeForge" target="_blank" style="color: #ff4081; text-decoration: underline;">Join our Telegram group</a>
    </div>

    <!-- Lightning Animation -->
    <div class="lightning"></div>

    <!-- Clouds Moving -->
    <div class="clouds"></div>

    <!-- AcademeForge Logo -->
    <img class="logo" src="https://ibb.co/23qH49sJ" alt="AcademeForge Logo">

    <!-- Button Section -->
    <div class="button-container">
        <a href="https://t.me/AcademeForge" target="_blank"><button class="access-button">Join Telegram</button></a>
        <a href="https://x.com/AcademeForge?t=Q4TXzMVYC9BZDXGEICxQ5w&s=09" target="_blank"><button class="access-button">Follow on X</button></a>
        <a href="https://www.youtube.com/@AcademeForgePro" target="_blank"><button class="access-button">Subscribe on YouTube</button></a>
        <a href="https://www.instagram.com/academeforgee" target="_blank"><button class="access-button">Follow on Instagram</button></a>
    </div>

    <!-- Dancing Cartoon Character -->
    <div class="dancing-character">
        <img src="https://i.ibb.co/k2KvC79Z/IMG-20250320-164334-559.jpg" alt="Dancing Character">
    </div>

    <!-- Audio for Lightning Sound -->
    <audio id="lightning-sound" src="https://www.soundjay.com/button/beep-07.wav"></audio>

    <script>
        const lightningSound = document.getElementById('lightning-sound');

        // Play the lightning sound every time the lightning animation is triggered
        setInterval(() => {
            lightningSound.play();
        }, 1500); // Play sound every 1.5 seconds (matching the lightning animation)
    </script>

</body>
</html>