
<html>
<head>
    <title>蘿蔔追你跑＋有沒有LP</title>
    <style>
        body {
            margin: 0;
            height: 100vh;
            background: linear-gradient(to right, orange, yellow);
            overflow: hidden;
            cursor: none;
        }

        #carrot {
            position: absolute;
            font-size: 50px;
            pointer-events: none;
            transition: transform 0.05s linear;
        }
    </style>
</head>
<body>
    <div id="carrot">🥕</div>

    <!-- 播放你上傳的聲音檔（跟這個 index.html 放在同一個資料夾） -->
    <audio id="ouchSound" src="有沒有LP.m4a"></audio>

    <script>
        const carrot = document.getElementById("carrot");
        const sound = document.getElementById("ouchSound");
        let lastPlay = 0;

        document.addEventListener("mousemove", function(event) {
            const x = event.clientX;
            const y = event.clientY;
            carrot.style.transform = `translate(${x}px, ${y}px)`;

            const now = Date.now();
            if (now - lastPlay > 500) {
                sound.currentTime = 0;
                sound.play();
                lastPlay = now;
            }
        });
    </script>
</body>
</html>
