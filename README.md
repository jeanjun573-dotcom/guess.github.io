💕
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Valentine
</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
body {
font-family: 'Arial', sans-serif;
background: linear-gradient(135deg, #ffafbd, #ffc3a0);
overflow: hidden;
margin: 0;
}
.container {
text-align: center;
background: #fff0f5;
padding: 30px;
border-radius: 20px;
width: 90%;
max-width: 400px;
margin: 100px auto;
box-shadow: 0 10px 20px rgba(0,0,0,0.2);
position: relative;
}
h1 {
margin-bottom: 20px;
color: #d6336c;
}
button {
font-size: 18px;
padding: 12px 22px;
margin: 10px;
border: none;
border-radius: 12px;
cursor: pointer;
transition: all 0.3s ease;
}
#yesBtn {
background-color: #ff4d6d;
color: white;
}
#noBtn {
background-color: #ccc;
position: absolute;
}
#message {
margin-top: 20px;
font-size: 18px;
color: #d6336c;
min-height: 24px;
}
/* Floating hearts */
.heart {
position: fixed;
bottom: -10px;
font-size: 20px;
animation: floatUp 5s linear forwards;
opacity: 0.8;
}
@keyframes floatUp {
from {
transform: translateY(0);
opacity: 1;
}
to {
transform: translateY(-110vh);
opacity: 0;
}
}
</style>
</head>
<body>
<div class="container" id="box">
<h1>Will you be my valentine? </h1>
<button id="yesBtn">YES</button>
<button id="noBtn">NO</button>
<div id="message"></div>
</div>
<!-- Sound -->
<audio id="noSound">
<source src="https://www.myinstants.com/media/sounds/boing.mp3" type="audio/mpeg">
</audio>
<script>
const yesBtn = document.getElementById("yesBtn");
const noBtn = document.getElementById("noBtn");
const message = document.getElementById("message");
const noSound = document.getElementById("noSound");
const box = document.getElementById("box");
let yesSize = 18;
let noClicks = 0;
const noMessages = [
"are you sure?",
"what about ur fingers?",
"heeeeey",
"just say yes",
"pleaseeee"
];
// Initial NO position
moveNo();
function moveNo() {
const boxRect = box.getBoundingClientRect();
const maxX = boxRect.width - 80;
const maxY = boxRect.height - 50;
const x = Math.random() * maxX;
const y = Math.random() * maxY;
noBtn.style.left = x + "px";
noBtn.style.top = y + "px";
}
noBtn.addEventListener("click", () => {
noSound.currentTime = 0;
noSound.play();
yesSize += 10;
yesBtn.style.fontSize = yesSize + "px";
yesBtn.style.padding = (yesSize / 2) + "px";
message.textContent = noMessages[noClicks % noMessages.length];
noClicks++;
moveNo();
spawnHeart();
});
yesBtn.addEventListener("click", () => {
document.body.innerHTML = `
<div class="container">
<h1>u like me so much </h1>
<p style="font-size:22px;">what's the plan </p>
</div>
`;
});
for (let i = 0; i < 30; i++) spawnHeart();
function spawnHeart() 
const heart = document.createElement("div");
heart.className = "heart";
heart.textContent = " ";
heart.style.left = Math.random() *
