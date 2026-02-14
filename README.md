<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For Mihira ❤️</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
<style>
*{
  margin:0;
  padding:0;
  box-sizing:border-box;
  font-family:'Poppins', sans-serif;
}

body{
  height:100vh;
  overflow:hidden;
  background: linear-gradient(135deg, #ffd6e8, #ffeaf4, #ffc2dd);
  display:flex;
  justify-content:center;
  align-items:center;
  text-align:center;
  position:relative;
}

/* Floating hearts */
body::before{
  content:"❤️ ❤️ ❤️ ❤️ ❤️ ❤️ ❤️ ❤️ ❤️ ❤️";
  position:absolute;
  font-size:20px;
  opacity:0.08;
  animation: float 20s linear infinite;
}
@keyframes float{
  0%{transform:translateY(100vh);}
  100%{transform:translateY(-100vh);}
}

.container{
  width:90%;
  max-width:600px;
  padding:30px;
  background:rgba(255,255,255,0.85);
  border-radius:20px;
  box-shadow:0 10px 30px rgba(0,0,0,0.1);
  position:relative;
  transition:opacity 0.5s ease, transform 0.5s ease;
}

.hidden{
  display:none;
}

h1{
  font-size:1.8rem;
  margin-bottom:20px;
  color:#d63384;
}

p{
  font-size:1rem;
  margin-bottom:20px;
  color:#444;
  line-height:1.6;
}

button{
  padding:10px 20px;
  border:none;
  border-radius:25px;
  margin:10px;
  cursor:pointer;
  font-size:1rem;
  transition:0.3s;
}

.yes-btn{
  background:#ff4d88;
  color:white;
}

button:hover{
  transform:scale(1.1);
}

/* Popups */
.popup, #finalPopup{
  position:fixed;
  top:50%;
  left:50%;
  transform:translate(-50%, -50%);
  background:white;
  padding:25px 30px;
  border-radius:20px;
  box-shadow:0 10px 25px rgba(0,0,0,0.2);
  display:none;
  text-align:center;
  z-index:100;
}

#finalPopup h1{
  font-size:2.5rem;
  color:#d63384;
  margin-bottom:15px;
  animation:popText 1.5s ease forwards;
}

#finalPopup p{
  font-size:1.2rem;
  margin-bottom:15px;
  animation:fadeInText 2s ease forwards;
}

@keyframes popText{
  0%{transform:scale(0); opacity:0;}
  60%{transform:scale(1.2);}
  100%{transform:scale(1); opacity:1;}
}

@keyframes fadeInText{
  from{opacity:0; transform:translateY(20px);}
  to{opacity:1; transform:translateY(0);}
}

/* Rose petals */
.petal{
  position:fixed;
  top:-20px;
  width:12px;
  height:18px;
  background:#ff4d6d;
  border-radius:50% 50% 50% 0;
  transform:rotate(45deg);
  opacity:0.8;
  animation:fall linear forwards;
}
@keyframes fall{
  to{transform:translateY(110vh) rotate(360deg);}
}

/* Dog gifs */
.dog{
  width:120px;
  margin-top:15px;
}

@media(max-width:500px){
  h1{font-size:1.4rem;}
  p{font-size:0.9rem;}
}
</style>
</head>
<body>

<!-- Page 1 -->
<div class="container" id="page1">
  <h1>Hello Mihira ❤️</h1>
  <p>
    Your so-called boyfriend has something to tell you this Valentine’s Day…  
    Would you like to proceed? 🥺
  </p>
  <button class="yes-btn" onclick="nextPage(2)">Yes</button>
  <button class="no-btn" id="noBtn">No</button>
  <img class="dog" src="https://media.giphy.com/media/MDJ9IbxxvDUQM/giphy.gif">
</div>

<!-- Page 2 -->
<div class="container hidden" id="page2">
  <h1>Before I Ask You Something… 💌</h1>
  <p>
    These last two or three months have been a little crazy.  
    There has been a huge shift in the dynamics of our relationship.  
    Things changed. Our perceptions changed. And so much more.  

    But out of everything that has happened in these past few months,  
    <b>you</b> are the best thing that has happened to me in a very long time.  

    I know I’m not the most perfect guy in the world,  
    but I’m trying every day to become better.  

    I love your energy, your aura, your voice, your smile,  
    your eyes, your nose… and yes, the rest of your beautiful face too.  

    I have thought about this a lot,  
    and I’ve never been more sure about anything than I am about this.  

    I may not be there with you physically,  
    but I hope you can feel my presence when you read this,  
    the way I feel yours while drafting these words.  

    So without making this any longer…
  </p>
  <button onclick="showPopup()">Continue 💖</button>
  <img class="dog" src="https://media.giphy.com/media/l0MYt5jPR6QX5pnqM/giphy.gif">
</div>

<!-- Popup -->
<div class="popup" id="popup">
  <p>“Kanivudan adutha pakkathukku ennai azhuthavum.” 💞</p>
  <button onclick="nextPage(3)">Open</button>
</div>

<!-- Page 3 -->
<div class="container hidden" id="page3">
  <h1>Will You Be My Valentine? 💍💖</h1>
  <button class="yes-btn" onclick="showFinalPopup()">Yes</button>
  <button class="yes-btn" onclick="showFinalPopup()">Aama</button>
  <button class="yes-btn" onclick="showFinalPopup()">Avunu</button>
  <img class="dog" src="https://media.giphy.com/media/3oriO0OEd9QIDdllqo/giphy.gif">
</div>

<!-- Final Popup -->
<div id="finalPopup">
  <h1>I Love U Mihi ❤️</h1>
  <p>And trust me… choosing me will be the best decision you ever made.</p>
</div>

<script>
function nextPage(page){
  document.getElementById("page1").classList.add("hidden");
  document.getElementById("page2").classList.add("hidden");
  document.getElementById("page3").classList.add("hidden");
  document.getElementById("page"+page).classList.remove("hidden");
  document.getElementById("popup").style.display="none";
}

/* Show middle popup */
function showPopup(){
  document.getElementById("popup").style.display="block";
}

/* Final popup */
function showFinalPopup(){
  for(let i=0;i<30;i++){
    createPetal(i*100);
  }
  setTimeout(()=>{
    document.getElementById("finalPopup").style.display="block";
  },500);
}

/* Rose petals */
function createPetal(delay){
  setTimeout(()=>{
    const petal=document.createElement("div");
    petal.classList.add("petal");
    petal.style.left=Math.random()*100+"vw";
    petal.style.animationDuration=(Math.random()*4+4)+"s";
    document.body.appendChild(petal);
    setTimeout(()=>petal.remove(),8000);
  },delay);
}

/* Make No button run away */
const noBtn = document.getElementById("noBtn");
noBtn.addEventListener("mouseover", function(){
  const x = Math.random() * (window.innerWidth - 100);
  const y = Math.random() * (window.innerHeight - 50);
  noBtn.style.left = x + "px";
  noBtn.style.top = y + "px";
});
</script>

</body>
</html>
