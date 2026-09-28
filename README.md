<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For Lang 🌙</title>

<style>
*{
  box-sizing:border-box;
}

html,body{
  margin:0;
  width:100%;
  height:100%;
  overflow:hidden;
  font-family:Georgia,serif;
}

body{
  background:#090615;
  color:white;
}

/* ================= CANVAS FIREWORKS ================= */

#fireworks{
  position:fixed;
  inset:0;
  width:100%;
  height:100%;
  pointer-events:none;
  z-index:50;
}

/* ================= COMMON SCENE ================= */

.scene{
  position:absolute;
  inset:0;
  display:flex;
  justify-content:center;
  align-items:center;
  flex-direction:column;
  text-align:center;
  transition:opacity 1s ease;
}

.hidden{
  opacity:0;
  pointer-events:none;
}

/* ================= SCENE 1 ================= */

#scene1{
  background:
    radial-gradient(circle at 50% 25%,#54255f 0%,#211032 42%,#080513 100%);
}

.stars{
  position:absolute;
  inset:0;
  background-image:
    radial-gradient(#fff 1px,transparent 1px),
    radial-gradient(#ffe9b0 1px,transparent 1px);
  background-size:65px 65px,95px 95px;
  opacity:.55;
}

.moon{
  position:absolute;
  top:8%;
  right:10%;
  width:125px;
  height:125px;
  border-radius:50%;
  background:#fff0b2;
  box-shadow:
    0 0 25px #ffe89a,
    0 0 70px #ffd76b;
}

.lantern{
  position:absolute;
  top:7%;
  font-size:52px;
  animation:swing 3s ease-in-out infinite;
}

.lantern.left{
  left:7%;
}

.lantern.right{
  right:7%;
  animation-delay:1.2s;
}

@keyframes swing{
  0%,100%{transform:rotate(-5deg)}
  50%{transform:rotate(5deg)}
}

.intro{
  position:relative;
  z-index:5;
}

.intro h1{
  font-size:clamp(42px,9vw,75px);
  margin:0;
  color:#ffe6a1;
  text-shadow:
    0 0 15px #ffbd42,
    0 0 35px #ff7b00;
}

.intro p{
  font-size:20px;
  color:#ffdca5;
}

.start{
  margin-top:25px;
  padding:15px 30px;
  border:0;
  border-radius:30px;
  background:linear-gradient(45deg,#ff9e2c,#ffe29a);
  color:#351300;
  font-weight:bold;
  font-size:18px;
  cursor:pointer;
  box-shadow:0 0 25px #ffb52e;
}

/* ================= CAKE SCENE ================= */

#scene2{
  background:
    radial-gradient(circle at center,#3b164c,#10071d 75%);
}

.cakeTitle{
  position:absolute;
  top:8%;
  font-size:25px;
  color:#ffe6a6;
}

.cake{
  position:relative;
  width:270px;
  height:190px;
  margin-top:30px;
}

/* cake layers */

.layer{
  position:absolute;
  left:0;
  width:270px;
  height:70px;
  border-radius:18px 18px 12px 12px;
  background:linear-gradient(#75402b,#3d1d18);
  box-shadow:0 10px 0 #28100f;
}

.layer.top{
  top:45px;
}

.layer.middle{
  top:100px;
  transform:scale(.9);
}

.icing{
  position:absolute;
  top:35px;
  left:0;
  width:270px;
  height:35px;
  border-radius:50%;
  background:#5a2a20;
  box-shadow:inset 0 -8px #2b1110;
}

.cream{
  position:absolute;
  top:48px;
  left:15px;
  width:240px;
  height:18px;
  border-radius:50%;
  background:#f4d6bd;
}

.cherry{
  position:absolute;
  top:18px;
  left:123px;
  font-size:30px;
}

/* candles */

.candle{
  position:absolute;
  top:-30px;
  width:15px;
  height:58px;
  border-radius:4px;
  background:repeating-linear-gradient(
    45deg,
    #fff 0 7px,
    #e64b64 7px 14px
  );
}

.c1{left:70px}
.c2{left:128px}
.c3{left:186px}

.flame{
  position:absolute;
  top:-23px;
  left:1px;
  width:13px;
  height:22px;
  background:#ffd447;
  border-radius:50% 50% 45% 45%;
  box-shadow:0 0 15px #ff9d00;
  animation:flame .25s infinite alternate;
}

@keyframes flame{
  from{transform:scale(.9) rotate(-3deg)}
  to{transform:scale(1.1) rotate(3deg)}
}

.candle.off .flame{
  display:none;
}

.count{
  margin-top:25px;
  font-size:28px;
  color:#ffe6a6;
  min-height:40px;
}

.instruction{
  color:#dcbfd8;
  font-size:15px;
  margin-top:8px;
}

/* ================= PAPER ================= */

#scene3{
  background:
    radial-gradient(circle at 50% 35%,#45205b,#110719 75%);
}

.paper{
  width:min(88vw,620px);
  min-height:100px;
  max-height:75vh;
  background:#f5dfad;
  color:#42273b;
  border-radius:8px;
  box-shadow:
    0 15px 45px rgba(0,0,0,.6),
    0 0 30px rgba(255,215,130,.25);
  padding:35px;
  transform:scaleY(.05);
  transform-origin:top;
  opacity:0;
  overflow:auto;
  transition:
    transform 1.8s cubic-bezier(.2,.8,.2,1),
    opacity .5s;
}

.paper.open{
  transform:scaleY(1);
  opacity:1;
}

.paper h2{
  color:#87394d;
  margin-top:0;
}

.letter{
  font-size:17px;
  line-height:1.8;
}

.nextBtn{
  margin-top:25px;
  padding:11px 25px;
  border:0;
  border-radius:22px;
  background:#87394d;
  color:white;
  cursor:pointer;
}

/* ================= ROSE GARDEN ================= */

#scene4{
  background:
    linear-gradient(
      to bottom,
      #080717 0%,
      #17102d 55%,
      #101d16 56%,
      #07120b 100%
    );
}

.gardenMoon{
  position:absolute;
  top:8%;
  width:115px;
  height:115px;
  border-radius:50%;
  background:#fff0b5;
  box-shadow:0 0 50px #ffd970;
}

.gardenTitle{
  position:absolute;
  top:5%;
  font-size:25px;
  color:#ffe3a0;
  z-index:4;
}

.ground{
  position:absolute;
  bottom:0;
  width:100%;
  height:45%;
  background:
    radial-gradient(ellipse at center,#17371e,#061009 70%);
}

/* roses */

.rose{
  position:absolute;
  bottom:25%;
  font-size:38px;
  animation:sway 3s ease-in-out infinite;
}

.r1{left:8%;animation-delay:.2s}
.r2{left:22%;animation-delay:1s}
.r3{right:22%;animation-delay:.5s}
.r4{right:8%;animation-delay:1.4s}

@keyframes sway{
  0%,100%{transform:rotate(-4deg)}
  50%{transform:rotate(4deg)}
}

/* rabbit */

.finalRabbit{
  position:absolute;
  bottom:18%;
  font-size:100px;
  z-index:5;
  animation:rabbitHop 2.5s ease-in-out infinite;
}

@keyframes rabbitHop{
  0%,100%{transform:translateY(0)}
  50%{transform:translateY(-15px)}
}

.finalText{
  position:absolute;
  bottom:7%;
  z-index:6;
  font-size:23px;
  color:#ffe6a8;
}

/* ================= MOBILE ================= */

@media(max-width:600px){

  .moon{
    width:90px;
    height:90px;
  }

  .lantern{
    font-size:38px;
  }

  .intro h1{
    font-size:43px;
  }

  .cake{
    transform:scale(.85);
  }

  .paper{
    padding:25px 20px;
  }

  .letter{
    font-size:15px;
  }
}
</style>
</head>

<body>

<canvas id="fireworks"></canvas>

<!-- ================= INTRO ================= -->

<section id="scene1" class="scene">

  <div class="stars"></div>

  <div class="moon"></div>

  <div class="lantern left">🏮</div>
  <div class="lantern right">🏮</div>

  <div class="intro">
    <h1>Happy Birthday Lang 🎂</h1>
    <p>Under a beautiful Mid-Autumn moon 🌙</p>

    <button class="start" onclick="startGame()">
      ✨ Begin Your Surprise
    </button>
  </div>

</section>


<!-- ================= CAKE ================= -->

<section id="scene2" class="scene hidden">

  <div class="cakeTitle">
    A little birthday cake for you 🍫🎂
  </div>

  <div class="cake">

    <div class="layer top"></div>
    <div class="layer middle"></div>

    <div class="icing"></div>
    <div class="cream"></div>
    <div class="cherry">🍒</div>

    <div class="candle c1" id="c1">
      <div class="flame"></div>
    </div>

    <div class="candle c2" id="c2">
      <div class="flame"></div>
    </div>

    <div class="candle c3" id="c3">
      <div class="flame"></div>
    </div>

  </div>

  <div class="count" id="count">
    Get ready...
  </div>

  <div class="instruction">
    Tap the screen to blow out the candles 🎂
  </div>

</section>


<!-- ================= LETTER ================= -->

<section id="scene3" class="scene hidden">

  <div class="paper" id="paper">

    <h2>💌 A Little Letter</h2>

    <div class="letter">

      <p>Hi, my dear friend Lang, 🌙</p>

      <p>
        We are from two different countries, with different religions,
        cultures, and backgrounds. Yet, somehow, by coincidence,
        we became friends. 🤍
      </p>

      <p>
        I hope we always remain friends. But if someday, for any reason,
        we stop talking, please remember this little crazy friend of yours. 🐇✨
      </p>

      <p>
        — Your Little Rabbit 🌙🥮
      </p>

    </div>

    <button class="nextBtn" onclick="goGarden()">
      🌹 One More Surprise
    </button>

  </div>

</section>


<!-- ================= ROSE GARDEN ================= -->

<section id="scene4" class="scene hidden">

  <div class="gardenMoon"></div>

  <div class="gardenTitle">
    A little garden for Lang 🌙
  </div>

  <div class="ground"></div>

  <div class="rose r1">🌹</div>
  <div class="rose r2">🌹</div>
  <div class="rose r3">🌹</div>
  <div class="rose r4">🌹</div>

  <div class="finalRabbit">
    🐇
  </div>

  <div class="finalText">
    Happy Birthday, Lang 🎂✨<br>
    — From your Little Rabbit 🐇
  </div>

</section>


<script>

/* =================================================
   REAL PARTICLE FIREWORKS
================================================= */

const canvas = document.getElementById("fireworks");
const ctx = canvas.getContext("2d");

let particles = [];
let rockets = [];

function resizeCanvas(){

  canvas.width = window.innerWidth;
  canvas.height = window.innerHeight;

}

resizeCanvas();
window.addEventListener("resize",resizeCanvas);


/* Rocket */

function launchRocket(){

  const rocket = {
    x:Math.random()*canvas.width,
    y:canvas.height+10,
    target:Math.random()*canvas.height*.45+80,
    speed:8,
    hue:Math.random()*360
  };

  rockets.push(rocket);

}


/* Explosion */

function explode(x,y,hue){

  const amount=90;

  for(let i=0;i<amount;i++){

    const angle=Math.random()*Math.PI*2;
    const speed=Math.random()*6+2;

    particles.push({

      x:x,
      y:y,

      vx:Math.cos(angle)*speed,
      vy:Math.sin(angle)*speed,

      life:1,
      decay:Math.random()*.018+.012,

      hue:hue
    });

  }

}


/* Animation */

function animateFireworks(){

  ctx.fillStyle="rgba(5,3,15,.20)";
  ctx.fillRect(0,0,canvas.width,canvas.height);

  /* rockets */

  rockets.forEach((r,index)=>{

    r.y-=r.speed;

    ctx.beginPath();
    ctx.arc(r.x,r.y,2,0,Math.PI*2);
    ctx.fillStyle=`hsl(${r.hue},100%,70%)`;
    ctx.fill();

    if(r.y<=r.target){

      explode(r.x,r.y,r.hue);

      rockets.splice(index,1);

    }

  });


  /* particles */

  particles.forEach((p,index)=>{

    p.x+=p.vx;
    p.y+=p.vy;

    p.vy+=.035;
    p.vx*=.985;

    p.life-=p.decay;

    ctx.beginPath();

    ctx.arc(
      p.x,
      p.y,
      2,
      0,
      Math.PI*2
    );

    ctx.fillStyle=
      `hsla(${p.hue},100%,65%,${p.life})`;

    ctx.fill();

    if(p.life<=0){

      particles.splice(index,1);

    }

  });

  requestAnimationFrame(animateFireworks);

}

animateFireworks();


function fireworksShow(){

  launchRocket();

  setTimeout(launchRocket,350);
  setTimeout(launchRocket,700);
  setTimeout(launchRocket,1050);
  setTimeout(launchRocket,1400);
  setTimeout(launchRocket,1800);

}


/* =================================================
   SCENE CONTROL
================================================= */

function showScene(id){

  document.querySelectorAll(".scene")
    .forEach(scene=>{
      scene.classList.add("hidden");
    });

  document.getElementById(id)
    .classList.remove("hidden");

}


/* =================================================
   START
================================================= */

function startGame(){

  showScene("scene2");

  fireworksShow();

  setTimeout(()=>{
    document.getElementById("count").innerText="1...";
  },700);

  setTimeout(()=>{
    document.getElementById("count").innerText="2...";
  },1700);

  setTimeout(()=>{
    document.getElementById("count").innerText="3...";
  },2700);

}


/* =================================================
   CANDLE GAME
================================================= */

let candleNumber=0;

document.getElementById("scene2")
.addEventListener("click",function(){

  if(candleNumber>=3) return;

  candleNumber++;

  document
    .getElementById("c"+candleNumber)
    .classList.add("off");

  if(candleNumber===1){

    document.getElementById("count")
      .innerText="One candle gone! ✨";

  }

  if(candleNumber===2){

    document.getElementById("count")
      .innerText="Two! Keep going! 🎂";

  }

  if(candleNumber===3){

    document.getElementById("count")
      .innerText="Happy Birthday, Lang! 🎉";

    fireworksShow();

    setTimeout(openLetter,1800);

  }

});


/* =================================================
   OPEN LETTER
================================================= */

function openLetter(){

  showScene("scene3");

  setTimeout(()=>{

    document
      .getElementById("paper")
      .classList.add("open");

  },300);

}


/* =================================================
   ROSE GARDEN
================================================= */

function goGarden(){

  fireworksShow();

  showScene("scene4");

}

</script>

</body>
</html>
