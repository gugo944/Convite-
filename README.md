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

        #envelope {
            position: relative;
            width: 280px;
            height: 180px;
            background-color: #f9c5c8;
            border-bottom-left-radius: 6px;
            border-bottom-right-radius: 6px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
            cursor: pointer;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 20px;
            color: #fff;
            text-align: center;
        }

        #letter {
            display: none;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 250px;
            padding: 20px;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
            text-align: center;
        }

        #letter p {
            margin: 0;
            font-size: 18px;
            color: #333;
        }

        #options {
            margin-top: 15px;
        }

        #options button {
            padding: 10px 20px;
            font-size: 16px;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin: 0 10px;
        }

        #accept {
            background-color: #4CAF50;
        }

        #decline {
            background-color: #f44336;
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

    <div id="envelope" onclick="openLetter()">
        Clique para abrir a mensagem
    </div>

    <div id="letter">
        <p>Oi Camila Kalatay,</p>
        <p>Você quer ir na seta para a pizzaria?</p>
        <div id="options">
            <button id="accept" onclick="acceptInvitation()">Aceitar</button>
            <button id="decline" onmouseover="moveDeclineButton()">Recusar</button>
        </div>
    </div>

    <div id="fireworks" class="fireworks"></div>

    <script>
        function openLetter() {
            document.getElementById('envelope').style.display = 'none';
            document.getElementById('letter').style.display = 'block';
        }

        function moveDeclineButton() {
            const declineButton = document.getElementById('decline');
            const randomX = Math.random() * (window.innerWidth - declineButton.offsetWidth);
            const randomY = Math.random() * (window.innerHeight - declineButton.offsetHeight);
            declineButton.style.position = 'absolute';
            declineButton.style.left = `${randomX}px`;
            declineButton.style.top = `${randomY}px`;
        }

        function acceptInvitation() {
            document.getElementById('letter').style.display = 'none';
            for (let i = 0; i < 100; i++) {
                createFirework();
            }
        }

        function createFirework() {
            const firework = document.createElement('div');
            firework.classList.add('firework');
            firework.style.left = `${Math.random() * 100}%`;
            firework.style.top = `${Math.random() * 100}%`;
            document.getElementById('fireworks').appendChild(firework);
            setTimeout(() => {
                firework.remove();
            }, 1000);
        }
    </script>

</body>
</html>{
                firework.remove();
            }, 1000);
        }
    </script>

</body>
</html>
