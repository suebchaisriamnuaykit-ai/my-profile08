<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>เกมทายตัวเลข 🎲</title>
    <style>
        body {
            font-family: sans-serif;
            text-align: center;
            background-color: #eef2f3;
            padding-top: 50px;
        }
        .game-card {
            background: white;
            padding: 30px;
            border-radius: 12px;
            display: inline-block;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
        }
        input {
            padding: 10px;
            font-size: 18px;
            width: 80px;
            text-align: center;
            border: 2px solid #ccc;
            border-radius: 6px;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            margin-left: 5px;
        }
        button:hover { background-color: #0056b3; }
        #message {
            margin-top: 20px;
            font-size: 20px;
            font-weight: bold;
        }
    </style>
</head>
<body>

    <div class="game-card">
        <h1>🎲 เกมทายตัวเลข (1 - 10)</h1>
        <p>ลองทายสิว่าคอมพิวเตอร์คิดเลขอะไรไว้?</p>
        
        <input type="number" id="guessInput" min="1" max="10" placeholder="1-10">
        <button onclick="checkGuess()">ทายเลย!</button>

        <p id="message"></p>
    </div>

    <script>
        // สุ่มเลข 1 ถึง 10 เก็บไว้
        const randomNumber = Math.floor(Math.random() * 10) + 1;

        function checkGuess() {
            // ดึงค่าที่ผู้เล่นพิมพ์เข้ามา
            const userGuess = Number(document.getElementById('guessInput').value);
            const messageElement = document.getElementById('message');

            if (!userGuess) {
                messageElement.innerText = "กรุณาใส่ตัวเลขก่อนนะ!";
                messageElement.style.color = "orange";
            } else if (userGuess === randomNumber) {
                messageElement.innerText = "🎉 ถูกต้องแล้ว! เก่งมากกก";
                messageElement.style.color = "green";
            } else if (userGuess > randomNumber) {
                messageElement.innerText = "📈 มากเกินไป ลองใหม่สิ!";
                messageElement.style.color = "red";
            } else {
                messageElement.innerText = "📉 น้อยเกินไป ลองใหม่สิ!";
                messageElement.style.color = "red";
            }
        }
    </script>

</body>
</html>
