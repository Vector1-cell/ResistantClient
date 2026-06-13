# ResistantClient
Its a minecraft client that helps boost your gameplay, make it feel better, smoother, snappier and much more

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Resistant Client</title>

<style>
/* ===== GLOBAL ===== */
body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: radial-gradient(circle at top, #0a0f1c, #000000 70%);
    color: white;
    overflow: hidden;
}

/* ===== LAYOUT ===== */
.container {
    display: flex;
    height: 100vh;
}

/* ===== SIDEBAR (LUNAR STYLE) ===== */
.sidebar {
    width: 240px;
    background: rgba(10, 15, 28, 0.6);
    backdrop-filter: blur(15px);
    border-right: 1px solid rgba(0, 170, 255, 0.2);
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

/* ===== MAIN AREA ===== */
.main {
    flex: 1;
    padding: 40px;
    overflow-y: auto;
}

/* ===== GLASS WIDGET ===== */
.glass {
    background: rgba(255, 255, 255, 0.06);
    border: 1px solid rgba(0, 170, 255, 0.2);
    backdrop-filter: blur(14px);
    border-radius: 18px;
    padding: 20px;
    box-shadow: 0 10px 30px rgba(0,0,0,0.5);
}

/* ===== HEADER ===== */
.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 30px;
}

.title {
    font-size: 28px;
    color: #00aaff;
}

/* ===== BUTTONS ===== */
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
    border: 1px solid #00aaff;
    box-shadow: 0 0 15px rgba(0,170,255,0.4);
}

/* ===== GRID ===== */
.grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 20px;
}

.card h3 {
    color: #00aaff;
}
</style>

</head>

<body>

<div class="container">

    <!-- SIDEBAR -->
    <div class="sidebar">
        <div class="logo">RESISTANT</div>

        <div class="nav-item">Dashboard</div>
        <div class="nav-item">Mods</div>
        <div class="nav-item">Cosmetics</div>
        <div class="nav-item">Settings</div>
        <div class="nav-item">Accounts</div>
    </div>

    <!-- MAIN -->
    <div class="main">

        <div class="header glass">
            <div class="title">Dashboard</div>
            <button class="btn">Launch Minecraft</button>
        </div>

        <div class="grid">

            <div class="glass card">
                <h3>Status</h3>
                <p>Client running smoothly. No issues detected.</p>
            </div>

            <div class="glass card">
                <h3>Latest Mods</h3>
                <p>Click Mods in sidebar to manage your pack.</p>
            </div>

            <div class="glass card">
                <h3>Performance</h3>
                <p>FPS Boost: Enabled<br>Memory Optimizer: Active</p>
            </div>

            <div class="glass card">
                <h3>Updates</h3>
                <p>Version 1.0 - Initial Resistant Client release</p>
            </div>

        </div>

    </div>

</div>

</body>
</html>
