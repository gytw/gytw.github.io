<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Idle Game</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
        }
        .resource {
            margin: 20px;
        }
    </style>
</head>
<body>
    <h1>Idle Game</h1>
    <div class="resource">
        Gold: <span id="gold">0</span>
    </div>
    <button onclick="buyWorker()">Buy Worker (Cost: 10 Gold)</button>
    <div class="resource">
        Workers: <span id="workers">0</span>
    </div>

    <script>
        let gold = 0;
        let workers = 0;
        let goldPerSecond = 0;

        function update() {
            gold += goldPerSecond;
            document.getElementById('gold').innerText = gold;
            document.getElementById('workers').innerText = workers;
        }

        function buyWorker() {
            if (gold >= 10) {
                gold -= 10;
                workers += 1;
                goldPerSecond += 1;
            }
        }

        setInterval(update, 1000);
    </script>
</body>
</html>
