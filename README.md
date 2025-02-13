
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contador de Tiempo</title>
    <style>
        body {
            background: linear-gradient(to right, rgb(251, 193, 233) , #bb51d0);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            font-family: 'Arial', sans-serif;
        }

        .container {
            text-align: center;
            background-color: white;
            padding: 20px 40px;
            border-radius: 15px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
            max-width: 100%;
            width: auto;
            min-width: 300px;
        }

        .title {
            font-size: 1.8em;
            font-weight: bold;
            color: #333;
            margin-bottom: 20px;
        }

        .timer {
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 2em;
            font-weight: bold;
            color: #c42c39;
        }

        .time-segment {
            display: flex;
            flex-direction: column;
            align-items: center;
            margin: 0 10px;
        }

        .time-value {
            font-size: 3em;
        }

        .time-label {
            font-size: 0.8em;
        }

        .separator {
            font-size: 3em;
            margin: 0 5px;
        }

        .btn {
            margin-top: 20px;
            padding: 10px 20px;
            font-size: 1em;
            color: rgb(0, 0, 0);
            background-color: #f0a0ae;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .btn:hover {
            background-color: #be4ec4;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="title">
            Empezamos el 6/09/2024 y llevamos...
        </div>
        <div class="timer" id="timer">
            <!-- El contador de tiempo aparecerá aquí -->
        </div>
        <button class="btn" onclick="location.href='opciones.html'">Dale aqui (o mejor no, q roche)</button>
    </div>
    
    <script>
        const startDate = new Date("2024-09-06T20:49:00Z");

        function updateTimer() {
            const now = new Date();
            const elapsedTime = now - startDate;

            const days = Math.floor(elapsedTime / (1000 * 60 * 60 * 24));
            const hours = Math.floor((elapsedTime % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((elapsedTime % (1000 * 60 * 60)) / (1000 * 60));
            const seconds = Math.floor((elapsedTime % (1000 * 60)) / 1000);

            document.getElementById("timer").innerHTML = `
                <div class="time-segment">
                    <div class="time-value">${days}</div>
                    <div class="time-label">días</div>
                </div>
                <div class="separator">:</div>
                <div class="time-segment">
                    <div class="time-value">${hours}</div>
                    <div class="time-label">horas</div>
                </div>
                <div class="separator">:</div>
                <div class="time-segment">
                    <div class="time-value">${minutes}</div>
                    <div class="time-label">minutos</div>
                </div>
                <div class="separator">:</div>
                <div class="time-segment">
                    <div class="time-value">${seconds}</div>
                    <div class="time-label">segundos</div>
                </div>
            `;
        }

        setInterval(updateTimer, 1000);
        updateTimer();
    </script>
</body>
</html>
