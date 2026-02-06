<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <title>Click the Box Game</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f0f0f0;
        }

        h1 {
            margin-top: 20px;
        }

        #score {
            font-size: 20px;
            margin: 10px;
        }

        #gameArea {
            width: 400px;
            height: 400px;
            background-color: white;
            border: 2px solid black;
            margin: 20px auto;
            position: relative;
        }

        #box {
            width: 50px;
            height: 50px;
            background-color: red;
            position: absolute;
            cursor: pointer;
        }
    </style>
</head>
<body>

    <h1>🎮 Click the Box</h1>
    <div id="score">Score: 0</div>

    <div id="gameArea">
        <div id="box"></div>
    </div>

    <script>
        const box = document.getElementById("box");
        const gameArea = document.getElementById("gameArea");
        const scoreText = document.getElementById("score");

        let score = 0;

        function moveBox() {
            const maxX = gameArea.clientWidth - box.clientWidth;
            const maxY = gameArea.clientHeight - box.clientHeight;

            const randomX = Math.floor(Math.random() * maxX);
            const randomY = Math.floor(Math.random() * maxY);

            box.style.left = randomX + "px";
            box.style.top = randomY + "px";
        }

        box.addEventListener("click", () => {
            score++;
            scoreText.textContent = "Score: " + score;
            moveBox();
        });

        moveBox();
    </script>

</body>
</html>
