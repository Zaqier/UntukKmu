<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Untuk Cintaku ❤</title>
    <style>
        /* Tambahkan di bagian <style> */
@media (max-width: 600px) {
    .container {
        padding: 8px;
    }
    .header, .love-letter, #loveMeter {
        padding: 15px;
        margin: 10px 0;
    }
    .photo-frame {
        width: 120px;
        height: 120px;
        margin: 10px auto;
    }
    h1 {
        font-size: 1.5em;
    }
    .button {
        padding: 10px 18px;
        font-size: 15px;
    }
}
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', cursive;
        }

        body {
            background: linear-gradient(45deg, #ff9a9e, #fad0c4);
            min-height: 100vh;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
            text-align: center;
        }

        .header {
            padding: 40px;
            background: rgba(255, 255, 255, 0.9);
            border-radius: 15px;
            margin: 20px 0;
            box-shadow: 0 0 20px rgba(0,0,0,0.1);
        }

        h1 {
            color: #e91e63;
            font-size: 2.5em;
            margin-bottom: 10px;
        }

        .love-letter {
            background: white;
            padding: 30px;
            border-radius: 15px;
            margin: 20px 0;
            text-align: left;
            line-height: 1.6;
            position: relative;
        }

        .love-letter::before {
            content: "❤";
            position: absolute;
            top: -15px;
            left: -15px;
            font-size: 30px;
        }

        .photo-frame {
            width: 200px;
            height: 200px;
            border-radius: 50%;
            overflow: hidden;
            margin: 20px auto;
            border: 5px solid white;
            box-shadow: 0 0 20px rgba(0,0,0,0.2);
        }

        .photo-frame img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .button {
            background: #e91e63;
            color: white;
            padding: 15px 30px;
            border: none;
            border-radius: 25px;
            font-size: 18px;
            cursor: pointer;
            transition: transform 0.3s;
            margin: 10px;
        }

        .button:hover {
            transform: scale(1.1);
            background: #c2185b;
        }

        .heart-rain {
            position: fixed;
            top: -20px;
            animation: rain 3s linear infinite;
            pointer-events: none;
        }

        @keyframes rain {
            0% { transform: translateY(-20px) rotate(0deg); }
            100% { transform: translateY(100vh) rotate(360deg); }
        }

        #loveMeter {
            background: white;
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
            font-size: 24px;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <div class="photo-frame">
              <img src="WhatsApp_Image_2025-05-27_at_19.27.53_6334c3fd.jpg" alt="Momen Spesial 1">
            </div>
            <div class="photo-frame">
               <img src="WhatsApp_Image_2025-05-27_at_19.27.53_6334c3fd.jpg" alt="Momen Spesial 2">
            </div>
            <h1 id="title">Untuk <span id="name">Kekasihku</span> ❤</h1>
            <p>Scroll untuk baca surat cintaku...</p>
        </div>

        <div class="love-letter">
            <h2>Sayangku tersayang,</h2>
            <p>Setiap detik bersamamu adalah anugerah yang tak ternilai. Kamu adalah...</p>
            <ul>
                <li>🤍 Cahaya di kegelapanku</li>
                <li>🤍 Pelangi setelah hujan</li>
                <li>🤍 Alasan tersenyum tiap pagi</li>
            </ul>
            <p>Aku bersyukur tuhan mempertemukan kita. Mari bersama selamanya!</p>
            <p>Dengan cinta,<br>Yang selalu merindukanmu</p>
        </div>

        <div id="loveMeter">
            <p>Tingkat Cintaku Padamu:</p>
            <p id="meterValue">100%</p>
            <button class="button" onclick="increaseLove()">Tambah Cinta! ❤</button>
        </div>

        <button class="button" onclick="createHearts()">Klik untuk Hujan Cinta! 🌸</button>
    </div>

    <!-- Load jQuery -->
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
    <script>
        // Personalisasi nama
        const name = prompt("Masukkan nama pacar kesayanganmu:");
        document.getElementById('name').textContent = name || 'Kekasihku';
        document.title = `Untuk ${name || 'Cintaku'} ❤`;

        // Hujan hati
        function createHearts() {
            for(let i = 0; i < 50; i++) {
                const heart = document.createElement('div');
                heart.classList.add('heart-rain');
                heart.innerHTML = '❤';
                heart.style.left = Math.random() * 100 + 'vw';
                heart.style.animationDuration = Math.random() * 2 + 1 + 's';
                document.body.appendChild(heart);
                
                setTimeout(() => heart.repeat(), 3000);
            }
        }

        // Meter cinta
        let loveLevel = 100;
        function increaseLove() {
            loveLevel = Math.min(loveLevel + Math.random() * 10, 1000);
            document.getElementById('meterValue').textContent = 
                Math.round(loveLevel) + '%';
            
            if(loveLevel > 200) {
                document.getElementById('loveMeter').style.backgroundColor = '#ffe6f0';
                alert("Kamu benar-benar mencintaiku! 😍");
            }
        }
    </script>
</body>
</html>
