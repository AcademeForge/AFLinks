
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="google-site-verification" content="F1L0xfSoJ09Jp0SjvlmTnzkWK_fuYyhBw36QvRdDGwM">
    <title>AcademeForge</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            height: 100vh;
            background-color: #121212;
            font-family: Arial, sans-serif;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
        }
        
        .logo {
            width: 150px;
            margin-bottom: 20px;
        }

        .button-container {
            position: relative;
            text-align: center;
            z-index: 2;
        }

        .access-button {
            background-color: #00e5ff;
            color: white;
            padding: 15px 30px;
            border: none;
            border-radius: 8px;
            font-size: 20px;
            cursor: pointer;
            margin: 10px;
            transition: background-color 0.3s ease;
            z-index: 10;
        }

        .access-button:hover {
            background-color: #ff4081;
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
            top: -20%;
            left: -100%;
            width: 100vw;
            height: 100%;
            background: url('https://cdn.pixabay.com/photo/2017/08/30/01/57/clouds-2695564_960_720.jpg') repeat-x;
            animation: cloudAnimation 10s linear infinite;
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
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            animation: danceAnimation 2s infinite;
        }

        @keyframes danceAnimation {
            0%, 100% {
                transform: translateX(-50%) rotate(0deg);
            }
            50% {
                transform: translateX(-50%) rotate(15deg);
            }
        }

        .banner-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background-color: #ffcc00;
            color: black;
            text-align: center;
            font-weight: bold;
            font-size: 20px;
            padding: 10px 0;
            z-index: 999;
        }

        .dancing-character img {
            width: 100px;
        }
    </style>
</head>
<body>

    <!-- Banner at the top -->
    <div class="banner-container">
        Stay Tuned For more updates <a href="https://t.me/AcademeForge" target="_blank" style="color: #ff4081; text-decoration: underline;">Join our Telegram group</a>
    </div>

    <!-- Lightning animation -->
    <div class="lightning"></div>

    <!-- Clouds moving fast -->
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

</body>
</html>