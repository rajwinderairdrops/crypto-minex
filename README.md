<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>CryptoMineX - Cloud Mining Platform</title>
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body {
      font-family: 'Segoe UI', sans-serif;
      background: linear-gradient(135deg, #0f2027, #203a43, #2c5364);
      color: #fff;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
    }
    header {
      background: #111;
      padding: 20px;
      text-align: center;
      font-size: 26px;
      font-weight: bold;
      box-shadow: 0 2px 5px rgba(0,0,0,0.5);
    }
    .container {
      flex: 1;
      padding: 40px 20px;
      max-width: 600px;
      margin: auto;
      text-align: center;
    }
    .container h2 {
      font-size: 28px;
      margin-bottom: 20px;
    }
    .stats {
      font-size: 22px;
      margin: 20px 0;
    }
    .btn {
      padding: 15px 35px;
      background: #00c853;
      border: none;
      font-size: 18px;
      color: white;
      cursor: pointer;
      border-radius: 5px;
      transition: background 0.3s;
    }
    .btn:hover {
      background: #00e676;
    }
    footer {
      padding: 15px;
      text-align: center;
      font-size: 14px;
      background: #111;
      color: #aaa;
    }
    @media (max-width: 480px) {
      .container h2 {
        font-size: 22px;
      }
      .stats {
        font-size: 18px;
      }
      .btn {
        width: 90%;
      }
    }
  </style>
</head>
<body>

  <header>CryptoMineX</header>

  <div class="container">
    <h2>Start Mining & Earn Free Bitcoin</h2>
    <p class="stats">Mined: <span id="minedAmount">0.00000000</span> BTC</p>
    <button class="btn" onclick="toggleMining()">Start Mining</button>
  </div>

  <footer>
    &copy; 2025 CryptoMineX. All rights reserved.
  </footer>

  <script>
    let isMining = false;
    let minedAmount = 0;
    let miningInterval;

    function toggleMining() {
      const btn = document.querySelector('.btn');
      if (!isMining) {
        btn.textContent = 'Stop Mining';
        miningInterval = setInterval(() => {
          minedAmount += Math.random() * 0.0000007;
          document.getElementById('minedAmount').textContent = minedAmount.toFixed(8);
        }, 1000);
        isMining = true;
      } else {
        btn.textContent = 'Start Mining';
        clearInterval(miningInterval);
        isMining = false;
      }
    }
  </script>

</body>
</html>
