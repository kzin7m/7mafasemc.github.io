
<html lang="pt-BR">
<head>
<meta charset="UTF-8" />
<title>Loja VIP 7MafaseMC</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Anton&display=swap');

  body {
    margin: 0;
    padding: 0;
    background: url('https://i.imgur.com/UOwo8cp.png') no-repeat center center fixed;
    background-size: cover;
    font-family: 'Anton', sans-serif;
    color: white;
    text-align: center;
  }

  header {
    background: rgba(0,0,0,0.6);
    padding: 30px 20px;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 15px;
  }

  header img {
    height: 70px;
    width: auto;
  }

  header h1 {
    font-size: 48px;
    font-weight: 900;
    margin: 0;
    user-select: none;
    background: linear-gradient(90deg, red 50%, white 50%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }

  .container {
    display: grid;
    grid-template-columns: repeat(auto-fit,minmax(220px,1fr));
    gap: 20px;
    padding: 40px;
    max-width: 1000px;
    margin: auto;
  }

  .card {
    background: rgba(30, 41, 59, 0.85);
    padding: 20px;
    border-radius: 12px;
    transition: transform 0.3s, box-shadow 0.3s;
    color: white;
  }

  .card:hover {
    transform: scale(1.05);
    box-shadow: 0 0 20px #22c55e;
  }

  h2 {
    margin-top: 0;
  }

  button {
    padding: 10px 20px;
    border: none;
    border-radius: 8px;
    background: #22c55e;
    color: white;
    cursor: pointer;
    font-weight: bold;
    margin-top: 10px;
  }

  button:hover {
    background: #16a34a;
  }

  form {
    margin: 20px auto;
    background: rgba(2, 6, 23, 0.85);
    padding: 20px;
    border-radius: 12px;
    width: 90%;
    max-width: 400px;
  }

  input {
    width: 90%;
    padding: 10px;
    margin: 10px 0;
    border-radius: 6px;
    border: none;
    font-size: 16px;
  }

  .qr-container {
    margin-top: 20px;
    color: white;
  }

  /* Seção de links para servidor e Discord */
  .links-container {
    margin: 40px auto 60px;
    max-width: 400px;
    display: flex;
    justify-content: center;
    gap: 20px;
  }

  .links-container a {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: #e63946;
    color: white;
    font-weight: bold;
    padding: 15px 30px;
    border-radius: 30px;
    font-size: 18px;
    text-decoration: none;
    box-shadow: 0 4px 12px rgba(230, 57, 70, 0.7);
    transition: background-color 0.3s ease;
  }

  .links-container a:hover {
    background: #b8323b;
  }

  .links-container a.discord {
    background: #7289da;
    box-shadow: 0 4px 12px rgba(114, 137, 218, 0.7);
  }

  .links-container a.discord:hover {
    background: #5b6eae;
  }

  .links-container img {
    height: 24px;
    width: 24px;
  }
</style>
</head>
<body>

<header>
  <img src="https://i.imgur.com/wZoMTLp.png" alt="Logo K" />
  <h1>7MafaseMC</h1>
</header>

<form id="userForm">
  <input type="text" id="nick" placeholder="Seu Nick Minecraft" required /><br />
  <input type="text" id="nome" placeholder="Seu Nome" required /><br />
  <input type="text" id="cpf" placeholder="CPF" required /><br />
</form>

<div class="container">
  <div class="card">
    <h2>⭐ VIP Lite</h2>
    <div class="price">R$5</div>
    <button onclick="gerarQR('5','VIP Lite')">Comprar</button>
  </div>
  <div class="card">
    <h2>🔥 VIP</h2>
    <div class="price">R$10</div>
    <button onclick="gerarQR('10','VIP')">Comprar</button>
  </div>
  <div class="card">
    <h2>💎 VIP Plus</h2>
    <div class="price">R$20</div>
    <button onclick="gerarQR('20','VIP Plus')">Comprar</button>
  </div>
  <div class="card">
    <h2>👑 VIP Elite</h2>
    <div class="price">R$35</div>
    <button onclick="gerarQR('35','VIP Elite')">Comprar</button>
  </div>
  <div class="card">
    <h2>🎉 Fazer Evento</h2>
    <div class="price">R$20</div>
    <button onclick="gerarQR('20','Fazer Evento')">Comprar</button>
  </div>
</div>

<!-- Seção de links -->
<div class="links-container">
  <a href="minecraft://seu-ip-aqui" target="_blank" rel="noopener noreferrer">Acesse nosso servidor</a>
  <a href="https://discord.gg/cC2zgfBsxJ" target="_blank" rel="noopener noreferrer" class="discord">
    <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/discord/discord-original.svg" alt="Discord" />
    Servidor do Discord
  </a>
</div>

<div class="qr-container" id="qrContainer"></div>

<script>
  function gerarQR(valor, produto) {
    const nick = document.getElementById("nick").value;
    const nome = document.getElementById("nome").value;
    const cpf = document.getElementById("cpf").value;
    if (!nick || !nome || !cpf) {
      alert("Preencha todos os campos!");
      return;
    }
    const pix = "kzinbala9@gmail.com";
    const dataPIX = `00020101021226850014BR.GOV.BCB.PIX0114${pix}520400005303986540${valor}0005802BR59227MafaseMC6009Sao Paulo61080540900062070503***6304`;
    const qrURL = `https://api.qrserver.com/v1/create-qr-code/?size=200x200&data=${encodeURIComponent(
      dataPIX
    )}`;
    document.getElementById("qrContainer").innerHTML = `
    <h3>Pagamento PIX - R$${valor}</h3>
    <p>Produto: ${produto}</p>
    <p>Nick: ${nick} | Nome: ${nome} | CPF: ${cpf}</p>
    <img src="${qrURL}" alt="QR Code PIX" /><br />
    <button onclick="copiarPIX()">COMPRAR</button>
    <p id="pixKey" style="display:none">${pix}</p>
  `;
  }

  function copiarPIX() {
    const pix = document.getElementById("pixKey").innerText;
    navigator.clipboard.writeText(pix).then(() => {
      alert("PIX copiado: " + pix);
    });
  }
</script>

</body>
</html>
