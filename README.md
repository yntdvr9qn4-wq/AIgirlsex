# AIgirlsex
<index.html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Chat public</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      font-family: system-ui, -apple-system, BlinkMacSystemFont;
      background: #0f172a;
      color: #e5e7eb;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }
    .box {
      background: #020617;
      padding: 24px;
      border-radius: 12px;
      width: 100%;
      max-width: 360px;
      box-shadow: 0 20px 40px rgba(0,0,0,0.6);
    }
    input, button {
      width: 100%;
      padding: 12px;
      margin-top: 12px;
      border-radius: 8px;
      border: none;
      font-size: 16px;
    }
    input {
      background: #020617;
      color: #e5e7eb;
      border: 1px solid #334155;
    }
    button {
      background: #2563eb;
      color: white;
      cursor: pointer;
    }
    .error {
      color: #f87171;
      margin-top: 12px;
      display: none;
    }
    .chat {
      margin-top: 16px;
      min-height: 120px;
      background: #020617;
      border: 1px solid #334155;
      border-radius: 8px;
      padding: 12px;
    }
  </style>
</head>
<body>

<div class="box" id="loginBox">
  <h2>Accès public</h2>
  <input type="password" id="password" placeholder="Qwerty12345">
  <button onclick="checkPassword()">Entrer</button>
  <div class="error" id="error">Mot de passe incorrect</div>
</div>

<div class="box" id="contentBox" style="display:none;">
  <h2>Chat IA public</h2>
  <p>Bienvenue Sebas. Le chat répond uniquement en français.</p>
  <div class="chat">🟢 Prêt à discuter.</div>
</div>

<script>
 function sendMessage() {
    const chat = document.getElementById("chat");
    const input = document.getElementById("userInput");

    if (input.value.trim() === "") return;

    chat.innerHTML += `<p><strong>Toi :</strong> ${input.value}</p>`;
    chat.innerHTML += `<p><strong>IA :</strong> Je te réponds pour l’instant automatiquement.</p>`;

    input.value = "";
  }
  const PASSWORD = "Qwerty12345";

  function checkPassword() {
    const input = document.getElementById("password").value;
    if (input === PASSWORD) {
      sessionStorage.setItem("access", "ok");
      loginBox.style.display = "none";
      contentBox.style.display = "block";
    } else {
      error.style.display = "block";
    }
  }

  if (sessionStorage.getItem("access") === "ok") {
    loginBox.style.display = "none";
    contentBox.style.display = "block";
  }
</script>

</body>
</html>