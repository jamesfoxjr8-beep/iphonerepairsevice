[index.html](https://github.com/user-attachments/files/26695519/index.html)
# iphonerepairsevice\<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Phone Repair Service</title>

<style>
  body {
    margin: 0;
    font-family: Arial, sans-serif;
    background: #0f172a;
    color: white;
  }

  header {
    padding: 80px 20px;
    text-align: center;
    background: linear-gradient(135deg, #2563eb, #1e40af);
  }

  h1 { font-size: 42px; margin: 0; }

  /* 🔥 BUTTONS */
  .btn {
    padding: 12px 16px;
    margin: 6px;
    border-radius: 8px;
    border: none;
    cursor: pointer;
    font-weight: bold;
    background: #22c55e;
    color: white;
    transition: 0.25s ease;
    position: relative;
    overflow: hidden;

    box-shadow: 0 6px 15px rgba(0,0,0,0.35);
  }

  .btn:hover {
    transform: scale(1.05);
    box-shadow: 0 10px 25px rgba(0,0,0,0.55);
  }

  /* 🌊 RIPPLE */
  .ripple {
    position: absolute;
    border-radius: 50%;
    transform: scale(0);
    animation: rippleEffect 600ms ease-out;
    background-color: rgba(255,255,255,0.5);
    pointer-events: none;
  }

  @keyframes rippleEffect {
    to {
      transform: scale(4);
      opacity: 0;
    }
  }

  /* ✨ PAGE ANIMATION */
  section {
    padding: 40px 20px;
    max-width: 900px;
    margin: auto;

    display: none;
    opacity: 0;
    transform: translateY(10px);
    transition: 0.4s ease;
  }

  section.show {
    display: block;
    opacity: 1;
    transform: translateY(0);
  }

  .box {
    background: #1e293b;
    padding: 20px;
    border-radius: 12px;
    margin-top: 20px;
  }

  select, input, textarea {
    width: 100%;
    padding: 12px;
    margin-top: 10px;
    border-radius: 8px;
    border: none;
  }

  .price {
    font-size: 22px;
    color: #22c55e;
    margin-top: 15px;
    font-weight: bold;
  }

  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 15px;
  }

  .card {
    background: #1e293b;
    padding: 15px;
    border-radius: 12px;
  }
</style>
</head>

<body>

<header>
  <h1>Phone Repair Service</h1>
  <p>📧 jamesfoxjr8@gmail.com • Fast • Trusted • Affordable</p>

  <button class="btn" onclick="goHome()">🏠 Home</button>
  <button class="btn" onclick="goFix()">🔧 Fix My Phone</button>
  <button class="btn" onclick="goCheckout()">💳 Checkout</button>
</header>

<!-- HOME -->
<section id="home" class="show">

  <div class="box">
    <h2>⭐ Reviews</h2>
    <div class="grid">
      <div class="card">★★★★★ “Fast service!” – Jake</div>
      <div class="card">★★★★★ “Great prices!” – Sarah</div>
    </div>
  </div>

  <div class="box">
    <h2>📝 Leave a Review</h2>
    <input id="name" placeholder="Your name" />
    <textarea id="reviewText" placeholder="Write your review"></textarea>
    <button class="btn" onclick="addReview()">Submit Review</button>
  </div>

  <div class="box">
    <h2>📢 Customer Reviews</h2>
    <div id="reviewList">
      <p>⭐ “Great service!” – Mike</p>
    </div>
  </div>

  <div class="box">
    <h2>📍 Location</h2>
    <p><b>Ponchatoula, Louisiana 🇺🇸</b></p>
  </div>

  <div class="box" style="text-align:center;">
    <h2>📲 Website QR</h2>
    <img 
      src="https://api.qrserver.com/v1/create-qr-code/?size=220x220&data=https://phonerepairservice.netlify.app"
      style="width:220px; border-radius:12px;"
    />
  </div>

</section>

<!-- FIX -->
<section id="fixPage">

  <h2>🔧 Fix My Phone</h2>

  <div class="box">
    <select id="phone">
      <option value="">Choose iPhone</option>

      <option>iPhone X</option>
      <option>iPhone XR</option>
      <option>iPhone XS</option>
      <option>iPhone XS Max</option>

      <option>iPhone 11</option>
      <option>iPhone 11 Pro</option>
      <option>iPhone 11 Pro Max</option>

      <option>iPhone 12 Mini</option>
      <option>iPhone 12</option>
      <option>iPhone 12 Pro</option>
      <option>iPhone 12 Pro Max</option>

      <option>iPhone 13 Mini</option>
      <option>iPhone 13</option>
      <option>iPhone 13 Pro</option>
      <option>iPhone 13 Pro Max</option>

      <option>iPhone 14</option>
      <option>iPhone 14 Plus</option>
      <option>iPhone 14 Pro</option>
      <option>iPhone 14 Pro Max</option>

      <option>iPhone 15</option>
      <option>iPhone 15 Plus</option>
      <option>iPhone 15 Pro</option>
      <option>iPhone 15 Pro Max</option>

      <option>iPhone 16</option>
      <option>iPhone 16 Plus</option>
      <option>iPhone 16 Pro</option>
      <option>iPhone 16 Pro Max</option>

      <option>iPhone 17</option>
      <option>iPhone 17 Plus</option>
      <option>iPhone 17 Pro</option>
      <option>iPhone 17 Pro Max</option>
    </select>
  </div>

  <div class="box">
    <select id="repair">
      <option value="">Choose Repair</option>
      <option value="screen">Screen</option>
      <option value="battery">Battery</option>
      <option value="charging">Charging Port</option>
      <option value="camera">Camera</option>
    </select>
  </div>

  <div class="box">
    <button class="btn" onclick="calculate()">Check Price</button>
    <div class="price" id="result">Select options</div>
  </div>

</section>

<!-- CHECKOUT -->
<section id="checkoutPage">

  <h2>💳 Checkout</h2>

  <div class="box">
    <div class="price" id="checkoutTotal">Total: $0</div>
  </div>

  <div class="box" style="text-align:center;">
    <h3>📲 Cash App</h3>
    <p><b>$jamesfoxjr6</b></p>

    <img 
      src="https://api.qrserver.com/v1/create-qr-code/?size=220x220&data=https://cash.app/$jamesfoxjr6"
      style="width:220px; border-radius:12px;"
    />
  </div>

</section>

<audio id="clickSound" src="https://actions.google.com/sounds/v1/cartoon/pop.ogg"></audio>

<script>
let currentPrice = 0;
const sound = document.getElementById("clickSound");

function fx(){
  sound.currentTime = 0;
  sound.play();
  if(navigator.vibrate) navigator.vibrate(50);
}

/* NAV */
function showPage(id){
  document.querySelectorAll("section").forEach(s=>{
    s.classList.remove("show");
  });

  setTimeout(()=>{
    document.querySelectorAll("section").forEach(s=>{
      s.style.display = "none";
    });

    const page = document.getElementById(id);
    page.style.display = "block";

    setTimeout(()=>page.classList.add("show"),20);

  },200);

  fx();
}

function goHome(){ showPage("home"); }
function goFix(){ showPage("fixPage"); }
function goCheckout(){
  showPage("checkoutPage");
  document.getElementById("checkoutTotal").innerText = "Total: $" + currentPrice;
}

/* PRICE (FULL MODELS FIXED) */
function calculate(){
  fx();

  let phone = document.getElementById("phone").value;
  let repair = document.getElementById("repair").value;

  if(!phone || !repair){
    document.getElementById("result").innerText = "Select options";
    return;
  }

  let price = 60;

  if(repair==="screen") price+=50;
  if(repair==="battery") price+=30;
  if(repair==="charging") price+=25;
  if(repair==="camera") price+=35;

  if(phone.includes("X") || phone.includes("11")) price+=10;
  if(phone.includes("12")) price+=20;
  if(phone.includes("13")) price+=30;
  if(phone.includes("14")) price+=40;
  if(phone.includes("15")) price+=50;
  if(phone.includes("16")) price+=60;
  if(phone.includes("17")) price+=70;

  currentPrice = price;

  document.getElementById("result").innerText = "$" + price;
}

/* REVIEW */
function addReview(){
  fx();

  let name = document.getElementById("name").value;
  let text = document.getElementById("reviewText").value;

  if(!name || !text) return;

  let p = document.createElement("p");
  p.innerText = `⭐ "${text}" – ${name}`;
  document.getElementById("reviewList").prepend(p);

  document.getElementById("name").value = "";
  document.getElementById("reviewText").value = "";
}

/* RIPPLE */
document.querySelectorAll(".btn").forEach(btn=>{
  btn.addEventListener("click",function(e){
    const circle=document.createElement("span");
    const rect=this.getBoundingClientRect();
    const size=Math.max(rect.width,rect.height);

    circle.classList.add("ripple");
    circle.style.width=circle.style.height=size+"px";
    circle.style.left=(e.clientX-rect.left-size/2)+"px";
    circle.style.top=(e.clientY-rect.top-size/2)+"px";

    this.appendChild(circle);
    setTimeout(()=>circle.remove(),600);
  });
});
</script>

</body>
</html>
