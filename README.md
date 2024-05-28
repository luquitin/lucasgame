<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Medidor de Belleza</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            background-image: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" width="30" height="30" viewBox="0 0 24 24"><text y="20" font-size="24">❤️</text></svg>');
            background-repeat: repeat;
            padding: 20px;
            text-align: center;
        }
        h1, h2 {
            color: #333;
        }
        h2 {
            font-size: 32px;
            margin-bottom: 20px;
        }
        #nombre-input {
            margin-bottom: 10px;
            padding: 10px;
            font-size: 18px;
            width: 60%;
        }
        #puntuar-btn {
            margin-bottom: 20px;
            padding: 10px 20px;
            font-size: 18px;
            cursor: pointer;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 5px;
        }
        #puntuar-btn:hover {
            background-color: #45a049;
        }
        .resultado {
            margin-top: 10px;
            padding: 10px;
            border: 1px solid #ccc;
            background-color: #fff;
            display: inline-block;
            width: 80%;
            font-size: 18px;
        }
        .asco {
            color: red;
        }
        .excelente {
            color: green;
        }
        #medidor {
            margin-top: 20px;
            font-size: 24px;
            color: #555;
        }
    </style>
</head>
<body>
    <h2>Creado por Lucas García</h2>
    <h1>Medidor de Belleza</h1>
    <input type="text" id="nombre-input" placeholder="Ingresa un nombre">
    <button id="puntuar-btn">Puntuar</button>
    <div id="resultados"></div>
    <div id="medidor">Medidor de Belleza</div>

    <script>
        document.getElementById('puntuar-btn').addEventListener('click', function() {
            const nombre = document.getElementById('nombre-input').value;
            const resultadosDiv = document.getElementById('resultados');
            const medidorDiv = document.getElementById('medidor');

            let puntuacion;
            let mensaje;

            if (nombre.toLowerCase() === 'aaron') {
                puntuacion = 0;
                mensaje = `${nombre}: ${puntuacion} 😖`;
            } else if (nombre.toLowerCase() === 'juan carlos') {
                puntuacion = 100;
                mensaje = `${nombre}: ${puntuacion} 💯`;
            } else {
                puntuacion = Math.floor(Math.random() * 99) + 1;
                mensaje = `${nombre}: ${puntuacion}`;
            }

            const resultadoDiv = document.createElement('div');
            resultadoDiv.classList.add('resultado');
            if (nombre.toLowerCase() === 'aaron') {
                resultadoDiv.classList.add('asco');
            } else if (nombre.toLowerCase() === 'juan carlos') {
                resultadoDiv.classList.add('excelente');
            }
            resultadoDiv.textContent = mensaje;

            resultadosDiv.appendChild(resultadoDiv);

            medidorDiv.textContent = `Medidor de Belleza: ${puntuacion}`;
        });
    </script>
</body>
</html>
