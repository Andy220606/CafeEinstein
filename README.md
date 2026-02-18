<!DOCTYPE html>
<html lang="da">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Café Einstein</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600&family=Inter:wght@300;400;500&display=swap" rel="stylesheet">
<style>
body { margin:0; font-family:'Inter',sans-serif; background:#0e0e0e; color:#f4efe6; scroll-behavior:smooth; }
nav { position:fixed; top:0; width:100%; background:rgba(0,0,0,0.85); padding:15px 40px; display:flex; justify-content:space-between; z-index:1000; }
nav a { color:#f4efe6; text-decoration:none; margin-left:20px; font-size:14px; }
.hero { height:100vh; display:flex; flex-direction:column; justify-content:center; align-items:center; text-align:center; background:linear-gradient(rgba(0,0,0,0.6),rgba(0,0,0,0.7)),url('https://images.unsplash.com/photo-1504674900247-0877df9cc836'); background-size:cover; background-position:center; }
h1 { font-family:'Playfair Display',serif; font-size:64px; margin:0; }
.hero p { font-size:22px; margin-top:15px; }
.btn { margin-top:25px; padding:14px 30px; background:#b08d57; border:none; border-radius:30px; color:white; cursor:pointer; }
section { padding:100px 40px; max-width:1200px; margin:auto; }
h2 { font-family:'Playfair Display',serif; font-size:36px; margin-bottom:30px; }
.grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(280px,1fr)); gap:30px; }
.card { background:#1a1a1a; padding:30px; border-radius:15px; box-shadow:0 15px 35px rgba(0,0,0,0.4); }
.gallery { display:grid; grid-template-columns:repeat(auto-fit,minmax(250px,1fr)); gap:20px; }
.gallery img { width:100%; border-radius:15px; }
form { display:grid; gap:15px; }
input,select,textarea { padding:12px; border-radius:8px; border:none; }
footer { background:#000; text-align:center; padding:40px; }
.cookie-banner { position:fixed; bottom:0; width:100%; background:#1a1a1a; padding:20px; display:flex; justify-content:space-between; align-items:center; z-index:1000; }
.chatbot { position:fixed; bottom:90px; right:20px; width:320px; background:#1a1a1a; border-radius:15px; box-shadow:0 10px 30px rgba(0,0,0,0.5); display:flex; flex-direction:column; overflow:hidden; z-index:1001; }
.chatbot-header { background:#b08d57; padding:10px; font-weight:bold; }
.chatbot-messages { padding:15px; height:250px; overflow-y:auto; font-size:14px; color:white; }
.chatbot-input { display:flex; }
.chatbot-input input { flex:1; border:none; padding:10px; border-radius:0; }
.chatbot-input button { border:none; background:#b08d57; color:white; padding:10px; cursor:pointer; }
</style>
</head>
<body>

<nav>
<div><strong>Café Einstein</strong></div>
<div>
<a href="#om">Om</a>
<a href="#events">Events</a>
<a href="#menu">Menu</a>
<a href="#booking">Booking</a>
</div>
</nav>

<div class="hero">
<h1>Café Einstein</h1>
<p>Mad, Musik og Mennesker</p>
<button class="btn" onclick="document.getElementById('booking').scrollIntoView()">Book Bord</button>
</div>

<section id="om">
<h2>Om os</h2>
<p>En stemningsfuld café med gastronomi, jazz og kulturelle aftener. Vi tilbyder både intime middage og professionelle arrangementer for virksomheder og private.</p>
</section>

<section id="events">
<h2>Events</h2>
<div class="grid">
<div class="card"><h3>Jazz Nights</h3><p>Live jazz i eksklusive omgivelser.</p></div>
<div class="card"><h3>Stand-up</h3><p>Comedy og middag i perfekt kombination.</p></div>
<div class="card"><h3>Private Events</h3><p>Konfirmationer, firmaarrangementer og mindesammenkomster.</p></div>
</div>
</section>

<section id="menu">
<h2>Udvalgt Menu</h2>
<div class="grid">
<div class="card"><h3>Forret</h3><p>Sæsonens suppe – 95 kr</p></div>
<div class="card"><h3>Hovedret</h3><p>Braiseret kalv med rodfrugter – 225 kr</p></div>
<div class="card"><h3>Dessert</h3><p>Chokolademousse med bær – 85 kr</p></div>
</div>
</section>

<section>
<h2>Galleri</h2>
<div class="gallery">
<img src="https://images.unsplash.com/photo-1559339352-11d035aa65de">
<img src="https://images.unsplash.com/photo-1528605248644-14dd04022da1">
<img src="https://images.unsplash.com/photo-1470337458703-46ad1756a187">
</div>
</section>

<section id="booking">
<h2>Booking</h2>
<form action="https://formspree.io/f/your-form-id" method="POST">
<select name="type" required>
<option value="">Type af booking</option>
<option>Bordreservation</option>
<option>Firmaarrangement</option>
<option>Privat arrangement</option>
</select>
<input type="text" name="name" placeholder="Fulde navn" required>
<input type="email" name="email" placeholder="E-mail" required>
<input type="tel" name="phone" placeholder="Telefonnummer" required>
<input type="date" name="date" required>
<input type="time" name="time" required>
<input type="number" name="guests" placeholder="Antal gæster" required>
<textarea name="message" placeholder="Særlige ønsker"></textarea>
<button class="btn" type="submit">Send forespørgsel</button>
</form>
</section>

<footer>
<p>Café Einstein | Adresse | Telefon | kontakt@cafeeinstein.dk</p>
</footer>

<div class="cookie-banner" id="cookieBanner">
<div>Vi bruger cookies til statistik og forbedring af oplevelsen.</div>
<div>
<button onclick="acceptCookies()">Accepter</button>
<button onclick="declineCookies()">Afvis</button>
</div>
</div>

<div class="chatbot" id="chatbot">
<div class="chatbot-header">Einstein Assistent</div>
<div class="chatbot-messages" id="chatMessages">
<div>Hej 👋 Hvordan kan jeg hjælpe dig?</div>
</div>
<div class="chatbot-input">
<input type="text" id="chatInput" placeholder="Skriv dit spørgsmål...">
<button onclick="sendMessage()">Send</button>
</div>
</div>

<script>
function acceptCookies(){localStorage.setItem('cookiesAccepted','true');document.getElementById('cookieBanner').style.display='none';}
function declineCookies(){localStorage.setItem('cookiesAccepted','false');document.getElementById('cookieBanner').style.display='none';}
if(localStorage.getItem('cookiesAccepted')){document.getElementById('cookieBanner').style.display='none';}

async function sendMessage(){
let input=document.getElementById('chatInput');
let messages=document.getElementById('chatMessages');
let userText=input.value;
if(!userText) return;
messages.innerHTML+=`<div><strong>Du:</strong> ${userText}</div>`;
input.value="";
messages.scrollTop=messages.scrollHeight;
messages.innerHTML+=`<div id="typing"><em>Einstein tænker...</em></div>`;
messages.scrollTop=messages.scrollHeight;
try {
const response = await fetch("/api/chat", {
method: "POST",
headers: { "Content-Type": "application/json" },
body: JSON.stringify({ message: userText })
});
const data = await response.json();
document.getElementById("typing").remove();
messages.innerHTML+=`<div><strong>Einstein:</strong> ${data.reply}</div>`;
messages.scrollTop=messages.scrollHeight;
} catch (error) {
document.getElementById("typing").remove();
messages.innerHTML+=`<div><strong>Einstein:</strong> Der opstod en fejl. Prøv igen senere.</div>`;
}
}
</script>

</body>
</html>
