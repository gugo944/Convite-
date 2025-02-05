<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Carta de Amor</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f9f9f9;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
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

        #letter button {
            margin-top: 15px;
            padding: 10px 20px;
            font-size: 16px;
            color: #fff;
            background-color: #f9c5c8;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
    </style>
</head>
<body>

    <div id="envelope" onclick="openLetter()">
        Clique para abrir a mensagem
    </div>

    <div id="letter">
        <p>Oi [Camila Kalatay],</p>
        <p>Você quer ir na pizzaria na sexta?</p>
        <button onclick="closeLetter()">Fechar</button>
    </div>

    <script>
        function openLetter() {
            document.getElementById('envelope').style.display = 'none';
            document.getElementById('letter').style.display = 'block';
        }

        function closeLetter() {
            document.getElementById('letter').style.display = 'none';
            document.getElementById('envelope').style.display = 'flex';
        }
    </script>

</body>
</html>-
