<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Happy Birthday Dipa Didi 🎉</title>

<style>
/* ---------- GENERAL ---------- */
body {
  margin: 0;
  font-family: 'Segoe UI', sans-serif;
  height: 100vh;
  background: linear-gradient(135deg, #ff9a9e, #fad0c4);
  color: white;
  overflow: hidden;
}

.section {
  display: none;
  height: 100vh;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.section.active {
  display: flex;
}

button {
  padding: 12px 30px;
  border: none;
  border-radius: 25px;
  font-size: 16px;
  cursor: pointer;
  background: white;
  color: #ff4d6d;
  margin-top: 25px;
  transition: 0.3s;
}

button:hover {
  transform: scale(1.1);
}

/* ---------- WELCOME ---------- */
.circle {
  width: 120px;
  height: 120px;
  border-radius: 50%;
  border: 6px solid white;
  margin: auto;
  animation: pulse 2s infinite;
}

@keyframes pulse {
  0% { transform: scale(0.8); opacity: 0.6; }
  50% { transform: scale(1); opacity: 1; }
  100% { transform: scale(0.8); opacity: 0.6; }
}

/* ---------- BIRTHDAY ---------- */
.card {
  background: rgba(255,255,255,0.2);
  padding: 40px;
  border-radius: 20px;
  max-width: 500px;
}

.quote {
  margin-top: 20px;
  font-style: italic;
  font-size: 18px;
}

/* ---------- THANK YOU ---------- */
.balloons {
  font-size: 45px;
  margin-top: 30px;
  animation: float 2s infinite alternate;
}

@keyframes float {
  from { transform: translateY(0); }
  to { transform: translateY(-20px); }
}

.confetti span {
  position: absolute;
  top: -10px;
  font-size: 20px;
  animation: fall 3s linear infinite;
}

@keyframes fall {
  to { transform: translateY(110vh); }
}
</style>
</head>

<body>

<!-- ---------- SECTION 1: WELCOME ---------- -->
<div class="section active" id="welcome">
  <div>
    <div class="circle"></div>
    <h1>Welcome 🎉</h1>
    <p>Something special is waiting for you</p>
    <button onclick="showBirthday()">Enter</button>
  </div>
</div>

<!-- ---------- SECTION 2: BIRTHDAY ---------- -->
<div class="section" id="birthday">
  <div class="card">
    <h1>🎈 HAPPY BIRTHDAY 🎂🥳</h1>
    <h2>Dipa didi 💖</h2>
    <p class="quote">
      “A sister is a gift to the heart,  
      a friend to the spirit,  
      and a golden thread to the meaning of life.”
    </p>
    <button onclick="showThankYou()">Next Surprise 🎁</button>
  </div>
</div>

<!-- ---------- SECTION 3: THANK YOU ---------- -->
<div class="section" id="thankyou">
  <div>
    <h1>🎉🎈 Happy Birthday 🎈🎉</h1>
    <p>Thank you for being such a wonderful sister 💕</p>
    <p>May your life always shine with happiness 🌸</p>
    <div class="balloons">🎈 🎈 🎈 🎈 🎈</div>
  </div>
</div>

<script>
function showBirthday() {
  document.getElementById("welcome").classList.remove("active");
  document.getElementById("birthday").classList.add("active");
}

function showThankYou() {
  document.getElementById("birthday").classList.remove("active");
  document.getElementById("thankyou").classList.add("active");
  createConfetti();
}

/* Confetti Effect */
function createConfetti() {
  for (let i = 0; i < 30; i++) {
    let confetti = document.createElement("span");
    confetti.innerHTML = "🎉";
    confetti.style.left = Math.random() * 100 + "vw";
    confetti.style.animationDuration = (Math.random() * 2 + 2) + "s";
    confetti.classList.add("confetti");
    document.body.appendChild(confetti);

    setTimeout(() => confetti.remove(), 4000);
  }
}
</script>

</body>
</html>
