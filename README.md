# Bigdream_
colour prediction game

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>BIGDREAM_</title>
<style>
*{box-sizing:border-box}
body{
 margin:0;
 font-family:Arial,sans-serif;
 background:#0b1020;
 color:white;
}
header{
 background:#171f38;
 padding:22px;
 text-align:center;
 font-size:28px;
 font-weight:bold;
 color:#ffc83d;
}
.container{
 max-width:480px;
 margin:25px auto;
 padding:18px;
}
.card{
 background:#171f38;
 padding:22px;
 border-radius:16px;
 margin-bottom:18px;
 text-align:center;
}
h2{margin-top:0}
.points{
 font-size:32px;
 color:#ffc83d;
 font-weight:bold;
}
.colors{
 display:grid;
 grid-template-columns:repeat(3,1fr);
 gap:10px;
}
button{
 border:0;
 padding:17px 8px;
 border-radius:12px;
 color:white;
 font-size:16px;
 font-weight:bold;
 cursor:pointer;
}
.red{background:#e84250}
.green{background:#16a66a}
.violet{background:#8054d9}
button:disabled{opacity:.5}
#result{margin-top:18px;font-size:18px}
input{
 width:100%;
 padding:14px;
 border-radius:9px;
 border:0;
 margin:10px 0;
}
</style>
</head>
<body>

<header>BIGDREAM_</header>

<div class="container">

<div class="card">
<h2>Welcome Player!</h2>
<p>Your Virtual Points</p>
<div class="points" id="points">100</div>
</div>

<div class="card">
<h2>🎮 Colour Guess Game</h2>
<p>Guess which colour will appear!</p>

<div class="colors">
<button class="red" onclick="guess('Red')">RED</button>
<button class="green" onclick="guess('Green')">GREEN</button>
<button class="violet" onclick="guess('Violet')">VIOLET</button>
</div>

<div id="result">Choose your colour!</div>
</div>

<div class="card">
<h2>🏆 Your Progress</h2>
<p>Correct guesses: <span id="wins">0</span></p>
<p>Total games: <span id="games">0</span></p>
</div>

<div class="card">
<h2>📞 Support</h2>
<p>Telegram: @Harshit_thakur_01</p>
</div>

</div>

<script>
let points = Number(localStorage.getItem("bd_points")) || 100;
let wins = Number(localStorage.getItem("bd_wins")) || 0;
let games = Number(localStorage.getItem("bd_games")) || 0;

function update(){
 document.getElementById("points").innerText=points;
 document.getElementById("wins").innerText=wins;
 document.getElementById("games").innerText=games;

 localStorage.setItem("bd_points",points);
 localStorage.setItem("bd_wins",wins);
 localStorage.setItem("bd_games",games);
}

function guess(choice){
 const colors=["Red","Green","Violet"];
 const answer=colors[Math.floor(Math.random()*3)];

 games++;

 if(choice===answer){
   wins++;
   points+=10;
   document.getElementById("result").innerHTML=
   "🎉 Correct! +10 virtual points";
 }else{
   document.getElementById("result").innerHTML=
   "The colour was "+answer+". Try again!";
 }

 update();
}

update();
</script>

</body>
</html>
