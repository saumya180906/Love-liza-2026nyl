<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy New Year Liza ❤️</title>
    <style>
        /* --- CSS STYLES --- */
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@700&family=Poppins:wght@300;500&display=swap');

        body, html {
            margin: 0;
            padding: 0;
            height: 100%;
            overflow: hidden;
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #2b002b 0%, #660033 50%, #1a001a 100%);
            color: white;
            text-align: center;
        }

        /* The Overlay (Click to Start) */
        #start-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.95);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            cursor: pointer;
            transition: opacity 1s ease;
        }

        #start-overlay h1 {
            font-family: 'Dancing Script', cursive;
            font-size: 3rem;
            color: #ff4d6d;
            animation: pulse 1.5s infinite;
        }

        #start-overlay p {
            font-size: 1.2rem;
            color: #ccc;
            margin-top: 10px;
        }

        /* Main Content */
        .container {
            display: none; /* Hidden until clicked */
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            position: relative;
            z-index: 10;
        }

        h1.title {
            font-family: 'Dancing Script', cursive;
            font-size: 4rem;
            margin: 0;
            text-shadow: 0 0 10px #ff4d6d, 0 0 20px #ff4d6d;
            opacity: 0;
            animation: fadeIn 2s forwards 0.5s;
        }

        h2.subtitle {
            font-size: 1.5rem;
            letter-spacing: 3px;
            margin-bottom: 30px;
            opacity: 0;
            animation: fadeIn 2s forwards 1.5s;
        }

        /* Photo Frame */
        .photo-frame {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            border: 5px solid white;
            box-shadow: 0 0 30px #ff4d6d;
            overflow: hidden;
            opacity: 0;
            animation: popIn 1s forwards 1s;
            margin-bottom: 20px;
            background-color: #fff;
        }

        .photo-frame img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .message {
            max-width: 600px;
            padding: 20px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            backdrop-filter: blur(5px);
            opacity: 0;
            animation: slideUp 1.5s forwards 2s;
            margin: 0 20px;
        }

        /* Falling Hearts Animation */
        .heart {
            position: absolute;
            color: #ff4d6d;
            opacity: 0.7;
            top: -10vh;
            animation: fall linear forwards;
            z-index: 1;
        }

        /* Keyframes */
        @keyframes pulse { 0% { transform: scale(1); } 50% { transform: scale(1.1); } 100% { transform: scale(1); } }
        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
        @keyframes popIn { 0% { transform: scale(0); opacity: 0; } 80% { transform: scale(1.1); opacity: 1; } 100% { transform: scale(1); opacity: 1; } }
        @keyframes slideUp { from { transform: translateY(50px); opacity: 0; } to { transform: translateY(0); opacity: 1; } }
        @keyframes fall { to { transform: translateY(110vh); } }

    </style>
</head>
<body>

    <div id="start-overlay">
        <h1>For My Love, Liza</h1>
        <p>(Tap anywhere to open)</p>
    </div>

    <div class="container" id="main-content">
        <h1 class="title">Happy New Year 2026</h1>
        <h2 class="subtitle">I LOVE YOU LIZA</h2>

        <div class="photo-frame">
            <img src="https://via.placeholder.com/200x200/ffb6c1/ffffff?text=Liza" alt="Liza"> 
        </div>

        <div class="message">
            <p>
                My Dearest Liza,<br><br>
                As the world steps into 2026, I am stepping into another year of loving you. 
                You are my favorite part of every day. Here is to more laughter, more memories, 
                and more love in the year ahead.<br><br>
                Forever yours. ❤️
            </p>
        </div>
    </div>

    <audio id="bg-music" loop>
        <source src="song.mp3" type="audio/mpeg">
        Your browser does not support the audio element.
    </audio>

    <script>
        /* --- JAVASCRIPT LOGIC --- */
        const overlay = document.getElementById('start-overlay');
        const content = document.getElementById('main-content');
        const audio = document.getElementById('bg-music');

        // Interaction to start music and animations
        overlay.addEventListener('click', () => {
            overlay.style.opacity = '0';
            setTimeout(() => {
                overlay.style.display = 'none';
                content.style.display = 'flex';
                
                // Try to play audio
                audio.play().catch(error => {
                    console.log("Audio playback failed (usually due to browser policy without interaction): ", error);
                });

                startHearts();
            }, 1000);
        });

        // Function to generate falling hearts
        function startHearts() {
            setInterval(() => {
                const heart = document.createElement('div');
                heart.classList.add('heart');
                heart.innerHTML = '❤️';
                heart.style.left = Math.random() * 100 + "vw";
                heart.style.fontSize = Math.random() * 20 + 10 + "px";
                heart.style.animationDuration = Math.random() * 3 + 2 + "s";
                
                document.body.appendChild(heart);

                // Remove heart after animation to keep memory low
                setTimeout(() => {
                    heart.remove();
                }, 5000);
            }, 300);
        }
    </script>
