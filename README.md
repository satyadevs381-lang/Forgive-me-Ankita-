<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For Ankita ❤️</title>

<style>
*{
  box-sizing:border-box;
  margin:0;
  padding:0;
}

body{
  min-height:100vh;
  background:linear-gradient(135deg,#ffd9e8,#fff1f6);
  font-family:Arial,sans-serif;
  overflow:hidden;
  color:#743452;
}

.page{
  display:none;
  min-height:100vh;
  padding:35px 25px;
  text-align:center;
  align-items:center;
  justify-content:center;
  flex-direction:column;
  animation:fade .6s ease;
}

.page.active{
  display:flex;
}

.card{
  width:min(92%,600px);
  min-height:70vh;
  padding:45px 25px;
  border-radius:35px;
  background:rgba(255,255,255,.82);
  box-shadow:0 15px 45px rgba(120,50,85,.18);
  display:flex;
  flex-direction:column;
  justify-content:center;
  align-items:center;
}

h1{
  font-size:clamp(32px,8vw,58px);
  margin-bottom:25px;
}

p{
  font-size:clamp(20px,5vw,30px);
  line-height:1.6;
}

.heart{
  font-size:100px;
  animation:beat 1.2s infinite;
  margin-bottom:30px;
}

.shayari{
  font-size:21px;
  line-height:2;
  margin:20px 0;
}

button{
  margin-top:35px;
  padding:15px 35px;
  border:0;
  border-radius:50px;
  background:#d85b91;
  color:white;
  font-size:18px;
  cursor:pointer;
  box-shadow:0 8px 20px rgba(160,60,110,.25);
}

button:active{
  transform:scale(.95);
}

.small{
  margin-top:15px;
  font-size:15px;
  opacity:.7;
}

@keyframes fade{
  from{opacity:0;transform:translateY(20px)}
  to{opacity:1;transform:translateY(0)}
}

@keyframes beat{
  0%,100%{transform:scale(1)}
  50%{transform:scale(1.12)}
}
</style>
</head>

<body>

<!-- PAGE 1 -->
<section class="page active">
  <div class="card">
    <div class="heart">❤️</div>
    <h1>Ankita Sharma</h1>
    <p>Hey Ankita… 🥺</p>
    <button onclick="nextPage()">Swipe / Next ↑</button>
    <div class="small">Ek chhoti si baat kehni hai…</div>
  </div>
</section>

<!-- PAGE 2 -->
<section class="page">
  <div class="card">
    <div class="heart">🥺</div>
    <h1>I'm Really Sorry ❤️</h1>
    <p>Mujhse galti ho gayi…</p>
    <button onclick="nextPage()">Next ❤️</button>
  </div>
</section>

<!-- PAGE 3 -->
<section class="page">
  <div class="card">
    <div class="heart">💗</div>
    <h1>Please Forgive Me</h1>
    <p>Tumhe hurt karna mera intention kabhi nahi tha.</p>
    <button onclick="nextPage()">Next 🫶</button>
  </div>
</section>

<!-- PAGE 4 -->
<section class="page">
  <div class="card">
    <div class="heart">💕</div>
    <h1>I Love You, Ankita</h1>
    <p>Tum mere liye bahut special ho.</p>
    <button onclick="nextPage()">Next ❤️</button>
  </div>
</section>

<!-- PAGE 5 -->
<section class="page">
  <div class="card">
    <div class="heart">🌸</div>
    <h1>Ek Chhoti Si Shayari…</h1>

    <p class="shayari">
      Galti meri thi, dil se maanta hoon,<br>
      Tumhari narazgi bhi samajhta hoon.<br>
      Bas ek baar muskura do Ankita,<br>
      Tumhare bina main adhura sa lagta hoon. ❤️
    </p>

    <button onclick="nextPage()">Next 💗</button>
  </div>
</section>

<!-- PAGE 6 -->
<section class="page">
  <div class="card">
    <div class="heart">🫶</div>
    <h1>— Gaurav Sharma ❤️</h1>
    <p>
      Bas ek baar smile kar do…<br>
      Aur meri maafi accept kar lo. 🥺
    </p>
    <button onclick="restart()">Start Again ❤️</button>
  </div>
</section>

<script>
let currentPage = 0;
const pages = document.querySelectorAll(".page");

function showPage(index){
  pages.forEach(page => page.classList.remove("active"));
  pages[index].classList.add("active");
}

function nextPage(){
  if(currentPage < pages.length - 1){
    currentPage++;
    showPage(currentPage);
  }
}

function restart(){
  currentPage = 0;
  showPage(currentPage);
}

/* Swipe support */
let startY = 0;

document.addEventListener("touchstart", e => {
  startY = e.touches[0].clientY;
});

document.addEventListener("touchend", e => {
  let endY = e.changedTouches[0].clientY;

  if(startY - endY > 60){
    nextPage();
  }

  if(endY - startY > 60 && currentPage > 0){
    currentPage--;
    showPage(currentPage);
  }
});
</script>

</body>
</html>