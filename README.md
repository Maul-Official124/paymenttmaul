<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Payment Maul Official</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --primary-color: #00c6ff;
      --secondary-color: #0072ff;
      --background-gradient: linear-gradient(135deg, #e0f7fa, #80deea);
      --text-gradient: linear-gradient(to right, var(--primary-color), var(--secondary-color));
      --container-bg: #ffffff;
      --shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: 'Poppins', sans-serif;
      background: var(--background-gradient);
      display: flex;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
      padding: 20px;
    }

    .container {
      background: var(--container-bg);
      padding: 30px;
      border-radius: 20px;
      box-shadow: var(--shadow);
      text-align: center;
      width: 100%;
      max-width: 400px;
      animation: fadeIn 1s ease;
    }

    h1 {
      background: var(--text-gradient);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      font-size: 26px;
      font-weight: 700;
      margin-bottom: 25px;
    }

    h2 {
      color: var(--secondary-color);
      font-size: 22px;
      margin: 30px 0 15px;
    }

    .button, .copy-button, .link-button {
      background: var(--text-gradient);
      color: white;
      padding: 12px 20px;
      border: none;
      border-radius: 12px;
      font-size: 16px;
      font-weight: 600;
      margin: 10px 0;
      display: inline-block;
      cursor: pointer;
      transition: all 0.3s ease;
      text-decoration: none;
      width: 100%;
      max-width: 250px;
    }

    .button:hover, .copy-button:hover, .link-button:hover {
      transform: translateY(-3px);
      box-shadow: 0 4px 15px rgba(0, 114, 255, 0.4);
    }

    .info {
      margin-top: 20px;
      opacity: 0;
      max-height: 0;
      overflow: hidden;
      transition: all 0.5s ease;
    }

    .info.show {
      opacity: 1;
      max-height: 500px;
    }

    .info h3 {
      margin-bottom: 5px;
      font-size: 18px;
      color: var(--secondary-color);
    }

    .info p {
      margin-bottom: 15px;
      font-size: 16px;
      color: #555;
    }

    .qr-code {
      margin: 25px 0;
      cursor: pointer;
      transition: transform 0.4s ease;
    }

    .qr-code img {
      width: 200px;
      border-radius: 15px;
      transition: transform 0.5s ease;
    }

    .qr-code.zoom img {
      transform: scale(1.8);
    }

    .links {
      margin-top: 20px;
    }

    @keyframes fadeIn {
      from {opacity: 0; transform: scale(0.95);}
      to {opacity: 1; transform: scale(1);}
    }
  </style>
</head>
<body>

<div class="container">
  <h1>𝗣𝗔𝗬𝗠𝗘𝗡𝗧 𝗠𝗔𝗨𝗟 𝗢𝗙𝗙𝗜𝗖𝗜𝗔𝗟</h1>

  <button class="button" onclick="showDana()">LIHAT NOMOR DANA</button>

  <div id="danaInfo" class="info">
    <h3>NOMOR DANA</h3>
    <p id="nomorDana">0882008647756</p>
    <button class="copy-button" onclick="copyDana()">Copy Nomor</button>

    <h3>NAMA AKUN</h3>
    <p>𝗔/𝗡 𝗧𝗢𝗟𝗫𝗫𝗫</p>
  </div>

  <h2>SCAN QRIS</h2>
  <div class="qr-code" id="qrisImage" onclick="zoomQRIS()">
    <img src="https://files.catbox.moe/s6nxzl.jpg" alt="QRIS">
  </div>

  <div class="links">
    <a href="https://whatsapp.com/channel/0029VbAQ2zFAe5VkDNVjBU1g" class="link-button" target="_blank">Channel Testimoni ⚡</a>
  </div>
</div>

<script>
function showDana() {
  const danaInfo = document.getElementById('danaInfo');
  danaInfo.classList.toggle('show');
}

function zoomQRIS() {
  const qris = document.getElementById('qrisImage');
  qris.classList.toggle('zoom');
}

function copyDana() {
  const nomor = document.getElementById('nomorDana').innerText;
  navigator.clipboard.writeText(nomor)
    .then(() => {
      alert('Nomor DANA berhasil disalin!');
    })
    .catch(() => {
      alert('Gagal menyalin nomor DANA.');
    });
}
</script>

</body>
</html>
