# Taixiu
<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Trò chơi Tài Xỉu</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            text-align: center;
            padding: 20px;
        }
        h1 {
            color: #4CAF50;
        }
        .container {
            background-color: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            display: inline-block;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background-color: #45a049;
        }
        .result {
            margin-top: 20px;
            font-size: 18px;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Trò chơi Tài Xỉu</h1>
        <p>Chọn Tài (11-17) hoặc Xỉu (4-10):</p>
        <button onclick="play('Tài')">Tài</button>
        <button onclick="play('Xỉu')">Xỉu</button>
        <div class="result" id="result"></div>
    </div>

    <script>
        function play(bet) {
            // Tạo 3 con xúc xắc ngẫu nhiên
            const dice1 = Math.floor(Math.random() * 6) + 1;
            const dice2 = Math.floor(Math.random() * 6) + 1;
            const dice3 = Math.floor(Math.random() * 6) + 1;
            const total = dice1 + dice2 + dice3;

            // Xác định kết quả
            let resultText;
            if ((total >= 11 && total <= 17 && bet === "Tài") || 
                (total >= 4 && total <= 10 && bet === "Xỉu")) {
                resultText = `Bạn đã thắng! Tổng điểm: ${total}`;
            } else {
                resultText = `Bạn đã thua! Tổng điểm: ${total}`;
            }

            // Hiển thị kết quả
            document.getElementById("result").innerText = resultText;
        }
    </script>
</body>
</html>
