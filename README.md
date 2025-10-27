<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>🎉 Happy Birthday Ocid 🎉</title>
<style>
  body {
    margin: 0;
    padding: 0;
    background: linear-gradient(to bottom, #ffeefc, #d9c8ff);
    font-family: "Poppins", sans-serif;
    text-align: center;
    overflow: hidden;
  }

  /* ✉️ Amplop */
  .envelope {
    position: absolute;
    top: 45%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 180px;
    height: 120px;
    background: white;
    border: 2px solid #ddd;
    border-radius: 6px;
    box-shadow: 0 6px 15px rgba(0,0,0,0.1);
    cursor: pointer;
    transition: transform 0.4s ease;
  }
  .envelope:hover {
    transform: translate(-50%, -50%) scale(1.05);
  }
  .heart {
    position: absolute;
    top: 45%;
    left: 50%;
    transform: translate(-50%, -50%);
    color: red;
    font-size: 30px;
  }

  /* 🎂 Info text */
  .info {
    position: absolute;
    top: 60%;
    left: 50%;
    transform: translate(-50%, -50%);
    font-size: 1.3em;
    font-weight: bold;
    color: #7b2cbf;
    opacity: 0;
    transition: opacity 1s ease;
    cursor: pointer;
  }

  /* 🎁 Gift box */
  .gift {
    position: absolute;
    top: 48%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 130px;
    height: 130px;
    background: #ff85a2;
    border-radius: 10px;
    box-shadow: 0 6px 15px rgba(0,0,0,0.2);
    display: none;
    cursor: pointer;
  }
  .gift::before {
    content: '';
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    width: 20px;
    height: 130px;
    background: #fff;
  }
  .gift::after {
    content: '';
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    width: 130px;
    height: 20px;
    background: #fff;
  }

  /* 🎂 Realistic cake */
  .cake {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 200px;
    height: 120px;
    display: none;
  }
  .cake .layer {
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    width: 200px;
    height: 40px;
    background: #ffb3c6;
    border-radius: 10px;
    box-shadow: 0 6px 10px rgba(0,0,0,0.1);
  }
  .cake .layer:nth-child(2) { top: 35px; background: #ffd6a5; width: 180px; }
  .cake .layer:nth-child(3) { top: 70px; background: #caffbf; width: 160px; }

  .candle {
    position: absolute;
    top: -35px;
    left: 50%;
    transform: translateX(-50%);
    width: 12px;
    height: 35px;
    background: repeating-linear-gradient(45deg, #ff69b4, #ff69b4 5px, #fff 5px, #fff 10px);
    border-radius: 3px;
  }
  .flame {
    position: absolute;
    top: -15px;
    left: 50%;
    transform: translateX(-50%);
    width: 14px;
    height: 18px;
    background: radial-gradient(circle at 50% 20%, #fff, #ffd700, #ff4500);
    border-radius: 50%;
    opacity: 0;
    animation: flicker 0.3s infinite alternate;
  }
  @keyframes flicker {
    from { transform: translateX(-50%) scale(1); opacity: 1; }
    to { transform: translateX(-50%) scale(1.1); opacity: 0.8; }
  }

  /* 🎈 Balloon */
  .balloon {
    position: absolute;
    bottom: -100px;
    width: 50px;
    height: 70px;
    background: radial-gradient(circle at 30% 30%, #fff, var(--color));
    border-radius: 50%;
    animation: float 7s linear infinite;
    opacity: 0.9;
  }
  .string {
    position: absolute;
    width: 2px;
    height: 70px;
    background: rgba(0,0,0,0.2);
    left: 50%;
    bottom: -70px;
    transform: translateX(-50%);
  }
  @keyframes float {
    0% { transform: translateY(0); opacity: 1; }
    100% { transform: translateY(-120vh); opacity: 0; }
  }

  /* 🎀 Falling ribbons */
  .ribbon-fall {
    position: absolute;
    width: 10px;
    height: 60px;
    background: var(--color);
    opacity: 0.9;
    animation: fall 3s linear infinite;
  }
  @keyframes fall {
    0% { transform: translateY(0) rotate(0deg); }
    100% { transform: translateY(-100vh) rotate(360deg); opacity: 0; }
  }

  /* 💬 Message */
  .message {
    position: absolute;
    top: 80%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 85%;
    font-size: 1.1em;
    color: #4a148c;
    opacity: 0;
    transition: opacity 2s ease;
    line-height: 1.6;
  }
</style>
</head>
<body>

  <div class="envelope" id="envelope">
    <div class="heart">❤️</div>
  </div>

  <div class="info" id="info">Umur 16 tahun, 24 November 2009</div>
  <div class="gift" id="gift"></div>

  <div class="cake" id="cake">
    <div class="layer"></div>
    <div class="layer"></div>
    <div class="layer"></div>
    <div class="candle"></div>
    <div class="flame" id="flame"></div>
  </div>

  <div class="message" id="message">
    Today is your birthday, isn’t it? I hope you’re always happy,<br>
    and that all of your dreams and goals come true.<br>
    I wish for you to always be a strong and brave man.<br>
    I’m really glad to have met you.<br>
    Thank you for loving me sincerely. 💖
  </div>

<script>
  const envelope = document.getElementById("envelope");
  const info = document.getElementById("info");
  const gift = document.getElementById("gift");
  const cake = document.getElementById("cake");
  const flame = document.getElementById("flame");
  const message = document.getElementById("message");

  // Klik amplop
  envelope.addEventListener("click", () => {
    envelope.style.display = "none";
    info.style.opacity = "1";
  });

  // Klik tulisan info
  info.addEventListener("click", () => {
    info.style.display = "none";
    createBalloons();
    createRibbons();
    setTimeout(() => gift.style.display = "block", 2000);
  });

  // Klik kado
  gift.addEventListener("click", () => {
    gift.style.display = "none";
    cake.style.display = "block";
    flame.style.opacity = "1";
    setTimeout(() => message.style.opacity = "1", 1500);
  });

  // 🎈 Balon
  function createBalloons() {
    for (let i = 0; i < 25; i++) {
      const balloon = document.createElement("div");
      balloon.classList.add("balloon");
      balloon.style.left = Math.random() * 100 + "vw";
      balloon.style.setProperty("--color", randomColor());
      balloon.style.animationDuration = 5 + Math.random() * 3 + "s";
      const string = document.createElement("div");
      string.classList.add("string");
      balloon.appendChild(string);
      document.body.appendChild(balloon);
      setTimeout(() => balloon.remove(), 8000);
    }
  }

  // 🎀 Pita
  function createRibbons() {
    for (let i = 0; i < 20; i++) {
      const ribbon = document.createElement("div");
      ribbon.classList.add("ribbon-fall");
      ribbon.style.left = Math.random() * 100 + "vw";
      ribbon.style.setProperty("--color", randomColor());
      ribbon.style.animationDuration = 3 + Math.random() * 3 + "s";
      document.body.appendChild(ribbon);
      setTimeout(() => ribbon.remove(), 6000);
    }
  }

  // 🎨 Warna acak
  function randomColor() {
    const colors = ['#ff4d6d','#ff9f1c','#ffd166','#80ed99','#6d67e4','#ff8fab','#48cae4'];
    return colors[Math.floor(Math.random() * colors.length)];
  }
</script>
</body>
</html>
