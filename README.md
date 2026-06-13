<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0">
<title>ICREATESTUFF VHS VAULT</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=VT323&display=swap" rel="stylesheet">

<link rel="stylesheet" href="style.css">
</head>

<body>

<div id="password-screen">
    <div class="login-box">
        <h1>VIDEO VAULT</h1>
        <p>ENTER ACCESS CODE</p>

        <input type="password" id="passwordInput">
        <button onclick="checkPassword()">ENTER</button>

        <p id="error"></p>
    </div>
</div>

<div id="main-site">

<header>

<div class="scanline"></div>

<h1>ICREATESTUFF</h1>
<p>BROADCAST ARCHIVE</p>

<nav>
<a href="#vault">VAULT</a>
<a href="#about">ABOUT</a>
<a href="#contact">CONTACT</a>
</nav>

</header>

<section class="hero">

<h2>RECOVERED FOOTAGE</h2>

<p>
Welcome to the archive.
Private uploads.
Behind the scenes.
Exclusive content.
</p>

<button onclick="scrollToVault()">
ENTER VAULT
</button>

</section>

<section id="vault">

<h2>VIDEO VAULT</h2>

<input
type="text"
id="search"
placeholder="SEARCH ARCHIVE..."
onkeyup="searchVideos()">

<div class="video-grid">

<div class="card">
<video controls>
<source src="videos/vlog1.mp4">
</video>
<h3>Urban Exploration</h3>
</div>

<div class="card">
<video controls>
<source src="videos/vlog2.mp4">
</video>
<h3>Behind The Scenes</h3>
</div>

<div class="card">
<video controls>
<source src="videos/vlog3.mp4">
</video>
<h3>Creator Life</h3>
</div>

</div>

</section>

<section id="about">

<h2>ABOUT</h2>

<p>
Digital creator documenting projects,
experiments, adventures and exclusive footage.
</p>

</section>

<section id="contact">

<h2>CONTACT</h2>

<p>your@email.com</p>

<p>YouTube | TikTok | Instagram</p>

</section>

<footer>

<p>© 2026 ICREATESTUFF ARCHIVES</p>

</footer>

</div>

<script src="script.js"></script>

</body>
</html>

*{
margin:0;
padding:0;
box-sizing:border-box;
}

body{
background:#050505;
color:#fff;
font-family:'VT323',monospace;
overflow-x:hidden;
}

#main-site{
display:none;
}

#password-screen{
height:100vh;
display:flex;
justify-content:center;
align-items:center;
background:black;
}

.login-box{
border:2px solid #ff003c;
padding:40px;
text-align:center;
box-shadow:0 0 20px #ff003c;
}

.login-box h1{
font-size:4rem;
}

input{
background:black;
color:white;
border:1px solid #ff003c;
padding:10px;
width:250px;
font-size:1.2rem;
margin-top:20px;
}

button{
padding:10px 20px;
margin-top:15px;
cursor:pointer;
background:#ff003c;
border:none;
color:white;
font-family:inherit;
font-size:1.2rem;
}

header{
padding:40px;
text-align:center;
position:relative;
}

header h1{
font-size:5rem;
letter-spacing:5px;
text-shadow:0 0 15px #ff003c;
}

nav{
margin-top:20px;
}

nav a{
color:white;
text-decoration:none;
margin:0 20px;
font-size:1.5rem;
}

.hero{
min-height:70vh;
display:flex;
flex-direction:column;
justify-content:center;
align-items:center;
text-align:center;
padding:40px;
}

.hero h2{
font-size:4rem;
color:#00d8ff;
}

.hero p{
max-width:700px;
font-size:1.5rem;
margin:20px;
}

#vault,
#about,
#contact{
padding:80px 10%;
}

.video-grid{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(300px,1fr));
gap:30px;
margin-top:30px;
}

.card{
background:#111;
padding:20px;
border:1px solid #333;
transition:.3s;
}

.card:hover{
transform:translateY(-5px);
box-shadow:0 0 15px #00d8ff;
}

video{
width:100%;
}

footer{
text-align:center;
padding:30px;
border-top:1px solid #222;
}

.scanline{
position:fixed;
top:0;
left:0;
width:100%;
height:100%;
pointer-events:none;
background:
linear-gradient(
to bottom,
transparent 50%,
rgba(255,255,255,.03) 51%
);
background-size:100% 4px;
animation:flicker .2s infinite;
}

@keyframes flicker{
0%{opacity:.95}
50%{opacity:1}
100%{opacity:.92}
}

.glitch{
animation:glitch .2s infinite;
}

@keyframes glitch{
0%{transform:translate(0)}
20%{transform:translate(-2px,2px)}
40%{transform:translate(2px,-2px)}
60%{transform:translate(-2px,0)}
80%{transform:translate(2px,2px)}
100%{transform:translate(0)}
}

const PASSWORD = "vault2026";

function checkPassword(){

const entered =
document.getElementById("passwordInput").value;

if(entered === PASSWORD){

document.getElementById("password-screen")
.style.display = "none";

document.getElementById("main-site")
.style.display = "block";

}else{

document.getElementById("error")
.innerText = "ACCESS DENIED";
}
}

function scrollToVault(){

document.getElementById("vault")
.scrollIntoView({
behavior:"smooth"
});
}

function searchVideos(){

let filter =
document.getElementById("search")
.value.toLowerCase();

let cards =
document.querySelectorAll(".card");

cards.forEach(card=>{

let title =
