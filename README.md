<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Telegram Mini App</title>
  <style>
    body {
      margin: 0;
      font-family: sans-serif;
      background: #f2f2f2;
      text-align: center;
      padding: 20px;
    }
    h1 {
      color: #333;
    }
    input, button {
      padding: 10px;
      font-size: 16px;
      margin: 10px;
      border-radius: 8px;
      border: 1px solid #ccc;
      width: 80%;
    }
    button {
      background-color: #2AABEE;
      color: white;
      border: none;
    }
  </style>
</head>
<body>
  <h1>Привет из Mini App</h1>
  <p>Введите сообщение для Telegram-бота:</p>
  <input type="text" id="inputText" placeholder="Введите что-нибудь..." />
  <button onclick="sendData()">Отправить боту</button>

  <script>
    const tg = window.Telegram.WebApp;

    // Настройка внешнего вида
    tg.expand(); // Расширяет на всю высоту
    tg.MainButton.text = "Отправить";
    tg.MainButton.color = "#2AABEE";
    tg.MainButton.textColor = "#ffffff";

    function sendData() {
      const data = document.getElementById("inputText").value;
      if (data.trim() === "") {
        alert("Введите текст");
        return;
      }
      tg.sendData(data); // Отправляет данные боту
    }
  </script>
</body>
</html>
