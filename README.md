<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For Megha</title>
    <style>
        body {
            margin: 0;
            font-family: 'Arial', sans-serif;
            background-color: #ffebee;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            overflow: hidden;
            text-align: center;
        }

        .container {
            background: rgba(255, 255, 255, 0.95);
            padding: 40px;
            border-radius: 25px;
            box-shadow: 0 15px 35px rgba(0,0,0,0.2);
            z-index: 10;
            max-width: 600px;
            width: 90%;
        }

        .heart-bg {
            position: absolute;
            font-size: 400px;
            color: rgba(255, 0, 0, 0.15);
            animation: vibrate 0.1s infinite;
            z-index: -1;
            user-select: none;
        }

        @keyframes vibrate {
            0% { transform: scale(1) translate(0,0); }
            25% { transform: scale(1.02) translate(3px, 3px); }
            50% { transform: scale(1) translate(-3px, -3px); }
            75% { transform: scale(1.02) translate(3px, -3px); }
            100% { transform: scale(1) translate(0,0); }
        }

        button {
            padding: 15px 35px;
            font-size: 20px;
            margin: 15px;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: transform 0.2s;
        }

        #btn-yes { background-color: #e91e63; color: white; font-weight: bold; }
        #btn-no { background-color: #757575; color: white; position: absolute; }

        .hidden { display: none; }

        .photo-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            margin-top: 20px;
        }

        .photo-grid img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: 15px;
            border: 3px solid #e91e63;
        }

        .mission-text {
            font-family: 'Courier New', Courier, monospace;
            background: #000;
            color: #ffeb3b;
            padding: 15px;
            font-size: 1.2em;
            margin: 20px 0;
        }
    </style>
</head>
<body>

    <div class="heart-bg">❤</div>

    <div id="page1" class="container">
        <h1>Hey Megha...</h1>
        <p style="font-size: 1.5em;">Will you want to reconcile?</p>
        <div style="height: 100px; position: relative;">
            <button id="btn-yes" onclick="startCelebration()">Yes</button>
            <button id="btn-no" onmouseover="teleportButton(this)">No</button>
        </div>
    </div>

    <div id="page2" class="container hidden">
        <h1 style="color: #e91e63;">HORRAYY!!!! 🎉</h1>
        <div class="photo-grid">
            <img src="photo1.jpg.jpeg" alt="Memory 1">
            <img src="photo2.jpg.jpeg" alt="Memory 2">
            <img src="photo3.jpg.jpeg" alt="Memory 3">
            <img src="photo4.jpg.jpeg" alt="Memory 4">
        </div>
        <audio id="reconcile-song" loop>
            <source src="your-song.mp3.mp3" type="audio/mpeg">
        </audio>
        <button id="btn-yes" onclick="showTerms()">Next</button>
    </div>

    <div id="page3" class="container hidden">
        <h2>Terms & Conditions</h2>
        <ul style="text-align: left; font-size: 1.1em; line-height: 1.8em;">
            <li>✨ No disrespect, only love.</li>
            <li>☕ Make coffee in the evening when I come home from the office.</li>
            <li>🤝 Always talk through the problems.</li>
        </ul>
        <div class="mission-text">
            YOUR MISSION, SHOULD YOU CHOOSE TO ACCEPT IT...
        </div>
        <button id="btn-yes" onclick="showContact()">I Accept</button>
        <button id="btn-no-retry" onclick="restart()">I Decline</button>
    </div>

    <div id="page4" class="container hidden">
        <h1>Mission Accepted! 🕵️‍♂️</h1>
        <p>I'm waiting for your call at:</p>
        <h1 style="color: #e91e63; font-size: 3em; letter-spacing: 2px;">8650320490</h1>
    </div>

    <script>
        function teleportButton(btn) {
            const x = Math.random() * (window.innerWidth - btn.clientWidth);
            const y = Math.random() * (window.innerHeight - btn.clientHeight);
            btn.style.left = x + 'px';
            btn.style.top = y + 'px';
        }

        function startCelebration() {
            document.getElementById('page1').classList.add('hidden');
            document.getElementById('page2').classList.remove('hidden');
            document.getElementById('reconcile-song').play();
        }

        function showTerms() {
            document.getElementById('page2').classList.add('hidden');
            document.getElementById('page3').classList.remove('hidden');
        }

        function showContact() {
            document.getElementById('page3').classList.add('hidden');
            document.getElementById('page4').classList.remove('hidden');
        }

        function restart() {
            alert("Self-destruct sequence initiated... just kidding. Let's try that again!");
            location.reload();
        }
    </script>
</body>
</html>
