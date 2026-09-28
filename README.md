<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>A Little Surprise for Lang</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@500;600&family=Dancing+Script:wght@500;600;700&display=swap');

*{
    box-sizing:border-box;
    margin:0;
    padding:0;
}

body{
    overflow:hidden;
    background:
        radial-gradient(circle at 50% 20%, #39204e 0%, #160d28 45%, #080611 100%);
    height:100vh;
    color:white;
    font-family:'Cinzel',serif;
}

/* ---------- NIGHT SKY ---------- */

.sky{
    position:fixed;
    inset:0;
    overflow:hidden;
}

.moon{
    position:absolute;
    top:7%;
    right:9%;
    width:105px;
    height:105px;
    border-radius:50%;
    background:linear-gradient(145deg,#fff9d8,#e8c96a);
    box-shadow:
        0 0 25px #ffe89a,
        0 0 70px rgba(255,220,120,.45);
}

.moon:after{
    content:"";
    position:absolute;
    width:105px;
    height:105px;
    border-radius:50%;
    background:#120a20;
    left:30px;
    top:-10px;
}

.star{
    position:absolute;
    width:3px;
    height:3px;
    background:white;
    border-radius:50%;
    box-shadow:0 0 8px white;
    animation:twinkle 2s infinite alternate;
}

@keyframes twinkle{
    from{opacity:.25;transform:scale(.6)}
    to{opacity:1;transform:scale(1.5)}
}

/* ---------- CHINESE LANTERNS ---------- */

.lantern{
    position:absolute;
    top:-10px;
    width:42px;
    height:58px;
    background:linear-gradient(90deg,#7c0808,#ef2424,#8b0808);
    border-radius:50% 50% 45% 45%;
    box-shadow:0 0 22px rgba(255,65,20,.7);
    animation:swing 3s ease-in-out infinite;
}

.lantern:before{
    content:"";
    position:absolute;
    top:-9px;
    left:12px;
    width:18px;
    height:10px;
    background:#e5a928;
}

.lantern:after{
    content:"";
    position:absolute;
    bottom:-19px;
    left:18px;
    width:6px;
    height:22px;
    background:#e5a928;
}

.l1{left:7%;animation-delay:.3s}
.l2{left:23%;top:35px;animation-delay:1s}
.l3{right:24%;top:25px;animation-delay:.6s}
.l4{right:7%;animation-delay:1.5s}

@keyframes swing{
    0%,100%{transform:rotate(-4deg)}
    50%{transform:rotate(5deg)}
}

/* ---------- BALLOONS ---------- */

.balloon{
    position:absolute;
    width:52px;
    height:65px;
    border-radius:50% 50% 45% 45%;
    animation:float 5s ease-in-out infinite;
}

.balloon:after{
    content:"";
    position:absolute;
    top:62px;
    left:25px;
    width:1px;
    height:110px;
    background:rgba(255,255,255,.45);
}

.b1{left:5%;bottom:-80px;background:#e84d75;animation-delay:0s}
.b2{right:5%;bottom:-100px;background:#5a8df2;animation-delay:1.3s}
.b3{left:17%;bottom:-120px;background:#f0bd45;animation-delay:2.1s}
.b4{right:18%;bottom:-130px;background:#a65de8;animation-delay:3s}

@keyframes float{
    0%{transform:translateY(0) rotate(-4deg)}
    50%{transform:translateY(-45px) rotate(5deg)}
    100%{transform:translateY(0) rotate(-4deg)}
}

/* ---------- MAIN STAGE ---------- */

.stage{
    position:absolute;
    inset:0;
    display:flex;
    justify-content:center;
    align-items:center;
    perspective:1200px;
}

.scene{
    position:relative;
    width:100%;
    height:100%;
}

/* ---------- CAKE ---------- */

.cake-area{
    position:absolute;
    left:50%;
    top:50%;
    transform:translate(-50%,-45%);
    text-align:center;
    transition:1s;
}

.cake{
    position:relative;
    width:250px;
    height:190px;
    margin:auto;
    transform-style:preserve-3d;
    animation:cakeFloat 3s ease-in-out infinite;
}

@keyframes cakeFloat{
    0%,100%{transform:translateY(0) rotateY(-5deg)}
    50%{transform:translateY(-10px) rotateY(5deg)}
}

.layer{
    position:absolute;
    left:25px;
    width:200px;
    height:55px;
    border-radius:50%;
    background:
        linear-gradient(180deg,#743a1e,#3c180d);
    box-shadow:
        inset 0 -12px 15px rgba(0,0,0,.35),
        0 12px 15px rgba(0,0,0,.35);
}

.layer:before{
    content:"";
    position:absolute;
    left:0;
    top:-12px;
    width:200px;
    height:28px;
    border-radius:50%;
    background:#6e3218;
    box-shadow:inset 0 5px 8px rgba(255,255,255,.12);
}

.layer:after{
    content:"";
    position:absolute;
    top:8px;
    left:25px;
    width:150px;
    height:8px;
    border-radius:50%;
    background:#f1d0a0;
    opacity:.75;
}

.bottom{top:105px}
.middle{top:65px;transform:scale(.9)}
.top{top:30px;transform:scale(.78)}

.choco{
    position:absolute;
    width:18px;
    height:18px;
    border-radius:50%;
    background:#d79b51;
    box-shadow:inset -3px -3px 5px #713a16;
}

.c1{left:55px;top:38px}
.c2{left:105px;top:35px}
.c3{left:145px;top:42px}
.c4{left:80px;top:80px}
.c5{left:125px;top:78px}

/* candles */

.candle{
    position:absolute;
    width:12px;
    height:48px;
    top:-15px;
    background:repeating-linear-gradient(
        45deg,
        #f8e4a0 0px,
        #f8e4a0 7px,
        #d68a45 7px,
        #d68a45 12px
    );
    border-radius:5px;
    z-index:10;
}

.candle1{left:78px}
.candle2{left:119px}
.candle3{left:160px}

.flame{
    position:absolute;
    width:16px;
    height:24px;
    top:-24px;
    left:-2px;
    border-radius:50% 50% 50% 10%;
    background:#ffd34e;
    transform:rotate(45deg);
    box-shadow:0 0 15px #ff9e21;
    animation:flicker .25s infinite alternate;
}

@keyframes flicker{
    from{transform:rotate(42deg) scale(.9)}
    to{transform:rotate(48deg) scale(1.08)}
}

.countdown{
    margin-top:20px;
    font-size:42px;
    color:#ffe49a;
    text-shadow:0 0 20px #e9a93b;
    font-weight:bold;
}

/* ---------- FIREWORKS ---------- */

.firework{
    position:absolute;
    width:5px;
    height:5px;
    border-radius:50%;
    background:#ffd76b;
    box-shadow:
        0 -55px 0 #ffcb5b,
        39px -39px 0 #ff7b7b,
        55px 0 0 #fff0a6,
        39px 39px 0 #ff7b7b,
        0 55px 0 #ffcb5b,
        -39px 39px 0 #8bd3ff,
        -55px 0 0 #fff0a6,
        -39px -39px 0 #8bd3ff;
    animation:boom 2s infinite;
}

.fw1{left:18%;top:28%}
.fw2{right:20%;top:40%;animation-delay:.7s}
.fw3{right:8%;top:18%;animation-delay:1.2s}

@keyframes boom{
    0%,100%{transform:scale(.2);opacity:.2}
    50%{transform:scale(1);opacity:1}
}

/* ---------- PARCHMENT ---------- */

.letter-scene{
    position:absolute;
    inset:0;
    display:flex;
    justify-content:center;
    align-items:center;
    opacity:0;
    pointer-events:none;
    transform:scale(.6) rotateX(45deg);
    transition:1.5s;
}

.letter-scene.show{
    opacity:1;
    transform:scale(1) rotateX(0);
    pointer-events:auto;
}

.parchment{
    position:relative;
    width:min(88%,650px);
    min-height:520px;
    padding:55px 45px;
    background:
        radial-gradient(circle at 20% 20%,rgba(255,255,255,.4),transparent 25%),
        linear-gradient(135deg,#f6e1a7,#cfa76b,#f0d596);
    color:#4b2815;
    box-shadow:
        0 20px 60px rgba(0,0,0,.65),
        inset 0 0 35px rgba(100,55,10,.35);
    border-radius:10px;
    transform-style:preserve-3d;
}

.parchment:before,
.parchment:after{
    content:"";
    position:absolute;
    width:35px;
    height:100%;
    top:0;
    background:rgba(93,49,20,.18);
    filter:blur(8px);
}

.parchment:before{left:0}
.parchment:after{right:0}

.scroll-top,
.scroll-bottom{
    position:absolute;
    left:-12px;
    width:calc(100% + 24px);
    height:28px;
    border-radius:50%;
    background:linear-gradient(#9c6736,#e4bd78,#805026);
    box-shadow:0 5px 10px rgba(0,0,0,.35);
}

.scroll-top{top:-12px}
.scroll-bottom{bottom:-12px}

.letter{
    position:relative;
    z-index:2;
    font-family:'Dancing Script',cursive;
    font-size:24px;
    line-height:1.55;
    font-weight:600;
    color:#6d3516;
    text-shadow:0 1px 1px rgba(255,255,255,.35);
}

.letter h1{
    text-align:center;
    font-size:37px;
    color:#b57916;
    text-shadow:
        0 1px #fff2b0,
        0 0 12px rgba(190,130,25,.45);
    margin-bottom:22px;
}

.signature{
    text-align:right;
    margin-top:25px;
    font-size:30px;
    color:#a96d15;
}

/* ---------- BUTTON ---------- */

.start{
    position:absolute;
    bottom:8%;
    left:50%;
    transform:translateX(-50%);
    padding:13px 30px;
    border:none;
    border-radius:30px;
    background:linear-gradient(135deg,#d9a441,#fff0a1,#b77b19);
    color:#3d2108;
    font-family:'Cinzel',serif;
    font-weight:bold;
    box-shadow:0 0 25px rgba(240,190,75,.6);
    cursor:pointer;
    z-index:50;
}

.start:active{
    transform:translateX(-50%) scale(.95);
}

/* hide environment after cake */

.fade{
    opacity:0;
    transition:1s;
}

@media(max-width:600px){
    .moon{
        width:75px;
        height:75px;
    }

    .moon:after{
        width:75px;
        height:75px;
    }

    .cake{
        transform:scale(.82);
    }

    .letter{
        font-size:19px;
    }

    .letter h1{
        font-size:29px;
    }

    .parchment{
        min-height:470px;
        padding:45px 25px;
    }
}
</style>
</head>

<body>

<div class="sky">

    <div class="moon"></div>

    <div class="lantern l1"></div>
    <div class="lantern l2"></div>
    <div class="lantern l3"></div>
    <div class="lantern l4"></div>

    <div class="balloon b1"></div>
    <div class="balloon b2"></div>
    <div class="balloon b3"></div>
    <div class="balloon b4"></div>

    <div class="firework fw1"></div>
    <div class="firework fw2"></div>
    <div class="firework fw3"></div>

</div>

<div class="stage">

    <!-- CAKE -->
    <div class="cake-area" id="cakeArea">

        <div class="cake">

            <div class="layer bottom"></div>
            <div class="layer middle"></div>
            <div class="layer top"></div>

            <div class="choco c1"></div>
            <div class="choco c2"></div>
            <div class="choco c3"></div>
            <div class="choco c4"></div>
            <div class="choco c5"></div>

            <div class="candle candle1">
                <div class="flame"></div>
            </div>

            <div class="candle candle2">
                <div class="flame"></div>
            </div>

            <div class="candle candle3">
                <div class="flame"></div>
            </div>

        </div>

        <div class="countdown" id="countdown">3</div>

    </div>


    <!-- LETTER -->
    <div class="letter-scene" id="letterScene">

        <div class="parchment">

            <div class="scroll-top"></div>
            <div class="scroll-bottom"></div>

            <div class="letter">

                <h1>For My Dear Friend 🌙</h1>

                Hi, my dear friend Lang, 🌙<br><br>

                We are from two different countries, with different
                religions, cultures, and backgrounds. Yet, somehow,
                by coincidence, we became friends. 🤍<br><br>

                I hope we always remain friends. But if someday,
                for any reason, we stop talking, please remember
                this little crazy friend of yours. 🐈✨

                <div class="signature">
                    — Ria 🐈
                </div>

            </div>

        </div>

    </div>

</div>

<button class="start" id="startBtn">
    ✨ Open Your Surprise ✨
</button>


<script>

const startBtn = document.getElementById("startBtn");
const countdown = document.getElementById("countdown");
const cakeArea = document.getElementById("cakeArea");
const letterScene = document.getElementById("letterScene");

const flames = document.querySelectorAll(".flame");

startBtn.addEventListener("click",()=>{

    startBtn.style.display="none";

    let number = 3;
    countdown.innerHTML = number;

    const timer = setInterval(()=>{

        number--;

        if(number > 0){
            countdown.innerHTML = number;
        }

        if(number === 0){

            countdown.innerHTML = "✨";

            flames.forEach(flame=>{
                flame.style.transition="1s";
                flame.style.opacity="0";
                flame.style.transform="scale(0)";
            });

            setTimeout(()=>{

                cakeArea.classList.add("fade");

                setTimeout(()=>{

                    cakeArea.style.display="none";

                    letterScene.classList.add("show");

                },900);

            },1200);

            clearInterval(timer);
        }

    },1000);

});


/* stars */

for(let i=0;i<55;i++){

    const star=document.createElement("div");

    star.className="star";

    star.style.left=Math.random()*100+"%";
    star.style.top=Math.random()*75+"%";
    star.style.animationDelay=(Math.random()*3)+"s";

    document.querySelector(".sky").appendChild(star);
}

</script>

</body>
</html>
