<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<title>Calculadora de Pisos</title>

<style>
body{
font-family: Arial;
background:#f4f4f4;
text-align:center;
padding:40px;
}

.container{
background:white;
padding:30px;
border-radius:10px;
max-width:500px;
margin:auto;
box-shadow:0 0 10px rgba(0,0,0,0.2);
}

input, select{
width:90%;
padding:10px;
margin:10px;
font-size:16px;
}

button{
padding:12px 25px;
font-size:16px;
background:#2e7d32;
color:white;
border:none;
border-radius:5px;
}

.resultado{
margin-top:20px;
font-size:18px;
}
</style>
</head>

<body>

<div class="container">

<h2>Calculadora de Piso</h2>

<input type="number" id="largura" placeholder="Largura do ambiente (m)">
<input type="number" id="comprimento" placeholder="Comprimento do ambiente (m)">

<select id="piso">
<option value="2.17">Piso 60x60 (2.17m² caixa)</option>
<option value="2.50">Piso 70x70 (2.50m² caixa)</option>
<option value="1.44">Piso 45x45 (1.44m² caixa)</option>
</select>

<button onclick="calcular()">Calcular</button>

<div class="resultado" id="resultado"></div>

</div>

<script>

function calcular(){

let largura = document.getElementById("largura").value
let comprimento = document.getElementById("comprimento").value
let caixa = document.getElementById("piso").value

let area = largura * comprimento

let areaComPerda = area * 1.10

let caixas = Math.ceil(areaComPerda / caixa)

document.getElementById("resultado").innerHTML =
"Área: " + area.toFixed(2) + " m² <br>" +
"Com 10% de perda: " + areaComPerda.toFixed(2) + " m² <br>" +
"Caixas necessárias: " + caixas

}

</script>

</body>
</html>
