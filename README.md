# SaintValentineMaurine
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Valentine 💐</title>
    <style>
        body {
            margin: 0;
            min-height: 100vh;
            font-family: "Georgia", serif;
            background: linear-gradient(135deg, #f7efe5, #e9d5c5);
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }

        .card {
            background: #fffaf5;
            padding: 35px 25px;
            border-radius: 22px;
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.12);
            text-align: center;
            border: 2px solid #e4c9b0;
            max-width: 420px;
            width: 100%;
        }

        h1 {
            font-size: 1.6em;
            color: #7a4a3c;
            margin-bottom: 35px;
            line-height: 1.4;
        }

        .buttons {
            position: relative;
            height: 120px;
        }

        button {
            font-size: 1.05em;
            padding: 14px 26px;
            border-radius: 999px;
            border: none;
            font-family: inherit;
        }

        #yes {
            background-color: #d89c8a;
            color: white;
            width: 100%;
            max-width: 220px;
        }

        #yes:active {
            transform: scale(0.96);
        }

        #no {
            background-color: #c9b2a6;
            color: white;
            position: absolute;
            left: 50%;
            top: 60px;
            transform: translateX(-50%);
        }
    </style>
</head>
<body>

<div class="card">
    <h1>Est-ce que tu veux être ma Valentine ? 💐</h1>

    <div class="buttons" id="zone">
        <button id="yes">Oui 🥰</button>
        <button id="no">Non 😵</button>
    </div>
</div>

<script>
    const noButton = document.getElementById("no");
    const zone = document.getElementById("zone");

    function moveButton() {
        const zoneRect = zone.getBoundingClientRect();
        const btnRect = noButton.getBoundingClientRect();

        const maxX = zoneRect.width - btnRect.width;
        const maxY = zoneRect.height - btnRect.height;

        const x = Math.random() * maxX;
        const y = Math.random() * maxY;

        noButton.style.left = `${x}px`;
        noButton.style.top = `${y}px`;
    }

    // Desktop : souris
    zone.addEventListener("mousemove", moveButton);

    // Mobile : toucher
    noButton.addEventListener("touchstart", (e) => {
        e.preventDefault();
        moveButton();
    });

    document.getElementById("yes").addEventListener("click", () => {
        document.querySelector(".card").innerHTML = `
            <h1>💖 Elle a dit OUI 💖</h1>
            <p style="color:#7a4a3c;font-size:1.1em;">
                Prépare-toi pour la plus belle des Valentines 🌸
            </p>
        `;
    });
</script>

</body>
</html>
