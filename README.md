
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Fizza's Scratch Games Hub</title>
  <style>
    body { font-family: Arial, sans-serif; background: #000; color: #fff; margin: 0; padding: 20px; text-align: center; }
    h1 { color: #ff4c4c; } /* Matches your cookie accent */
    .welcome-text { opacity: 0.9; max-width: 600px; margin: 0 auto 30px; } /* Style for welcome paragraph */
    .subtitle { 
      color: #ff8c1a; /* Orange for warning vibe */
      font-size: 1.1em;
      opacity: 0.9;
      max-width: 600px;
      margin: 0 auto 20px;
      font-style: italic;
    } /* Style for subtitle */
    .games-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 20px; max-width: 1200px; margin: 0 auto; }
    .game-card { background: #333; border-radius: 10px; padding: 15px; box-shadow: 0 5px 15px rgba(255,76,76,0.3); transition: transform 0.2s; }
    .game-card:hover { transform: scale(1.05); }
    .game-title { margin: 10px 0; font-size: 1.5em; }
    .play-btn { background: #ff4c4c; color: white; border: none; padding: 10px 20px; border-radius: 5px; cursor: pointer; font-size: 1em; }
    .play-btn:hover { background: #ff8c1a; }
    iframe { width: 100%; height: 500px; border: none; margin-top: 20px; } /* Adjusted height for Scratch stage */
    #game-player { display: none; } /* Hidden until game selected */
  </style>
</head>
<body>
  <h1>🍪 Fizza's Scratch Games! 🍪</h1>
  <p class="subtitle">⚠️ Heads up: The games you're going to play do not save progress—fresh start every time! 💪</p>
  <p class="welcome-text">Pick a game and click Play.</p>
 
  <div class="games-grid">
    <!-- Your Cookie Clicker – the star! -->
    <div class="game-card">
      <h2 class="game-title">Cookie Clicker</h2>
      <p>Click cookies, buy upgrades, go infinite!</p>
      <button class="play-btn" onclick="loadGame('Cookie clicker by - Fizza (1).html')">Play Now!</button>
    </div>
   
    <!-- Add more games here later – copy this block -->
    <!-- Example placeholder:
    <div class="game-card">
      <h2 class="game-title">My Next Game</h2>
      <p>Description...</p>
      <button class="play-btn" onclick="loadGame('game2.html')">Play Now!</button>
    </div> -->
  </div>
 
  <div id="game-player">
    <button class="play-btn" onclick="backToMenu()" style="position: absolute; top: 10px; left: 10px; z-index: 10;">← Back to Menu</button>
    <iframe id="game-frame" sandbox="allow-scripts allow-same-origin allow-forms allow-pointer-lock allow-popups allow-top-navigation" allowfullscreen></iframe> <!-- Enhanced sandbox + fullscreen -->
  </div>
 
  <script>
    function loadGame(gameFile) {
      document.querySelector('.games-grid').style.display = 'none';
      document.querySelector('.welcome-text').style.display = 'none'; // Hide welcome text when game loads
      document.querySelector('.subtitle').style.display = 'none'; // Hide subtitle when game loads
      document.getElementById('game-player').style.display = 'block';
      document.getElementById('game-frame').src = gameFile;
    }
    function backToMenu() {
      document.getElementById('game-player').style.display = 'none';
      document.querySelector('.games-grid').style.display = 'grid';
      document.querySelector('.welcome-text').style.display = 'block'; // Show welcome text when back to menu
      document.querySelector('.subtitle').style.display = 'block'; // Show subtitle when back to menu
      document.getElementById('game-frame').src = ''; // Unload game
    }
  </script>
</body>
</html>
