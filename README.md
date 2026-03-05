<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<title>Loja 7MafaseMC</title>
<style>

body{
font-family: Arial, sans-serif;
margin:0;
padding:0;
background: url('https://i.imgur.com/q8U7pYk.jpg') no-repeat center center fixed;
background-size: cover;
color:white;
text-align:center;
}

header{
background:rgba(2,6,23,0.85);
padding:30px;
font-size:32px;
font-weight:bold;
text-shadow: 2px 2px 4px #000;
}

.container{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
gap:20px;
padding:40px;
}

.card{
background:rgba(30,41,59,0.85);
padding:20px;
border-radius:12px;
transition: transform 0.3s, box-shadow 0.3s;
}

.card:hover{
transform:scale(1.05);
box-shadow:0 0 20px #22c55e;
}

h2{
margin-top:0;
}

.price{
font-size:22px;
margin:10px 0;
color:#22c55e;
font-weight:bold;
}

.pix{
background:rgba(2,6,23,0.85);
padding:20px;
margin:30px;
border-radius:12px;
font-size:18px;
}

button{
padding:10px 20px;
border:none;
border-radius:8px;
background:#22c55e;
color:white;
cursor:pointer;
font-weight:bold;
margin-top:10px;
}

button:hover{
background:#16a34a;
}

.qr{
margin-top:15px;
}

</style>
</head>
<body>

<header>
🛒 Loja VIP do Servidor 7MafaseMC
</header>

<div class="container">

<div class="card">
<h2>⭐ VIP Lite</h2>
<div class="price">R$5</div>
<button onclick="copiarPIX()">Copiar PIX</button>
</div>

<div class="card">
<h2>🔥 VIP</h2>
<div class="price">R$10</div>
<button onclick="copiarPIX()">Copiar PIX</button>
</div>

<div class="card">
<h2>💎 VIP Plus</h2>
<div class="price">R$20</div>
<button onclick="copiarPIX()">Copiar PIX</button>
</div>

<div class="card">
<h2>👑 VIP Elite</h2>
<div class="price">R$35</div>
<button onclick="copiarPIX()">Copiar PIX</button>
</div>

</div>

<div class="pix">
💰 Pague pelo PIX:<br><br>
<b id="pixkey">kzinbala9@gmail.com</b><br><br>
Após pagar, envie o comprovante para o dono do servidor.<br>

<div class="qr">
<img src="https://api.qrserver.com/v1/create-qr-code/?size=150x150&data=00020101021226850014BR.GOV.BCB.PIX0114kzinbala9@gmail.com520400005303986540500.005802BR59227MafaseMC6009Sao Paulo61080540900062070503***6304" alt="QR Code PIX">
</div>
</div>

<script>
function copiarPIX() {
  const pix = document.getElementById("pixkey").innerText;
  navigator.clipboard.writeText(pix).then(() => {
    alert("PIX copiado: " + pix);
  });
}
</script>

</body>
</html>
