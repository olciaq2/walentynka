<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <title>Czy zostaniesz moją walentynką?</title>
    <style>
        body {
            background-color: #ffe6f2;
            font-family: 'Cursive', sans-serif;
            text-align: center;
            padding-top: 100px;
            color: #ff4d88;
            overflow: hidden;
        }

        h1 {
            font-size: 48px;
            margin-bottom: 40px;
        }

        button {
            font-size: 20px;
            padding: 10px 30px;
            margin: 10px;
            border: none;
            border-radius: 20px;
            cursor: pointer;
            transition: transform 0.2s, background-color 0.3s;
        }

        #yesButton {
            background-color: #ff66b2;
            color: white;
        }

        #noButton {
            background-color: #ffb3d9;
            color: white;
        }

        button:hover {
            transform: scale(1.1);
        }

        #message {
            margin-top: 30px;
            font-size: 24px;
            color: #ff3385;
        }

        .heart {
            position: fixed;
            top: -10px;
            font-size: 24px;
            color: #ff3366;
            animation: fall linear infinite;
            opacity: 0.8;
        }

        @keyframes fall {
            0% {
                transform: translateY(-10px) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(100vh) rotate(360deg);
                opacity: 0;
            }
        }
    </style>
</head>
<body>

    <h1>zostaniesz moją walentynką? 💖</h1>

    <button id="yesButton" onclick="answerYes()">Tak! 🥰</button>
    <button id="noButton" onclick="answerNo()">Nie 😢</button>

    <p id="message"></p>

    <script>
        function answerYes() {
            document.getElementById("message").innerHTML = "Wiedziałam!!!😚🫶 już nigdy się mnie nie pozbędziesz😈";
        }

        function answerNo() {
            const messages = [
                "Na pewno? 🤔",
                "Jesteś tego pewna? 😳",
                "Jeszcze możesz zmienić swoją decyzję 😌",
                "Albo pomyliłaś przyciski, albo naprawdę nie chcesz... 😔"
            ];

            let index = 0;

            function showNextMessage() {
                if (index < messages.length) {
                    document.getElementById("message").innerHTML = messages[index];
                    index++;
                    setTimeout(showNextMessage, 2000);  // Wyświetlanie co 2 sekundy
                }
            }

            showNextMessage();
        }

        // Funkcja tworząca spadające serduszka
        function createHeart() {
            const heart = document.createElement("div");
            heart.classList.add("heart");
            heart.innerText = "❤️";

            heart.style.left = Math.random() * 100 + "vw";
            heart.style.animationDuration = Math.random() * 2 + 3 + "s";

            document.body.appendChild(heart);

            setTimeout(() => {
                heart.remove();
            }, 5000);
        }

        setInterval(createHeart, 300);
    </script>

</body>
</html>
