<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>For Lang 🌙</title>

<style>
@import url('https://fonts.googleapis.com/css2?family=Great+Vibes&family=Cinzel:wght@500;700&display=swap');

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

body{
    overflow:hidden;
    background:
      radial-gradient(circle at 50% 20%, #40215f 0%, #170d2c 45%, #070611 100%);
    height:100vh;
    font-family:'Cinzel',serif;
    color:white;
}

/* ---------- STARS ---------- */

.stars{
    position:fixed;
    inset:0;
    pointer-events:none;
}

.star{
    position:absolute;
    width:3px;
    height:3px;
    background:#fff;
    border-radius:50%;
    animation:twinkle 2s infinite alternate;
}

@keyframes twinkle{
    from{opacity:.2; transform:scale(.7);}
    to{opacity:1; transform:scale(1.4);}
}

/* ---------- MOON ---------- */

.moon{
    position:absolute;
    top:35px;
    right:45px;
    width:95px;
    height:95px;
    border-radius:50%;
    background:#fff5c7;
    box-shadow:0 0 30px #ffeaa0;
    z-index:2;
}

.moon:after{
    content:"";
    position:absolute;
    top:-10px;
    left:25px;
    width:95px;
    height:95px;
    border-radius:50%;
    background:#24133e;
}

/* ---------- CHINESE LANTERNS ---------- */

.lantern{
    position:absolute;
    top:70px;
    width:35px;
    height:50px;
    background:linear-gradient(90deg,#b51717,#ff4545,#b51717);
    border-radius:45%;
    box-shadow:0 0 18px #ff3838;
    animation:swing 3s ease-in-out infinite;
}

.lantern:before{
    content:"";
    position:absolute;
    top:-10px;
    left:13px;
    width:9px;
    height:10px;
    background:#e5b84c;
}

.lantern:after{
    content:"";
    position:absolute;
    bottom:-25px;
    left:16px;
    width:3px;
    height:25px;
    background:#e5b84c;
}

.l1{left:10%; animation-delay:.2s;}
.l2{left:25%; top:115px; animation-delay:1s;}
.l3{right:22%; top:100px; animation-delay:.5s;}
.l4{right:7%; animation-delay:1.4s;}

@keyframes swing{
    0%,100%{transform:rotate(-5deg);}
    50%{transform:rotate(5deg);}
}

/* ---------- BALLOONS ---------- */

.balloon{
    position:absolute;
    width:45px;
    height:58px;
    border-radius:50%;
    animation:float 5s ease-in-out infinite;
    z-index:4;
}

.balloon:after{
    content:"";
    position:absolute;
    top:56px;
    left:22px;
    height:90px;
    border-left:1px solid rgba(255,255,255,.6);
}

.b1{
    background:#ff477e;
    left:7%;
    bottom:12%;
}

.b2{
    background:#ffd166;
    left:16%;
    bottom:22%;
    animation-delay:1s;
}

.b3{
    background:#5ee7df;
    right:8%;
    bottom:15%;
    animation-delay:2s;
}

.b4{
    background:#a66cff;
    right:17%;
    bottom:27%;
    animation-delay:1.5s;
}

@keyframes float{
    0%,100%{transform:translateY(0) rotate(-3deg);}
    50%{transform:translateY(-35px) rotate(4deg);}
}

/* ---------- MAIN SCENE ---------- */

.scene{
    position:absolute;
    inset:0;
    display:flex;
    justify-content:center;
    align-items:center;
    flex-direction:column;
    transition:1s;
}

.scene.hide{
    opacity:0;
    transform:scale(.7);
    pointer-events:none;
}

/* ---------- CAKE ---------- */

.cake-area{
    text-align:center;
    perspective:900px;
}

.cake{
    position:relative;
    width:280px;
    height:150px;
    transform-style:preserve-3d;
    animation:cakeFloat 3s ease-in-out infinite;
}

@keyframes cakeFloat{
    0%,100%{transform:translateY(0) rotateX(3deg);}
    50%{transform:translateY(-8px) rotateX(-3deg);}
}

.layer{
    position:absolute;
    left:20px;
    width:240px;
    height:55px;
    border-radius:18px;
    background:linear-gradient(#70401f,#351707);
    box-shadow:
        inset 0 8px 8px rgba(255,255,255,.2),
        0 15px 25px rgba(0,0,0,.5);
}

.layer1{
    bottom:0;
}

.layer2{
    bottom:48px;
    left:38px;
    width:204px;
}

.cream{
    position:absolute;
    height:15px;
    background:#fff0d4;
    border-radius:20px;
    width:100%;
    top:-4px;
}

.choco{
    position:absolute;
    width:22px;
    height:30px;
    background:#4a210b;
    border-radius:0 0 12px 12px;
    top:5px;
}

.c1{left:35px;}
.c2{left:90px;}
.c3{left:150px;}
.c4{left:195px;}

.candle{
    position:absolute;
    bottom:103px;
    width:13px;
    height:50px;
    background:linear-gradient(90deg,#fff,#ffd86b,#fff);
    border-radius:5px;
}

.candle1{left:105px;}
.candle2{left:134px;}
.candle3{left:163px;}

.flame{
    position:absolute;
    width:17px;
    height:25px;
    background:orange;
    border-radius:50% 50% 50% 0;
    transform:rotate(-45deg);
    top:-23px;
    left:-2px;
    box-shadow:0 0 15px orange;
    animation:flame .25s infinite alternate;
}

@keyframes flame{
    from{transform:rotate(-45deg) scale(.9);}
    to{transform:rotate(-45deg) scale(1.1);}
}

.cake-title{
    margin-top:25px;
    font-size:20px;
    letter-spacing:2px;
}

.count{
    font-size:42px;
    margin-top:15px;
    color:#ffd76a;
    text-shadow:0 0 15px #ffae00;
}

/* ---------- LETTER ---------- */

.letter-scene{
    position:absolute;
    inset:0;
    display:flex;
    align-items:center;
    justify-content:center;
    opacity:0;
    pointer-events:none;
    transform:scale(.4) rotateY(70deg);
    transition:1.5s;
    perspective:1200px;
}

.letter-scene.show{
    opacity:1;
    pointer-events:auto;
    transform:scale(1) rotateY(0);
}

.scroll{
    width:min(90vw,700px);
    min-height:430px;
    padding:55px 55px;
    position:relative;

    background:
      linear-gradient(90deg,
      #b97b32,
      #f7d98b 8%,
      #fff0b7 50%,
      #f0ce79 92%,
      #a96d2b);

    border:6px solid #9b6125;

    box-shadow:
      0 0 35px rgba(255,193,67,.5),
      inset 0 0 25px rgba(102,48,5,.5);

    transform:rotateX(3deg);

    color:#fff2ad;
}

.scroll:before,
.scroll:after{
    content:"";
    position:absolute;
    left:-20px;
    right:-20px;
    height:35px;
    background:linear-gradient(#b6752c,#f1c36c,#a96524);
    border-radius:50%;
    box-shadow:0 5px 15px rgba(0,0,0,.5);
}

.scroll:before{top:-18px;}
.scroll:after{bottom:-18px;}

.letter{
    position:relative;
    z-index:2;
    font-family:'Great Vibes',cursive;
    font-size:27px;
    line-height:1.55;
    text-align:left;

    color:#b8860b;

    text-shadow:
      0 1px 0 #fff1a8,
      0 0 4px rgba(255,215,100,.4);
}

.letter .title{
    font-size:38px;
    margin-bottom:22px;
    text-align:center;
}

.signature{
    text-align:right;
    margin-top:20px;
    font-size:31px;
}

/* ---------- FIREWORKS ---------- */

.firework{
    position:absolute;
    width:5px;
    height:5px;
    border-radius:50%;
    animation:boom 2s infinite;
    z-index:1;
}

.fw1{left:15%;top:20%;}
.fw2{right:17%;top:30%;animation-delay:.8s;}
.fw3{left:75%;top:15%;animation-delay:1.4s;}

@keyframes boom{
    0%{
        box-shadow:0 0 0 0 white;
        opacity:1;
    }
    50%{
        box-shadow:
        0 -60px 0 #ffd166,
        42px -42px 0 #ff6b6b,
        60px 0 0 #7bed9f,
        42px 42px 0 #70a1ff,
        0 60px 0 #ff9ff3,
        -42px 42px 0 #feca57,
        -60px 0 0 #54a0ff,
        -42px -42px 0 #ff7979;
        opacity:1;
    }
    100%{
        box-shadow:
        0 -90px 0 transparent,
        65px -65px 0 transparent,
        90px 0 0 transparent,
        65px 65px 0 transparent,
        0 90px 0 transparent,
        -65px 65px 0 transparent,
        -90px 0 0 transparent,
        -65px -65px 0 transparent;
        opacity:0;
    }
}

/* ---------- BUTTON ---------- */

.start-btn{
    margin-top:20px;
    padding:13px 28px;
    border:1px solid #ffd76a;
    background:rgba(255,215,106,.12);
    color:#ffd76a;
    border-radius:30px;
    font-size:15px;
    cursor:pointer;
    transition:.3s;
}

.start-btn:hover{
    background:#ffd76a;
    color:#28142f;
    transform:scale(1.08);
}

@media(max-width:600px){
    .scroll{
        min-height:480px;
        padding:45px 30px;
    }

    .letter{
        font-size:21px;
        line-height:1.5;
    }

    .letter .title{
        font-size:31px;
    }

    .signature{
        font-size:25px;
    }

    .cake{
        transform:scale(.8);
    }
}
</style>
</head>

<body>

<!-- STARS -->
<div class="stars">
    <span class="star" style="left:10%;top:15%"></span>
    <span class="star" style="left:30%;top:8%"></span>
    <span class="star" style="left:50%;top:18%"></span>
    <span class="star" style="left:70%;top:10%"></span>
    <span class="star" style="left:85%;top:25%"></span>
    <span class="star" style="left:40%;top:35%"></span>
    <span class="star" style="left:60%;top:42%"></span>
</div>

<!-- MOON -->
<div class="moon"></div>

<!-- LANTERNS -->
<div class="lantern l1"></div>
<div class="lantern l2"></div>
<div class="lantern l3"></div>
<div class="lantern l4"></div>

<!-- BALLOONS -->
<div class="balloon b1"></div>
<div class="balloon b2"></div>
<div class="balloon b3"></div>
<div class="balloon b4"></div>

<!-- FIREWORKS -->
<div class="firework fw1"></div>
<div class="firework fw2"></div>
<div class="firework fw3"></div>


<!-- ================= CAKE SCENE ================= -->

<section class="scene" id="cakeScene">

    <div class="cake-area">

        <div class="cake">

            <div class="layer layer1">
                <div class="cream"></div>

                <div class="choco c1"></div>
                <div class="choco c2"></div>
                <div class="choco c3"></div>
                <div class="choco c4"></div>
            </div>

            <div class="layer layer2">
                <div class="cream"></div>
            </div>

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

        <div class="cake-title">
            A little surprise for you 🌙
        </div>

        <div class="count" id="count">3</div>

        <button class="start-btn" id="startBtn">
            ✨ Start the surprise
        </button>

    </div>

</section>


<!-- ================= LETTER SCENE ================= -->

<section class="letter-scene" id="letterScene">

    <div class="scroll">

        <div class="letter">

            <div class="title">
                For Lang 🌙
            </div>

            Hi, my dear friend Lang, 🌙<br><br>

            We are from two different countries, with different
            religions, cultures, and backgrounds. Yet, somehow,
            by coincidence, we became friends. 🤍<br><br>

            I hope we always remain friends. But if someday,
            for any reason, we stop talking, please remember
            this little crazy friend of yours. 🐈✨

            <div class="signature">
                — Your Little cat 🐈
            </div>

        </div>

    </div>

</section>


<script>

const startBtn = document.getElementById("startBtn");
const count = document.getElementById("count");
const cakeScene = document.getElementById("cakeScene");
const letterScene = document.getElementById("letterScene");

let started = false;

startBtn.addEventListener("click", () => {

    if(started) return;

    started = true;
    startBtn.style.display = "none";

    let number = 3;

    count.innerText = number;

    const timer = setInterval(() => {

        number--;

        if(number > 0){

            count.innerText = number;

        }else{

            clearInterval(timer);

            count.innerText = "✨";

            // Candle flames disappear
            document.querySelectorAll(".flame").forEach(flame=>{
                flame.style.display = "none";
            });

            setTimeout(() => {

                // Cake disappears
                cakeScene.classList.add("hide");

                // Letter comes forward
                setTimeout(() => {
                    letterScene.classList.add("show");
                },700);

            },1200);
        }

    },1000);

});

</script>

</body>
</html>
