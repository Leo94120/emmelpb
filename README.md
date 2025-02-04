<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Compte à Rebours</title>
    <style>
        body {
            text-align: center;
            font-family: Arial, sans-serif;
            margin-top: 50px;
            background: url('https://www.transparenttextures.com/patterns/hearts.png'), linear-gradient(135deg, #ff758c, #ff7eb3);
            color: white;
        }
        h1 {
            font-size: 36px;
            margin-bottom: 20px;
        }
        #countdown {
            font-size: 40px;
            font-weight: bold;
            background: rgba(0, 0, 0, 0.2);
            padding: 20px;
            border-radius: 10px;
            display: inline-block;
            margin-bottom: 20px;
        }
        #message {
            display: none;
            font-size: 28px;
            color: #ffeb3b;
            font-weight: bold;
        }
        #loveLetter {
            display: none;
            font-size: 24px;
            color: white;
            background: rgba(255, 0, 102, 0.8);
            padding: 20px;
            border-radius: 10px;
            margin-top: 20px;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }
    </style>
</head>
<body>
    <h1>Compte à Rebours</h1>
    <div id="countdown"></div>
    <div id="message">🎉 Le temps est écoulé ! 🎉</div>
    <div id="loveLetter">
        Chère Emma,
        <br><br>
        Enfin nous nous retrouvons. Cela fait longtemps que je ne t’ai pas vue. En réalité, cela fait juste 2 semaines, mais en 2 semaines, tu m’as énormément manqué. Cela me manque de ne plus te voir et de ne plus ressentir ta présence auprès de moi. Car, après tout, tu es celle qui fait ressortir mon bonheur, mon sourire, ma joie de vivre et mon plaisir d’aimer la vie.
        <br><br>
        Tu me fais prendre conscience que la vie est belle quand je suis à tes côtés, mais aussi qu’elle peut être triste quand je te quitte et que la distance reprend le dessus. Aujourd’hui, tu es là avec moi, car ta maman a accepté que nous nous retrouvions, et je garde dans mon cœur la confiance inestimable qu’elle a envers moi. J’en suis très reconnaissant, car je ne pensais pas m’intégrer aussi facilement. J’avais peur que je ne lui convienne pas, mais au final, tout s’est très bien passé, et je suis extrêmement heureux de t’avoir avec moi aujourd’hui.
        <br><br>
        Tu me fais vivre des moments inoubliables, et je te remercie pour ça. Je t’aime du plus profond de mon cœur, mon amour de ma vie. Profitons des heures si précieuses qui nous restent. ❤️❤️
    </div>
    <audio id="music" src="https://www.myinstants.com/media/sounds/lana-del-rey-ultraviolence.mp3" preload="auto"></audio>
    
    <script>
        const targetDate = new Date("February 19, 2025 12:05:00").getTime();
        const countdownEl = document.getElementById("countdown");
        const messageEl = document.getElementById("message");
        const loveLetterEl = document.getElementById("loveLetter");
        const music = document.getElementById("music");
        
        function updateCountdown() {
            const now = new Date().getTime();
            const timeLeft = targetDate - now;
            
            if (timeLeft > 0) {
                const days = Math.floor(timeLeft / (1000 * 60 * 60 * 24));
                const hours = Math.floor((timeLeft % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                const minutes = Math.floor((timeLeft % (1000 * 60 * 60)) / (1000 * 60));
                const seconds = Math.floor((timeLeft % (1000 * 60)) / 1000);
                
                countdownEl.textContent = `${days}j ${hours}h ${minutes}m ${seconds}s restants`;
            } else {
                countdownEl.style.display = "none";
                messageEl.style.display = "block";
                loveLetterEl.style.display = "block";
                music.play();
                clearInterval(interval);
            }
        }
        
        updateCountdown();
        let interval = setInterval(updateCountdown, 1000);
    </script>
</body>
</html>
