<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora de Média</title>
</head>
<body>
    <h1>Calculadora de Média</h1>
    <form id="notaForm">
        <label for="ap1">Nota AP1:</label>
        <input type="number" id="ap1" step="0.01" required>
        <br><br>
        <label for="ac">Nota AC:</label>
        <input type="number" id="ac" step="0.01" required>
        <br><br>
        <button type="button" id="calcularButton">Calcular</button>
    </form>
    <p id="resultado"></p>
    <script>
        // Função que realiza os cálculos
        function calcular() {
            const ap1 = parseFloat(document.getElementById("ap1").value) || 0; // Captura o valor ou assume 0
            const ac = parseFloat(document.getElementById("ac").value) || 0;   // Captura o valor ou assume 0
            const calculo = ap1 * 0.4 + ac * 0.2;
            const quantoFaltaPraSete = (7 - calculo) / 0.4;

            const resultado = document.getElementById("resultado");
            if (quantoFaltaPraSete > 10) {
                resultado.textContent = "Você está de AS, vai estudar nina!!";
            } else {
                resultado.textContent = `Você precisa de ${quantoFaltaPraSete.toFixed(2)} na AP2. Tá tranquilo, bora disbicar nina!!`;
            }
        }

        // Adicionando o evento de clique ao botão
        document.getElementById("calcularButton").addEventListener("click", calcular);
    </script>
</body>
</html>
