# Foodcinema
Foodcinema movie website 

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta name="theme-color" content="#0b0907">
<title>FOOD CINEMA — Movies Without Limits</title>
<style>
:root {
 --bg:#0b0907;
 --panel:#15110d;
 --gold:#d6ad61;
 --gold2:#f2d69a;
 --text:#f8f2e8;
 --muted:#a69b89;
 --line:#382d1e;
}
* {box-sizing:border-box}
body {
 margin:0;
 background:var(--bg);
 color:var(--text);
 font-family:Arial,sans-serif;
}
header {
 padding:18px 5%;
 display:flex;
 justify-content:space-between;
 align-items:center;
 flex-wrap:wrap;
 border-bottom:1px solid #382d1e;
}
.logo {
 font-size:25px;
 font-weight:900;
 color:var(--gold2);
 letter-spacing:2px;
}
nav {display:flex;gap:18px}
nav a {
 color:white;
 text-decoration:none;
 font-size:14px;
}
button {
 cursor:pointer;
}
.btn {
 background:var(--gold);
 color:#171008;
 border:0;
 border-radius:5px;
 padding:11px 16px;
 font-weight:bold;
}
main {
 max-width:1200px;
 margin:auto;
 padding:20px;
}
.hero {
 min-height:380px;
 padding:40px;
 display:flex;
 align-items:end;
 border:1px solid #6c512b;
 border-radius:12px;
 background:
 linear-gradient(90deg,#090807,#09080799),
 url('https://images.unsplash.com/photo-1489599849927-2ee91cede3ba?auto=format&fit=crop&w=1800&q=85')
 center/cover;
}
.hero h1 {
 font-size:clamp(38px,7vw,70px);
 margin:10px 0;
 font-family:Georgia,serif;
}
.hero p {
 color:#d0c4b3;
 line-height:1.7;
}
.gold {color:var(--gold2)}
.section {margin:40px 0}
.section h2 {
 font-family:Georgia,serif;
 font-size:28px;
}
.search {
 width:100%;
 max-width:350px;
 padding:13px;
 background:#15110d;
 color:white;
 border:1px solid var(--line);
 border-radius:5px;
}
.filters {
 display:flex;
 gap:8px;
 flex-wrap:wrap;
 margin:18px 0;
}
.chip {
 padding:10px 16px;
 border:1px solid var(--line);
 background:#17130e;
 color:white;
 border-radius:25px;
}
.chip.active {
 background:var(--gold);
 color:black;
}
.grid {
 display:grid;
 grid-template-columns:repeat(4,1fr);
 gap:16px;
}
.movie {
 background:var(--panel);
 border:1px solid #382d1e;
 border-radius:8px;
 overflow:hidden;
}
.poster {
 height:190px;
 display:flex;
 align-items:center;
 justify-content:center;
 font-size:60px;
 background:radial-gradient(circle,#59401e,#17110a);
}
.movie-body {padding:14px}
.movie h3 {margin:5px 0}
.meta {
 color:var(--muted);
 font-size:12px;
}
.movie-actions {
 display:flex;
 gap:8px;
 margin-top:14px;
}
.movie-actions button {flex:1}
.earning {
 display:grid;
 grid-template-columns:repeat(3,1fr);
 gap:15px;
}
.earn-card {
 background:#20190f;
 border:1px solid var(--line);
 padding:20px;
 border-radius:8px;
}
.earn-card b {
 display:block;
 color:var(--gold2);
 margin:10px 0;
}
.earn-card p {
 color:var(--muted);
 line-height:1.6;
 font-size:13px;
}
.notice {
 background:#211a10;
 border:1px solid #6b512a;
 padding:15px;
 border-radius:7px;
 color:#e9d6b1;
 line-height:1.6;
 font-size:13px;
}
footer {
 border-top:1px solid var(--line);
 padding:25px;
 text-align:center;
 color:var(--muted);
 font-size:12px;
}
@media(max-width:800px) {
 .grid {grid-template-columns:repeat(2,1fr)}
 .earning {grid-template-columns:1fr}
}
@media(max-width:500px) {
 header {gap:15px}
 nav {width:100%;justify-content:space-between}
 .hero {padding:25px;min-height:350px}
 .grid {gap:10px}
 .poster {height:140px}
 .movie-actions {flex-direction:column}
}
</style>
</head>

<body>

<header>
 <div class="logo">FOOD CINEMA 🎬</div>
 <nav>
  <a href="#home">Home</a>
  <a href="#movies">Movies</a>
  <a href="#languages">Languages</a>
  <a href="#earn">Earning</a>
 </nav>
</header>

<main>

<section class="hero" id="home">
 <div>
  <div class="gold">THE WORLD OF CINEMA</div>
  <h1>Stories worth<br>
  <span class="gold">staying up for.</span></h1>
  <p>
   Discover Hindi, South Indian and Hollywood cinema
   in one place. Watch and download authorized movies.
  </p>
  <button class="btn"
   onclick="document.getElementById('movies').scrollIntoView()">
   Explore Movies
  </button>
 </div>
</section>

<div class="notice">
 <b>FOOD CINEMA:</b>
 Only movies with valid streaming and download
 permissions will be available. Sample movie cards
 are placeholders.
</div>

<section class="section" id="movies">
 <h2>Explore Movies</h2>

 <input class="search"
  id="search"
  placeholder="Search movies..."
  oninput="render()">

 <div class="filters">
  <button class="chip active" onclick="filter('All',this)">All</button>
  <button class="chip" onclick="filter('Hindi',this)">Hindi</button>
  <button class="chip" onclick="filter('South',this)">South Indian</button>
  <button class="chip" onclick="filter('Hollywood',this)">Hollywood</button>
 </div>

 <div class="grid" id="catalog"></div>
</section>

<section class="section" id="languages">
 <h2>Movies in Your Language</h2>
 <div class="earning">
  <div class="earn-card">
   🇮🇳 <b>Hindi Cinema</b>
   <p>Hindi movies and classics with proper permissions.</p>
  </div>
  <div class="earn-card">
   🎞️ <b>South Indian Cinema</b>
   <p>Telugu, Tamil, Malayalam and Kannada movies.</p>
  </div>
  <div class="earn-card">
   🌎 <b>Hollywood</b>
   <p>International and independent cinema.</p>
  </div>
 </div>
</section>

<section class="section" id="earn">
 <h2>Earn With FOOD CINEMA</h2>
 <div class="earning">
  <div class="earn-card">
   📺 <b>Advertising</b>
   <p>Earn through approved advertising partners.</p>
  </div>
  <div class="earn-card">
   👑 <b>Subscriptions</b>
   <p>Offer paid plans for a licensed movie catalogue.</p>
  </div>
  <div class="earn-card">
   🎟️ <b>Partnerships</b>
   <p>Work with authorized streaming services.</p>
  </div>
 </div>
</section>

</main>

<footer>
 © 2026 FOOD CINEMA. All rights reserved.
</footer>

<script>
const films = [
 {title:"Hindi Feature Slot",lang:"Hindi",emoji:"🎭"},
 {title:"Hindi Classics Slot",lang:"Hindi",emoji:"🎬"},
 {title:"Telugu Feature Slot",lang:"South",emoji:"🎥"},
 {title:"Tamil Feature Slot",lang:"South",emoji:"🎞️"},
 {title:"Malayalam Feature Slot",lang:"South",emoji:"🎭"},
 {title:"Kannada Feature Slot",lang:"South",emoji:"📽️"},
 {title:"Hollywood Feature Slot",lang:"Hollywood",emoji:"🌆"},
 {title:"Independent Film Slot",lang:"Hollywood",emoji:"⭐"}
];

let current = "All";

function filter(category,button) {
 current = category;
 document.querySelectorAll(".chip").forEach(
  b => b.classList.remove("active")
 );
 button.classList.add("active");
 render();
}

function render() {
 const q = document.getElementById("search").value.toLowerCase();

 const list = films.filter(f =>
  (current === "All" || f.lang === current) &&
  f.title.toLowerCase().includes(q)
 );

 document.getElementById("catalog").innerHTML =
 list.map(f => `
  <article class="movie">
   <div class="poster">${f.emoji}</div>
   <div class="movie-body">
    <h3>${f.title}</h3>
    <div class="meta">${f.lang} Cinema</div>
    <div class="movie-actions">
     <button class="btn"
      onclick="alert('Authorized movie playback link will be added here.')">
      ▶ Watch
     </button>
     <button class="btn"
      onclick="alert('Authorized download link will be added here.')">
      ↓ Download
     </button>
    </div>
   </div>
  </article>
 `).join("");
}

render();
</script>

</body>
</html>
