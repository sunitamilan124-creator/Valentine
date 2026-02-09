<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Valentine 💖</title>

<style>
    body {
        text-align: center;
        font-family: Arial, sans-serif;
        background: linear-gradient(to bottom, #ffe6f0, #ffccdd);
        overflow: hidden;
        height: 100vh;
        margin: 0;
    }

    h1 {
        margin-top: 100px;
        font-size: 42px;
        color: #ff1a75;
        z-index: 2;
        position: relative;
    }

    .btn {
        padding: 12px 25px;
        font-size: 18px;
        border: none;
        border-radius: 8px;
        cursor: pointer;
        position: absolute;
        z-index: 2;
    }

    #yes {
        background: #ff4d88;
        color: white;
        left: 45%;
        top: 55%;
    }

    #no {
        background: #ccc;
        left: 55%;
        top: 55%;
    }

    /* Floating hearts */
    .heart {
        position: absolute;
        bottom: -20px;
        color: red;
        font-size: 20px;
        animation: floatUp linear infinite;
        opacity: 0.7;
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

<h1>Will you be my valentine? 💖</h1>

<button id="yes" class="btn" onclick="yesClicked()">Yes 💕</button>
<button id="no" class="btn">No 😜</button>

<!-- Music -->
<audio id="music" autoplay loop>
    <source src="https://www2.cs.uic.edu/~i101/SoundFiles/Perfect.mp3" type="audio/mpeg">
</audio>

<script>
function yesClicked() {
    document.body.innerHTML = `
        <h1 style='margin-top:150px;color:#ff1a75;'>Yayyyy!!! 💖🥰</h1>
        <h2>I love you ❤️</h2>
    `;
}

/* Moving NO button */
const noBtn = document.getElementById("no");

noBtn.addEventListener("mouseover", moveButton);
noBtn.addEventListener("click", moveButton);

function moveButton() {
    const x = Math.random() * (window.innerWidth - 100);
    const y = Math.random() * (window.innerHeight - 50);
    noBtn.style.left = x + "px";
    noBtn.style.top = y + "px";
}

/* Create floating hearts */
function createHeart() {
    const heart = document.createElement("div");
    heart.classList.add("heart");
    heart.innerHTML = "❤️";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.animationDuration = (Math.random() * 3 + 3) + "s";
    heart.style.fontSize = (Math.random() * 20 + 15) + "px";

    document.body.appendChild(heart);

    setTimeout(() => {
        heart.remove();
    }, 6000);
}

setInterval(createHeart, 300);
</script>

</body>
</html>
