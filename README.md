# freefire-adm
Uma página de adm de compra venda e troca de contas 
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Free Fire — Envio via ADM</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #0b0b12;
      color: #fff;
      display: flex;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
    }
    .card {
      background: #151528;
      padding: 20px;
      border-radius: 12px;
      width: 100%;
      max-width: 420px;
      box-shadow: 0 0 20px rgba(0,0,0,.5);
    }
    h1 {
      text-align: center;
      margin-bottom: 16px;
    }
    label {
      font-size: 14px;
      opacity: .9;
    }
    input, select, button, textarea {
      width: 100%;
      margin-top: 6px;
      margin-bottom: 14px;
      padding: 12px;
      border-radius: 8px;
      border: none;
      outline: none;
      font-size: 15px;
    }
    input, textarea {
      background: #0f0f1e;
      color: #fff;
    }
    button {
      background: #25D366;
      color: #000;
      font-weight: bold;
      cursor: pointer;
    }
    .nota {
      font-size: 12px;
      opacity: .7;
      text-align: center;
    }
  </style>
</head>
<body>

  <div class="card">
    <h1>Envio de Conta — Via ADM</h1>

    <label>UID da conta Free Fire</label>
    <input id="uid" type="text" placeholder="Ex: 123456789" />

    <label>E-mail de contato</label>
    <input id="email" type="email" placeholder="seuemail@gmail.com" />

    <label>Valor combinado (R$)</label>
    <input id="valor" type="number" placeholder="Ex: 500" />

    <label>Observações</label>
    <textarea id="obs" placeholder="Ex: Conta full, via ADM"></textarea>

    <button onclick="enviarWhats()">Enviar para o ADM</button>

    <p class="nota">
      ⚠️ Nunca informe senha. O ADM não solicita credenciais.
    </p>
  </div>

  <script>
    function enviarWhats() {
      const uid = document.getElementById("uid").value.trim();
      const email = document.getElementById("email").value.trim();
      const valor = document.getElementById("valor").value.trim();
      const obs = document.getElementById("obs").value.trim();

      if (!uid || !email || !valor) {
        alert("Preencha todos os campos obrigatórios.");
        return;
      }

      const mensagem =
`🚨 FREE FIRE — VIA ADM 🚨

🆔 UID:
${uid}

📧 Contato do vendedor:
${email}

💰 Valor combinado:
R$ ${valor}

📝 Observações:
${obs || "Nenhuma"}

Status: Solicitação enviada ao ADM`;

      const numeroADM = "5546991326905";
      const url = "https://wa.me/" + numeroADM + "?text=" + encodeURIComponent(mensagem);

      window.location.href = url;
    }
  </script>

</body>
</html>
