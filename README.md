<!DOCTYPE html>
<html lang="hi">
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>My OTT Hub - All in One</title>
<style>
* {margin:0; padding:0; box-sizing:border-box}
body {
    font-family: 'Arial Black', sans-serif;
    background: linear-gradient(135deg, #0a0a1a 0%, #1a0a2e 100%);
    color: #fff;
    min-height: 100vh;
}
header {
    background: rgba(255,0,128,0.1);
    backdrop-filter: blur(10px);
    padding: 20px;
    text-align: center;
    border-bottom: 3px solid #ff0080;
}
header h1 {
    font-size: 32px;
    background: linear-gradient(90deg, #ff0080, #00FFFF, #FFD700);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    text-shadow: 0 0 20px #ff0080;
}
.container {
    padding: 20px;
    max-width: 1200px;
    margin: 0 auto;
}
.section-title {
    font-size: 24px;
    margin: 30px 0 15px;
    color: #00FFFF;
    border-left: 5px solid #00FFFF;
    padding-left: 15px;
}
.grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
    gap: 20px;
}
.card {
    background: rgba(255,255,255,0.05);
    border-radius: 15px;
    padding: 20px;
    text-align: center;
    cursor: pointer;
    transition: all 0.3s;
    border: 2px solid transparent;
}
.card:hover {
    transform: translateY(-8px) scale(1.05);
    border-color: #ff0080;
    box-shadow: 0 10px 30px rgba(255,0,128,0.4);
}
.card img {
    width: 80px;
    height: 80px;
    border-radius: 15px;
    margin-bottom: 10px;
}
.card p {
    font-size: 14px;
    color: #FFD700;
}
.youtube-player {
    background: rgba(0,0,0,0.5);
    border-radius: 15px;
    padding: 20px;
    margin: 20px 0;
}
.youtube-player iframe {
    width: 100%;
    height: 315px;
    border-radius: 10px;
    border: 3px solid #ff0080;
}
.search-box {
    width: 100%;
    padding: 15px;
    font-size: 16px;
    border-radius: 10px;
    border: 2px solid #00FFFF;
    background: rgba(255,255,255,0.1);
    color: #fff;
    margin: 20px 0;
}
.search-box::placeholder {color: #aaa}
footer {
    text-align: center;
    padding: 30px;
    color: #888;
    font-size: 12px;
}
@media (max-width: 600px) {
    .youtube-player iframe {height: 200px}
    header h1 {font-size: 24px}
</style>
</head>
<body>

<header>
    <h1>🎬 MY OTT HUB 🎵</h1>
    <p style="color:#00FFFF; margin-top:10px">Netflix + JioHotstar + Prime + YouTube - Ek Jagya Ae</p>
</header>

<div class="container">

    <input type="text" class="search-box" placeholder="🔍 Search karo - 'Mirzapur', 'Shinchan', 'Arijit Songs'..." onkeyup="searchOTT(this.value)">

    <div class="section-title">📺 Streaming Platforms</div>
    <div class="grid" id="ottGrid">
        <div class="card" onclick="window.open('https://www.netflix.com', '_blank')">
            <img src="https://logo.clearbit.com/netflix.com" alt="Netflix">
            <p>Netflix</p>
        </div>
        <div class="card" onclick="window.open('https://www.jiocinema.com', '_blank')">
            <img src="https://logo.clearbit.com/jiocinema.com" alt="JioHotstar">
            <p>JioHotstar</p>
        </div>
        <div class="card" onclick="window.open('https://www.primevideo.com', '_blank')">
            <img src="https://logo.clearbit.com/primevideo.com" alt="Prime">
            <p>Prime Video</p>
        </div>
        <div class="card" onclick="window.open('https://www.mxplayer.in', '_blank')">
            <img src="https://logo.clearbit.com/mxplayer.in" alt="MX Player">
            <p>MX Player Free</p>
        </div>
        <div class="card" onclick="window.open('https://www.zee5.com', '_blank')">
            <img src="https://logo.clearbit.com/zee5.com" alt="ZEE5">
            <p>ZEE5</p>
        </div>
        <div class="card" onclick="window.open('https://www.sonyliv.com', '_blank')">
            <img src="https://logo.clearbit.com/sonyliv.com" alt="SonyLIV">
            <p>SonyLIV</p>
        </div>
    </div>

    <div class="section-title">🎵 YouTube Music Player</div>
    <div class="youtube-player">
        <iframe id="ytPlayer" src="https://www.youtube.com/embed/videoseries?list=PL9tY0BWXOZFtcc4f6x3T5oG7zTnHh0g0G" frameborder="0" allowfullscreen></iframe>
        <p style="margin-top:10px; color:#00FFFF">Tari favorite playlist - Arijit, Badshah, Old Songs</p>
    </div>

    <div class="section-title">🎯 Quick Search</div>
    <div class="grid">
        <div class="card" onclick="searchYt('Arijit Singh Songs')">
            <p>🎤 Arijit Songs</p>
        </div>
        <div class="card" onclick="searchYt('Badshah New Song')">
            <p>🔥 Badshah Hits</p>
        </div>
        <div class="card" onclick="searchYt('Shinchan Full Episode')">
            <p>📺 Shinchan</p>
        </div>
        <div class="card" onclick="searchYt('Motu Patlu Cartoon')">
            <p>Motu Patlu</p>
        </div>
    </div>

</div>

<footer>
    <p>⚡ Made with ❤️ | Legal Aggregator - Content Official Sites Par Khule Chhe</p>
</footer>

<script>
function searchOTT(query){
    if(query.length > 2){console.log('Searching: ' + query);}
}
function searchYt(query){
    const player = document.getElementById('ytPlayer');
    player.src = 'https://www.youtube.com/embed?listType=search&list=' + encodeURIComponent(query) + '&autoplay=1';
}
</script>

</body>
</html>
