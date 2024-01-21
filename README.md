# Calculadora-Enem-
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora de Desconto ENEM</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 50px;
            background-color: #ffdb58; /* Amarelo mais vivo */
            display: flex;
            flex-direction: column;
            align-items: center;
            position: relative;
        }
        input {
            margin: 10px;
            display: block;
        }
        button {
            margin-top: 10px;
        }
        #uninassauText {
            color: #001f3f; /* Azul marinho */
            font-size: 20px;
            margin-top: 50px;
            font-weight: bold; /* Negrito */
        }
        #shadow {
            position: absolute;
            top: 0;
            left: 50%;
            transform: translateX(-50%);
            background: linear-gradient(to bottom, transparent 0%, #ffdb58 50%, #ffdb58 100%);
            width: 100%;
            height: 50px; /* Ajuste conforme necessário */
            z-index: -1;
        }
    </style>
</head>
<body>
    <h2>Calculadora de Desconto ENEM - UNINASSAU Garanhuns</h2>
    
    <label for="matematica">Matemática:</label>
    <input type="number" id="matematica" placeholder="Digite a nota de Matemática" required>
    
    <label for="humanas">Humanas:</label>
    <input type="number" id="humanas" placeholder="Digite a nota de Humanas" required>
    
    <label for="natureza">Natureza:</label>
    <input type="number" id="natureza" placeholder="Digite a nota de Natureza" required>
    
    <label for="linguagens">Linguagens:</label>
    <input type="number" id="linguagens" placeholder="Digite a nota de Linguagens" required>
    
    <label for="redacao">Redação:</label>
    <input type="number" id="redacao" placeholder="Digite a nota de Redação" required>
    
    <button onclick="calcularMedia()">Calcular Média</button>
    
    <p id="resultado"></p>

    <div id="shadow"></div>
    <div id="uninassauText">
        <p>UNINASSAU GARANHUNS</p>
    </div>

    <script>
        function calcularMedia() {
            const matematica = parseFloat(document.getElementById("matematica").value);
            const humanas = parseFloat(document.getElementById("humanas").value);
            const natureza = parseFloat(document.getElementById("natureza").value);
            const linguagens = parseFloat(document.getElementById("linguagens").value);
            const redacao = parseFloat(document.getElementById("redacao").value);

            if (isNaN(matematica) || isNaN(humanas) || isNaN(natureza) || isNaN(linguagens) || isNaN(redacao)) {
                alert("Por favor, insira valores numéricos válidos.");
                return;
            }

            const mediaGeral = (matematica + humanas + natureza + linguagens + redacao) / 5;

            document.getElementById("resultado").innerHTML = `Sua média geral é: ${mediaGeral.toFixed(2)}`;

            if (mediaGeral >= 250 && mediaGeral <= 650.99) {
                document.getElementById("resultado").innerHTML += "<br> Você tem um desconto de 60% nos cursos da UNINASSAU Garanhuns.";
            } else if (mediaGeral >= 651 && mediaGeral <= 899.99) {
                document.getElementById("resultado").innerHTML += "<br> Você tem um desconto de 70% nos cursos da UNINASSAU Garanhuns.";
            } else if (mediaGeral >= 900) {
                document.getElementById("resultado").innerHTML += "<br> Você tem um desconto de 100% nos cursos da UNINASSAU Garanhuns.";
            }
        }
    </script>
</body>
</html>
