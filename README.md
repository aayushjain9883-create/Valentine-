# Valentine-
Invitation
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Valentine Surprise 💘</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      height: 100vh;
      margin: 0;
      display: flex;
      justify-content: center;
      align-items: center;
    }
    .box {
      background: white;
      padding: 25px;
      border-radius: 16px;
      box-shadow: 0 10px 25px rgba(0,0,0,0.25);
      text-align: center;
      width: 320px;
      position: relative;
    }
    .heart {
      font-size: 55px;
      cursor: pointer;
      animation: pulse 1s infinite;
    }
    @keyframes pulse {
      0% { transform: scale(1); }
      50% { transform: scale(1.25); }
      100% { transform: scale(1); }
    }
    button {
      padding: 10px 20px;
      border: none;
      border-radius: 10px;
      font-size: 16px;
      cursor: pointer;
      margin: 10px;
    }
    #yes {
      background: #ff4b5c;
      color: white;
    }
    #no {
      background: #ddd;
      position: absolute;
    }
  </style>
</head>
<body>

<div class="box" id="game">
  <h2>Tap the heart 💖</h2>
  <p>Only true love unlocks the secret 😉</p>
  <div class="heart" onclick="unlock()">❤️</div>
</div>

<script>
  function unlock() {
    document.getElementById("game").innerHTML = `
      <h2>Question time 😏</h2>
      <p>Will you be my Valentine? 💘</p>
      <button id="yes" onclick="yesClicked()">YES 💖</button>
      <button id="no" onmouseover="moveNo()">NO 🙄</button>
    `;
  }

  function moveNo() {
    const noBtn = document.getElementById("no");
    const box = document.querySelector(".box");
    const maxX = box.offsetWidth - noBtn.offsetWidth;
    const maxY = box.offsetHeight - noBtn.offsetHeight;

    const x = Math.random() * maxX;
    const y = Math.random() * maxY;

    noBtn.style.left = x + "px";
    noBtn.style.top = y + "px";
  }

  function yesClicked() {
    document.getElementById("game").innerHTML = `
      <h2>YAYYY 🥹💘</h2>
      <p>I knew it!</p>
      <h3>See you on 14th Feb ❤️</h3>
      <p>✨ Just You & Me ✨</p>
    `;
  }
</script>

</body>
</html>
