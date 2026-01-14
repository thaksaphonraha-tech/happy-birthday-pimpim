# happy-birthday-pimpim
Birthday surprise 💙
<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Happy Birthday 💙</title>

<style>
body {
    margin: 0;
    font-family: "Comic Sans MS", "Sarabun", sans-serif;
    background: linear-gradient(#bfe7ff, #eaf6ff);
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    overflow: hidden;
}

/* หนังสือ */
.book {
    width: 330px;
    height: 500px;
    perspective: 2500px;
    position: relative;
}

.page {
    width: 100%;
    height: 100%;
    position: absolute;
    background: #ffffff;
    border-radius: 18px;
    box-shadow: 0 15px 40px rgba(0,0,0,0.25);
    transform-origin: left;
    transition: transform 1.1s ease-in-out;
    padding: 20px;
    box-sizing: border-box;
    backface-visibility: hidden;
}

/* ลำดับหน้า */
#p1 { z-index: 3; }
#p2 { z-index: 2; }
#p3 { z-index: 1; }

.page.flipped {
    transform: rotateY(-180deg);
}

/* เค้ก */
.cake {
    position: relative;
    width: 180px;
    margin: 50px auto 20px;
}

.layer {
    background: #ffb6d5;
    height: 40px;
    border-radius: 12px;
    margin-bottom: 6px;
}

.layer:nth-child(2) { background: #ffd6e8; }
.layer:nth-child(3) { background: #ffc1dd; }

.plate {
    width: 200px;
    height: 20px;
    background: #a6ddff;
    border-radius: 50%;
    margin: 0 auto;
}

/* เทียน */
.candles {
    display: flex;
    justify-content: center;
    gap: 18px;
    position: absolute;
    top: -34px;
    width: 100%;
}

.candle {
    width: 8px;
    height: 30px;
    background: #7ecbff;
    border-radius: 4px;
    position: relative;
}

.flame {
    width: 10px;
    height: 14px;
    background: radial-gradient(circle, #fff 30%, orange 70%);
    border-radius: 50%;
    position: absolute;
    top: -14px;
    left: -1px;
    animation: flicker 0.25s infinite alternate;
}

@keyframes flicker {
    from { transform: scale(1); }
    to { transform: scale(0.85); }
}

/* ควัน */
.smoke {
    width: 12px;
    height: 12px;
    border-radius: 50%;
    background: rgba(200,200,200,0.7);
    position: absolute;
    top: -6px;
    animation: smoke 2s infinite;
}

@keyframes smoke {
    from { transform: translateY(0) scale(1); opacity: 1; }
    to { transform: translateY(-30px) scale(1.6); opacity: 0; }
}

/* ข้อความ */
.note {
    margin-top: 20px;
    font-size: 15px;
    line-height: 1.6;
    text-align: center;
}

/* พลุ */
.fireworks {
    position: absolute;
    inset: 0;
    background:
      radial-gradient(circle, #fff 2px, transparent 3px),
      radial-gradient(circle, #ffb6c1 2px, transparent 3px),
      radial-gradient(circle, #87cefa 2px, transparent 3px);
    background-size: 70px 70px;
    animation: boom 1.8s infinite;
    opacity: 0.5;
}

@keyframes boom {
    from { background-position: 0 0; }
    to { background-position: 70px 70px; }
}

/* สติ๊กเกอร์ */
.sticker {
    position: absolute;
    font-size: 28px;
}
.s1 { top: 12px; left: 12px; }
.s2 { top: 12px; right: 12px; }
.s3 { bottom: 12px; left: 12px; }
.s4 { bottom: 12px; right: 12px; }

.tap {
    position: absolute;
    bottom: 10px;
    width: 100%;
    text-align: center;
    font-size: 12px;
    opacity: 0.6;
}
</style>
</head>

<body>

<audio id="blow">
  <source src="https://cdn.pixabay.com/audio/2022/03/15/audio_2a91b6b3d4.mp3" type="audio/mpeg">
</audio>

<div class="book" onclick="nextPage()">

    <!-- หน้า 1 -->
    <div class="page" id="p1">
        <div class="sticker s1">🧸</div>
        <div class="sticker s2">💙</div>
        <div class="sticker s3">🐰</div>
        <div class="sticker s4">⭐</div>

        <div class="cake">
            <div class="layer"></div>
            <div class="layer"></div>
            <div class="layer"></div>
            <div class="plate"></div>
        </div>

        <div class="note">
            สุขสันต์วันเกิดนะครับ พี่พิม 💙<br><br>
            ขอให้หลังจากนี้มีแต่สิ่งดีๆ  
            มีความสุขมากๆ นะครับ
        </div>
        <div class="tap">👆 แตะเพื่อเปิดหน้า</div>
    </div>

    <!-- หน้า 2 -->
    <div class="page" id="p2">
        <div class="cake">
            <div class="candles">
                <div class="candle"><div class="flame"></div></div>
                <div class="candle"><div class="flame"></div></div>
                <div class="candle"><div class="flame"></div></div>
            </div>
            <div class="layer"></div>
            <div class="layer"></div>
            <div class="layer"></div>
            <div class="plate"></div>
        </div>

        <div class="note">
            เตรียมเป่านะครับ 🎂✨<br><br>
            1 … 2 … 3 💨
        </div>
        <div class="tap">👆 แตะอีกครั้ง</div>
    </div>

    <!-- หน้า 3 -->
    <div class="page" id="p3">
        <div class="fireworks"></div>

        <div class="cake">
            <div class="candles">
                <div class="candle"><div class="smoke"></div></div>
                <div class="candle"><div class="smoke"></div></div>
                <div class="candle"><div class="smoke"></div></div>
            </div>
            <div class="layer"></div>
            <div class="layer"></div>
            <div class="layer"></div>
            <div class="plate"></div>
        </div>

        <div class="note" style="font-size:20px;">
            🎉 HAPPY BIRTHDAY TO YOU 🎉<br>
            💐🎂💙
        </div>
    </div>

</div>

<script>
let page = 0;
function nextPage() {
    page++;

    if (page === 1) {
        document.getElementById("p1").classList.add("flipped");
    }

    if (page === 2) {
        document.getElementById("p2").classList.add("flipped");
        document.getElementById("blow").play();
    }

    if (page === 3) {
        document.getElementById("p3").classList.add("flipped");
    }
}
</script>

</body>
</html>
