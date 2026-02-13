# Happy-valentines-nni
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>NNI ❤️ BEEBO</title>

<style>
body {
    margin: 0;
    font-family: "Segoe UI", Arial, sans-serif;
    background: linear-gradient(135deg, #ff758c, #ff7eb3);
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
    color: white;
}

/* Dreamy glow layer */
body::before {
    content: "";
    position: absolute;
    width: 200%;
    height: 200%;
    background: radial-gradient(circle, rgba(255,255,255,0.15), transparent 40%);
    animation: glowMove 12s linear infinite;
}

@keyframes glowMove {
    from { transform: translate(-25%, -25%); }
    to { transform: translate(-35%, -35%); }
}

.card {
    background: rgba(0,0,0,0.25);
    padding: 30px;
    border-radius: 30px;
    width: 90%;
    max-width: 420px;
    text-align: center;
    box-shadow: 0 20px 40px rgba(0,0,0,0.35);
    position: relative;
    z-index: 2;
    backdrop-filter: blur(10px);
}

h1 {
    margin: 0;
    font-size: 32px;
}

.typing {
    margin-top: 10px;
    font-size: 18px;
    min-height: 60px;
}

.hug-img {
    width: 160px;
    margin: 15px auto;
    display: block;
    filter: drop-shadow(0 10px 20px rgba(0,0,0,0.35));
    animation: float 3s ease-in-out infinite;
}

@keyframes float {
    0% { transform: translateY(0); }
    50% { transform: translateY(-6px); }
    100% { transform: translateY(0); }
}

button {
    padding: 12px 24px;
    border: none;
    border-radius: 30px;
    background: white;
    color: #ff4f81;
    font-size: 16px;
    cursor: pointer;
    margin-top: 10px;
    transition: 0.3s;
}

button:hover {
    transform: scale(1.05);
}

.hidden { display: none; }

/* Hearts */
.heart, .sparkle {
    position: absolute;
    pointer-events: none;
}

/* Floating hearts */
.heart {
    animation: floatUp 6s linear infinite;
    opacity: 0.8;
}

@keyframes floatUp {
    from { transform: translateY(0); opacity: 0.8; }
    to { transform: translateY(-110vh); opacity: 0; }
}

/* Sparkles */
.sparkle {
    color: white;
    animation: sparkleFloat 4s linear infinite;
    opacity: 0.9;
    text-shadow: 0 0 8px rgba(255,255,255,0.8);
}

@keyframes sparkleFloat {
    from { transform: translateY(0) scale(0.8); opacity: 0; }
    50% { opacity: 1; }
    to { transform: translateY(-80vh) scale(1.2); opacity: 0; }
}
</style>
</head>

<body>

<div class="card">
    <h1>NNI ❤️</h1>
    <div class="typing" id="typing"></div>

    <img class="hug-img" src="https://i.imgur.com/3ZQ3Z4O.png">

    <button onclick="showLove()">Tap My Heart 💖</button>

    <div id="message" class="hidden">
        <p style="margin-top:15px; font-size:20px;">
            You Are My Favorite Person ✨💞<br><br>
            Sending Infinite Love & Hugs 🤗<br><br>
            Forever Yours,<br>
            <b>BEEBO</b> ❤️
        </p>

        <img class="hug-img" src="https://i.imgur.com/JqEuJ6t.png">
    </div>
</div>

<script>
// Typewriter Text
const text = "Happy Valentine’s Day My Love 💕 You make my world brighter every single day ✨";
let i = 0;

function typeWriter() {
    if (i < text.length) {
        document.getElementById("typing").innerHTML += text.charAt(i);
        i++;
        setTimeout(typeWriter, 55);
    }
}
typeWriter();

function showLove() {
    document.getElementById("message").style.display = "block";
}

// Floating hearts
function createHeart() {
    const heart = document.createElement("div");
    heart.className = "heart";
    heart.innerHTML = "❤️";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.bottom = "-20px";
    heart.style.fontSize = (Math.random() * 20 + 16) + "px";
    heart.style.animationDuration = (Math.random() * 3 + 3) + "s";
    document.body.appendChild(heart);
    setTimeout(() => heart.remove(), 6000);
}

// Sparkles
function createSparkle() {
    const sparkle = document.createElement("div");
    sparkle.className = "sparkle";
    sparkle.innerHTML = "✨";
    sparkle.style.left = Math.random() * 100 + "vw";
    sparkle.style.bottom = "-10px";
    sparkle.style.fontSize = (Math.random() * 12 + 14) + "px";
    sparkle.style.animationDuration = (Math.random() * 2 + 2) + "s";
    document.body.appendChild(sparkle);
    setTimeout(() => sparkle.remove(), 4000);
}

setInterval(createHeart, 350);
setInterval(createSparkle, 200);
</script>

</body>
</html>
