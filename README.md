# TugasJarmul
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Radio Streaming</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            padding: 20px;
            background-image: url('r.jpg'); /* Ganti 'radio.jpg' dengan nama file gambar latar belakang Anda */
            background-size: cover; /* Menyesuaikan gambar latar belakang dengan ukuran jendela browser */
            background-position: center; /* Posisi gambar latar belakang di tengah halaman */
            background-repeat: no-repeat; /* Mencegah gambar latar belakang diulang */
            color: white; /* Warna teks di atas gambar latar belakang */
        }

        h1 {
            color: #15ff00;
            font-size:100px;
        }

        .btn-container {
            margin-top: 20px;
        }

        button {
            background-color: #4CAF50;
            color: white;
            border: none;
            padding: 10px 20px;
            text-align: center;
            text-decoration: none;
            display: inline-block;
            font-size: 16px;
            margin: 5px 2px;
            transition-duration: 0.4s;
            cursor: pointer;
            border-radius: 8px;
        }

        button:hover {
            background-color: white;
            color: #4CAF50;
            border: 2px solid #4CAF50;
        }

        button:active {
            background-color: #45a049;
        }

        audio {
            width: 100%;
            margin-top: 20px;
        }

        .volume-slider {
            width: 80%;
            margin-top: 20px;
        }
    </style>
</head>

<body>
    <h1>Radio Streaming</h1>
    <div class="btn-container">
        <button id="playPauseBtn">Play</button>
        <br>
        <button id="stopBtn">Stop</button>
        <br>
        <button id="channel1Btn">Channel 1</button>
        <button id="channel2Btn">Channel 2</button>
        <button id="channel3Btn">Channel 3</button>
        <button id="channel4Btn">Channel 4</button>
        <button id="channel5Btn">Channel 5</button>
    </div>

    <audio id="radio" controls></audio>
    <div class="volume-slider">
        <label for="volume">Volume:</label>
        <input type="range" id="volume" min="0" max="1" step="0.1" value="1">
    </div>

    <script>
        document.addEventListener("DOMContentLoaded", function() {
            const radio = document.getElementById('radio');
            const playPauseBtn = document.getElementById('playPauseBtn');
            const stopBtn = document.getElementById('stopBtn');
            const volumeSlider = document.getElementById('volume');
            const channel1Btn = document.getElementById('channel1Btn');
            const channel2Btn = document.getElementById('channel2Btn');
            const channel3Btn = document.getElementById('channel3Btn');
            const channel4Btn = document.getElementById('channel4Btn');
            const channel5Btn = document.getElementById('channel5Btn');

            // URL streaming radio
            const channels = [
                "https://c5.siar.us/proxy/ssfm/stream", // Ganti dengan URL streaming channel 1 Anda
                "https://27153.live.streamtheworld.com/T_RAD_90S_S01_SC", // Ganti dengan URL streaming channel 2 Anda
                "https://stream.live.vc.bbcmedia.co.uk/bbc_world_service", // Ganti dengan URL streaming channel 3 Anda
                "https://c5.siar.us/proxy/ssfm/stream", // Ganti dengan URL streaming channel 4 Anda
                "https://n05.radiojar.com/4ywdgup3bnzuv?rj-"  // Ganti dengan URL streaming channel 5 Anda
            ];

            let currentChannel = 0;
            let isPlaying = false;

            function playChannel(channelIndex) {
                radio.src = channels[channelIndex];
                radio.play();
                isPlaying = true;
            }

            playPauseBtn.addEventListener('click', function() {
                if (isPlaying) {
                    radio.pause();
                    playPauseBtn.textContent = 'Play';
                } else {
                    playChannel(currentChannel);
                    playPauseBtn.textContent = 'Pause';
                }
                isPlaying = !isPlaying;
            });

            stopBtn.addEventListener('click', function() {
                radio.pause();
                radio.currentTime = 0;
                playPauseBtn.textContent = 'Play';
                isPlaying = false;
            });

            volumeSlider.addEventListener('input', function() {
                radio.volume = volumeSlider.value;
            });

            channel1Btn.addEventListener('click', function() {
                playChannel(0);
                currentChannel = 0;
                playPauseBtn.textContent = 'Pause';
                isPlaying = true;
            });

            channel2Btn.addEventListener('click', function() {
                playChannel(1);
                currentChannel = 1;
                playPauseBtn.textContent = 'Pause';
                isPlaying = true;
            });

            channel3Btn.addEventListener('click', function() {
                playChannel(2);
                currentChannel = 2;
                playPauseBtn.textContent = 'Pause';
                isPlaying = true;
            });

            channel4Btn.addEventListener('click', function() {
                playChannel(3);
                currentChannel = 3;
                playPauseBtn.textContent = 'Pause';
                isPlaying = true;
            });

            channel5Btn.addEventListener('click', function() {
                playChannel(4);
                currentChannel = 4;
                playPauseBtn.textContent = 'Pause';
                isPlaying = true;
            });
        });
    </script>
</body>

</html>
