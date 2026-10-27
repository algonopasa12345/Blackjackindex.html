<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Neon Arcade Casino</title>
<style>
*{box-sizing:border-box}
body{margin:0;background:#07111f;color:#fff;font-family:Arial,sans-serif}
main{max-width:900px;margin:auto;padding:20px}
h1{text-align:center}
.notice{background:#11233e;border:1px solid #294b78;padding:12px 15px;border-radius:12px;color:#cfe1ff}
.balance{text-align:center;font-size:24px;margin:18px}
.tabs{text-align:center;margin-bottom:15px}
button{border:0;border-radius:10px;padding:11px 16px;margin:5px;background:#3478f6;color:#fff;font-weight:bold;cursor:pointer}
button:disabled{opacity:.4;cursor:not-allowed}
.game{display:none;background:#101e34;border:1px solid #263c5e;border-radius:18px;padding:20px;margin-top:15px}
.game.active{display:block}
.display{background:#081424;border-radius:14px;padding:20px;text-align:center;margin:15px 0}
.reels{font-size:44px;letter-spacing:10px;min-height:55px}
.result{min-height:24px;font-weight:bold}
.wheel{width:190px;height:190px;border-radius:50%;margin:15px auto;border:8px solid #d8b74e;background:conic-gradient(#e53b50 0 45deg,#171717 45deg 90deg,#e53b50 90deg 135deg,#171717 135deg 180deg,#e53b50 180deg 225deg,#171717 225deg 270deg,#e53b50 270deg 315deg,#171717 315deg);display:flex;align-items:center;justify-content:center;font-size:42px;font-weight:bold}
.cards{display:flex;justify-content:center;gap:10px;flex-wrap:wrap;min-height:90px}
.card{width:60px;height:82px;background:white;color:#111;border-radius:9px;display:flex;align-items:center;justify-content:center;font-size:24px;font-weight:bold}
.score{text-align:center;margin:10px}
footer{text-align:center;color:#91a8c7;margin:25px}
</style>
</head>
<body>
<main>
<h1>🎮 Neon Arcade Casino</h1>
<div class="notice">Este es un juego de arcade con puntos ficticios. No usa dinero real ni ofrece premios.</div>
<div class="balance">🪙 Puntos: <b id="coins">1000</b></div>

<div class="tabs">
<button id="tabSlots">🎰 Máquina</button>
<button id="tabWheel">🎡 Rueda</button>
<button id="tabCards">🃏 21 Arcade</button>
<button id="resetBtn">↻ Reiniciar</button>
</div>

<section id="slotsGame" class="game active">
<h2>🎰 Máquina de símbolos</h2>
<p>Cada partida cuesta 25 puntos. Dos símbolos iguales: +50. Tres iguales: +200.</p>
<div class="display">
<div id="reels" class="reels">🍒 ⭐ 💎</div>
<p id="slotResult" class="result">Pulsa JUGAR.</p>
<button id="slotsBtn">JUGAR · 25</button>
</div>
</section>

<section id="wheelGame" class="game">
<h2>🎡 Rueda de puntos</h2>
<p>Cada giro cuesta 20 puntos.</p>
<div class="display">
<div id="wheel" class="wheel">?</div>
<p id="wheelResult" class="result">Pulsa GIRAR.</p>
<button id="wheelBtn">GIRAR · 20</button>
</div>
</section>

<section id="cardsGame" class="game">
<h2>🃏 21 Arcade</h2>
<p>Intenta acercarte a 21 sin pasarte. La ronda cuesta 30 puntos. Una victoria devuelve 60 puntos.</p>
<div class="display">
<h3>Tus cartas</h3>
<div id="playerCards" class="cards"></div>
<div class="score">Puntuación: <b id="playerScore">0</b></div>
<h3>Rival</h3>
<div id="dealerCards" class="cards"></div>
<div class="score">Puntuación rival: <b id="dealerScore">?</b></div>
<p id="cardResult" class="result">Pulsa NUEVA RONDA.</p>
<button id="newRoundBtn">NUEVA RONDA · 30</button>
<button id="hitBtn" disabled>PEDIR</button>
<button id="standBtn" disabled>PLANTARSE</button>
</div>
</section>

<footer>Neon Arcade · puntos virtuales</footer>
</main>

<script>
(function(){
"use strict";

const $ = id => document.getElementById(id);
let coins = 1000;
let player = [];
let dealer = [];
let activeRound = false;

try {
  const stored = localStorage.getItem("neonArcadeCoins");
  if (stored !== null && !isNaN(Number(stored))) coins = Number(stored);
} catch(e) {}

function save(){
  $("coins").textContent = coins;
  try { localStorage.setItem("neonArcadeCoins", String(coins)); } catch(e) {}
}

function pay(amount){
  if(coins < amount){
    alert("No tienes suficientes puntos. Pulsa Reiniciar para volver a 1000.");
    return false;
  }
  coins -= amount;
  save();
  return true;
}

function showGame(gameId){
  ["slotsGame","wheelGame","cardsGame"].forEach(id => $(id).classList.remove("active"));
  $(gameId).classList.add("active");
}

$("tabSlots").addEventListener("click", () => showGame("slotsGame"));
$("tabWheel").addEventListener("click", () => showGame("wheelGame"));
$("tabCards").addEventListener("click", () => showGame("cardsGame"));

$("resetBtn").addEventListener("click", function(){
  coins = 1000;
  player = [];
  dealer = [];
  activeRound = false;
  $("hitBtn").disabled = true;
  $("standBtn").disabled = true;
  $("cardResult").textContent = "Pulsa NUEVA RONDA.";
  renderCards(false);
  save();
});

$("slotsBtn").addEventListener("click", function(){
  if(!pay(25)) return;
  const symbols = ["🍒","🍋","⭐","💎","7️⃣"];
  const result = [0,0,0].map(() => symbols[Math.floor(Math.random()*symbols.length)]);
  $("reels").textContent = result.join(" ");

  let prize = 0;
  if(result[0] === result[1] && result[1] === result[2]) prize = 200;
  else if(result[0] === result[1] || result[1] === result[2] || result[0] === result[2]) prize = 50;

  coins += prize;
  save();
  $("slotResult").textContent = prize > 0 ? "¡Premio! +" + prize + " puntos" : "Sin premio esta vez.";
});

$("wheelBtn").addEventListener("click", function(){
  if(!pay(20)) return;
  const prizes = [0,5,10,15,20,25,40,60];
  const prize = prizes[Math.floor(Math.random()*prizes.length)];
  $("wheel").textContent = "…";
  $("wheelBtn").disabled = true;

  setTimeout(function(){
    $("wheel").textContent = prize;
    coins += prize;
    save();
    $("wheelResult").textContent = "Has conseguido " + prize + " puntos.";
    $("wheelBtn").disabled = false;
  }, 500);
});

function drawCard(){
  const values = [2,3,4,5,6,7,8,9,10,10,10,10,11];
  return values[Math.floor(Math.random()*values.length)];
}

function score(hand){
  let total = hand.reduce((a,b) => a+b, 0);
  let aces = hand.filter(v => v === 11).length;
  while(total > 21 && aces > 0){
    total -= 10;
    aces--;
  }
  return total;
}

function label(v){ return v === 11 ? "A" : String(v); }

function renderCards(hideDealer){
  $("playerCards").innerHTML = player.map(v => '<div class="card">'+label(v)+'</div>').join("");
  $("dealerCards").innerHTML = dealer.map((v,i) =>
    '<div class="card">'+(hideDealer && i === 1 ? "?" : label(v))+'</div>'
  ).join("");
  $("playerScore").textContent = score(player);
  $("dealerScore").textContent = hideDealer ? "?" : score(dealer);
}

function finishRound(message, reward){
  coins += reward;
  activeRound = false;
  $("hitBtn").disabled = true;
  $("standBtn").disabled = true;
  $("cardResult").textContent = message;
  renderCards(false);
  save();
}

$("newRoundBtn").addEventListener("click", function(){
  if(activeRound) return;
  if(!pay(30)) return;

  player = [drawCard(), drawCard()];
  dealer = [drawCard(), drawCard()];
  activeRound = true;

  $("hitBtn").disabled = false;
  $("standBtn").disabled = false;
  $("cardResult").textContent = "Tu turno.";
  renderCards(true);

  if(score(player) === 21) $("standBtn").click();
});

$("hitBtn").addEventListener("click", function(){
  if(!activeRound) return;
  player.push(drawCard());
  renderCards(true);

  if(score(player) > 21) finishRound("Te has pasado de 21. Gana el rival.", 0);
  else if(score(player) === 21) $("standBtn").click();
});

$("standBtn").addEventListener("click", function(){
  if(!activeRound) return;

  while(score(dealer) < 17) dealer.push(drawCard());

  const p = score(player);
  const d = score(dealer);

  if(d > 21 || p > d) finishRound("¡Has ganado! +60 puntos.", 60);
  else if(p === d) finishRound("Empate: recuperas los 30 puntos.", 30);
  else finishRound("Gana el rival.", 0);
});

save();
renderCards(false);
})();
</script>
</body>
</html>
