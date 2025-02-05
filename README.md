<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Convite</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f9f9f9;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            overflow: hidden;
            position: relative;
        }

        #message {
            text-align: center;
            background-color: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
        }

        #message h1 {
            font-size: 24px;
            color: #333;
        }

        #options {
            margin-top: 20px;
        }

        #options button {
            padding: 10px 20px;
            font-size: 16px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin: 0 10px;
        }

        #accept {
            background-color: #4CAF50;
            color: white;
        }

        #decline {
            background-color: #f44336;
            color: white;
        }

        .fireworks {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            pointer-events: none;
        }

        .firework {
            position: absolute;
            width: 10px;
            height: 10px;
            background-color: #ff0;
            border-radius: 50%;
            animation: explode 1s ease-out;
        }

        @keyframes explode {
            0% {
                transform: scale(1);
                opacity: 1;
            }
            100% {
                transform: scale(10);
                opacity: 0;
            }
        }
    </style>
</head>
<body>

    <div id="message">
        <h1>Você aceita o convite?</h1>
        <div id="options">
            <button id="accept">Aceitar</button>
            <button id="decline">Recusar</button>
        </div>
    </div>

    <div id="fireworks" class="fireworks"></div>

    <script>
        const acceptButton = document.getElementById('accept');
        const declineButton = document.getElementById('decline');
        const fireworksContainer = document.getElementById('fireworks');

        declineButton.addEventListener('mouseover', () => {
            const randomX = Math.random() * (window.innerWidth - declineButton.offsetWidth);
            const randomY = Math.random() * (window.innerHeight - declineButton.offsetHeight);
            declineButton.style.position = 'absolute';
            declineButton.style.left = `${randomX}px`;
            declineButton.style.top = `${randomY}px`;
        });

        acceptButton.addEventListener('click', () => {
            document.getElementById('message').style.display = 'none';
            for (let i = 0; i < 100; i++) {
                createFirework();
            }
        });

        function createFirework() {
            const firework = document.createElement('div');
            firework.classList.add('firework');
            firework.style.left = `${Math.random() * 100}%`;
            firework.style.top = `${Math.random() * 100}%`;
            fireworksContainer.appendChild(firework);
            setTimeout(() => {
                firework.remove();
            }, 1000);
        }
    </script>

</body>
</html>
