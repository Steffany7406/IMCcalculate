<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="shortcut icon" href="Phoenix Company [Tamanho original].png" type="image/x-icon">
    <title>Phoenix's Company Calculator</title>

    <link rel="stylesheet" href="calcule.css">
</head>
<body>
    <script src="calcule.js"></script>
    <main>
        <div class="container">
            <div class="title">Calculadora - IMC</div>
             <div class="input"><br>
                 <label for="name">Nome:</label>
                 <input type="text" id="nome">
                 <br><br>
                 <label for="height">Altura:</label>
                 <input type="number" id="altura">
                 <br><br>
                 <label for="">Peso:</label>
                 <input type="number" id="Peso">   
             </div><br>
             <button id="calcular" onclick="imc()">Calcular</button>
             <div class="result" id="resultado"></div>
        </div>
    </main>
    <p><img src="1268747583764tabela de IMC.jpg" alt="" /></p>
    
</body>
</html>

*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}
body{
    background-image: url(4K-Beautiful-Desktop-Wallpaper-Colorful-Nature-Sunset-Landscape-Free-Download-2048x1152.jpg);
}
body{
    align-items: center;
    justify-content: center;
    text-align: center;
    display: flex; /*Para ajudar a centralizar o que tiver na page*/
    height: 100%; /*Para tomar 100 da page*/
}
.container{
    background-color: rgba(162, 0, 255, 0.644);
    box-shadow: 10px;
    display: block;
    padding: 45px;
    border-radius: 10px;
    align-items: center;
    position: absolute;
    top: 50%;
    transform: translateY(-50%) translateX(-50%);
    right: 40%;
}
.title{
    font-weight: bold;
    color: antiquewhite;
    font-size: 35px;
    padding: 10px;
}
input{
    padding: 16px;
    border-radius: 9px;
    width: 200px;
}
label{
    color: blanchedalmond;
    font-size: 27px;
    padding: 10px;
}
button{
    color: beige;
    background-color: rgb(140, 0, 255);
    padding: 16px;
    width: 226px;
    border-radius: 9px;
    justify-content: space-between;
    font-size: 20px;
}
button:hover{
    background-color: rgb(255, 0, 255);
}
.result{
    font-size: 16px;
    font-weight: bold;
    box-shadow: 15px;
    color: blanchedalmond;
    padding: 10px;
}
table {
    width: 50%;
    border-collapse: collapse;
    display: flex;
}
img{
    width: 560px;
    height: 509px;
    box-shadow: 10px;
    display: flex;
    padding: 25px;
    border-radius: 4px;
    align-items: right;
    justify-content: right;
    position: absolute;
    top: 18%;
    left: 52%;
    bottom: 25%;
} 

document.addEventListener("DOMContentLoaded", function() {
    // Obtenha os elementos do formulário
    const nomeInput = document.getElementById("nome");
    const alturaInput = document.getElementById("altura");
    const pesoInput = document.getElementById("Peso");
    const calcularButton = document.getElementById("calcular");
    const resultadoElement = document.getElementById("resultado");
  
     //Função para calcular o IMC
    function calcularImc() {
      // Obtenha os valores dos campos
      const nome = nomeInput.value;
      const altura = parseFloat(alturaInput.value);
      const peso = parseFloat(pesoInput.value);
  
      // Verifique se todos os campos estão preenchidos
      if (nome !== '' && altura !== '' && peso !== '') {
        // Calcule o IMC
        const imc = (peso / (altura * altura)).toFixed(2);
  
        // Exiba o resultado
        resultadoElement.innerText = `${nome} tem ${altura} de altura e seu IMC é de ${imc}`;
      } else {
        alert("Por favor, preencha todas as caixas!");
      }
    }
  
    //Adicione um evento de clique ao botão calcular
    calcularButton.addEventListener("click", calcularImc);
  });
