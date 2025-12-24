<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<title>Rafael</title>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Verdana, Arial, sans-serif;
}

body {
  width: 100vw;
  height: 100vh;
  background: linear-gradient(#0a2a66, #0f3c88);
  overflow: hidden;
  position: relative;
  color: #9fc9ff;
}

/* CAMADA DE TEXTO DILUÍDO */
.noise-text {
  position: absolute;
  inset: 0;
  padding: 30px;
  font-size: 9px;
  line-height: 1.35;
  opacity: 0.35;
  white-space: pre-wrap;
  pointer-events: none;
}

/* POEMA CENTRAL (ÍNTEGRO) */
.center-poem {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 420px;
  transform: translate(-50%, -50%);
  font-size: 13px;
  line-height: 1.5;
  color: #d6e7ff;
  background: rgba(10, 40, 90, 0.55);
  padding: 18px;
  border-radius: 10px;
  box-shadow: 0 0 18px rgba(0,0,0,0.4);
}

/* BOTÃO DVD */
#dvd {
  position: absolute;
  padding: 16px 26px;
  background: red;
  color: #0044ff;
  font-size: 22px;
  font-weight: bold;
  border-radius: 6px;
  cursor: pointer;
  box-shadow: 0 0 14px rgba(0,0,0,0.5);
  user-select: none;
}

/* ESPIRAL */
.spiral {
  position: absolute;
  bottom: 30px;
  right: 30px;
  width: 160px;
  height: 160px;
  border-radius: 50%;
  border: 2px dashed rgba(180,210,255,0.6);
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  font-size: 12px;
  color: #bcdcff;
  background: radial-gradient(circle at center,
    rgba(200,220,255,0.25),
    rgba(0,0,0,0));
}

/* FRUTIGER AERO SUAVE */
.spiral::before {
  content: "";
  position: absolute;
  inset: 10px;
  border-radius: 50%;
  border: 1px dotted rgba(255,255,255,0.3);
}

</style>
</head>

<body>

<!-- TEXTO DE FUNDO MISTURADO -->
<div class="noise-text">
Olho a árvore e indago está aí para quê o mundo é sem sentido quanto mais vasto é
Encore des mots toujours des mots les mêmes mots
If I'm butter then he's a hot knife dancing bird of paradise
Paroles et paroles et paroles
Caramels bonbons et chocolats
Je te regarde comme pour la première fois
Tu es le vent et le parfum des roses
Des mots fragiles qui sonnent faux
CinemaScope screen showing the dancing bird
Moi les mots tendres enrobés de douceur
Encore des mots toujours des mots
If I'm butter if I'm butter
Les souvenirs se fanent
Paroles que tu sèmes au vent
</div>

<!-- POEMA CENTRAL ÍNTEGRO -->
<div class="center-poem">
Lembra-te que morreremos, 
Meu ódio-amor.  
De carne e miséria,  
Esta casa breve de matéria,  
Corpo-campo de luta e de suor.  

Lembra-te do anônimo da Terra,  
Que meditanto a sós com seus botões,  
Gravou no relógio das quimeras:  
"É mais tarde do que supões".  

Por isso  
Mata-me apenas em sonhos.  
Podes dormir em fúria pela eternidade, 
Mas acordado, ama. 
Porque ao meu lado  
Tudo se faz tarde: amor, gozo, ventura.
</div>

<!-- BOTÃO DVD -->
<div id="dvd">Rafael</div>

<!-- ESPIRAL MATEMÁTICA -->
<div class="spiral">
limₙ→∞<br>
(eu te amo)ⁿ<br>
= você
</div>

<script>
const dvd = document.getElementById("dvd");

let x = 120;
let y = 80;
let dx = 2;
let dy = 2;

let clicked = false;

function animate() {
  const w = window.innerWidth;
  const h = window.innerHeight;
  const rect = dvd.getBoundingClientRect();

  x += dx;
  y += dy;

  if (x <= 0 || x + rect.width >= w) dx *= -1;
  if (y <= 0 || y + rect.height >= h) dy *= -1;

  dvd.style.left = x + "px";
  dvd.style.top = y + "px";

  requestAnimationFrame(animate);
}

dvd.addEventListener("click", () => {
  if (!clicked) {
    dvd.textContent = "eu te amoo pra valeeeer!!!";
    clicked = true;
  }
});

animate();
</script>

</body>
</html>
