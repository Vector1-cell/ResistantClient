<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Resistant Client</title>

<style>
body {
    margin: 0;
    font-family: Arial, sans-serif;
    overflow-x: hidden;
    color: white;
    background: #000;
}

/* 🌊 CANVAS BACKGROUND */
canvas {
    position: fixed;
    top: 0;
    left: 0;
    z-index: -1;
}

/* MAIN LAYOUT */
.container {
    display: flex;
    height: 100vh;
}

/* SIDEBAR */
.sidebar {
    width: 240px;
    background: rgba(10, 15, 28, 0.55);
    backdrop-filter: blur(15px);
    border-right: 1px solid rgba(0, 170, 255, 0.25);
    padding: 20px;
}

.logo {
    font-size: 22px;
    font-weight: bold;
    color: #00aaff;
    letter-spacing: 2px;
    margin-bottom: 30px;
}

.nav-item {
    padding: 12px;
    margin: 10px 0;
    border-radius: 12px;
    cursor: pointer;
    background: rgba(255,255,255,0.05);
    border: 1px solid rgba(0,170,255,0.15);
    transition: 0.3s;
}

.nav-item:hover {
    background: rgba(0,170,255,0.15);
    border: 1px solid #00aaff;
    transform: translateX(5px);
}

/* MAIN */
.main {
    flex: 1;
    padding: 40px;
}

/* GLASS */
.glass {
    background: rgba(255, 255, 255, 0.06);
    border: 1px solid rgba(0, 170, 255, 0.2);
    backdrop-filter: blur(14px);
    border-radius: 18px;
    padding: 20px;
}

/* HEADER */
.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 25px;
}

.title {
    font-size: 28px;
    color: #00aaff;
}

/* BUTTON */
.btn {
    padding: 10px 18px;
    border-radius: 12px;
    border: 1px solid rgba(0,170,255,0.3);
    background: rgba(0,0,0,0.3);
    color: white;
    cursor: pointer;
    transition: 0.3s;
}

.btn:hover {
    background: rgba(0,170,255,0.2);
    box-shadow: 0 0 15px rgba(0,170,255,0.4);
}

/* GRID */
.grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 20px;
}

/* DOWNLOAD BUTTON */
.download-btn {
    padding: 14px 26px;
    border-radius: 14px;
    border: 1px solid #00aaff;
    background: rgba(0,0,0,0.4);
    color: white;
    cursor: pointer;
    transition: 0.3s;
}

.download-btn:hover {
    background: rgba(0,170,255,0.25);
    box-shadow: 0 0 20px rgba(0,170,255,0.5);
    transform: scale(1.05);
}

.small {
    color: #aaa;
    font-size: 13px;
}
</style>
</head>

<body>

<!-- 🌊 WATER WAVE BACKGROUND -->
<canvas id="waveCanvas"></canvas>

<div class="container">

    <!-- SIDEBAR -->
    <div class="sidebar">
        <div class="logo">RESISTANT</div>
        <div class="nav-item">Home</div>
        <div class="nav-item">Downloads</div>
        <div class="nav-item">Mods</div>
        <div class="nav-item">Changelog</div>
        <div class="nav-item">Support</div>
    </div>

    <!-- MAIN -->
    <div class="main">

        <div class="header glass">
            <div class="title">Download Hub</div>
            <button class="btn">Check Updates</button>
        </div>

        <div class="grid">

            <div class="glass">
                <h2 style="color:#00aaff;">Resistant Client</h2>
                <p class="small">Latest version v1.0</p>
                <br>
                <button class="download-btn">Download Client</button>
                <p class="small">Windows • Java Edition</p>
            </div>

            <div class="glass">
                <h3 style="color:#00aaff;">Features</h3>
                <p>FPS boost tools<br>Clean UI overlay<br>Lightweight system</p>
            </div>

        </div>

    </div>
</div>

<!-- 🌊 WAVE SCRIPT -->
<script>
const canvas = document.getElementById("waveCanvas");
const ctx = canvas.getContext("2d");

function resize() {
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
}
resize();
window.addEventListener("resize", resize);

let time = 0;

function drawWave() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);

    for (let i = 0; i < 5; i++) {
        ctx.beginPath();

        let opacity = 0.08 + i * 0.02;
        ctx.strokeStyle = `rgba(0, 170, 255, ${opacity})`;
        ctx.lineWidth = 2;

        for (let x = 0; x < canvas.width; x++) {
            let y =
                canvas.height / 2 +
                Math.sin(x * 0.01 + time + i) * 40 +
                Math.cos(x * 0.02 + time) * 20;

            if (x === 0) ctx.moveTo(x, y);
            else ctx.lineTo(x, y);
        }

        ctx.stroke();
    }

    time += 0.02;
    requestAnimationFrame(drawWave);
}

drawWave();
</script>

</body>
</html>
