# ...-..--.----..-.--.-
<!DOCTYPE html>
<html lang="mn">
<head>
<meta charset="UTF-8">
<title>For You</title>

<style>
body{
  margin:0;
  height:100vh;
  display:flex;
  justify-content:center;
  align-items:center;
  background:radial-gradient(circle at top,#ff5f8a,#8b0000);
  overflow:hidden;
  font-family:-apple-system;
}

/* Main heart */
#box{
  width:160px;
  height:140px;
  background:#ff1a1a;
  position:relative;
  transform:rotate(-45deg);
  cursor:pointer;
  animation:pulse 1.5s infinite;
}
#box:before,#box:after{
  content:"";
  width:160px;
  height:140px;
  background:#ff1a1a;
  border-radius:50%;
  position:absolute;
}
#box:before{top:-80px;left:0}
#box:after{left:80px;top:0}

@keyframes pulse{
  0%{transform:scale(1) rotate(-45deg)}
  50%{transform:scale(1.1) rotate(-45deg)}
  100%{transform:scale(1) rotate(-45deg)}
}

/* Message */
#msg{
  display:none;
  color:white;
  font-size:30px;
  font-weight:600;
  text-align:center;
  z-index:10;
}

/* Falling hearts */
.heart{
  position:fixed;
  top:-20px;
  font-size:20px;
  animation:fall linear forwards;
  color:rgba(255,255,255,.8);
}
@keyframes fall{
  to{transform:translateY(110vh);opacity:0}
}
</style>
</head>

<body>

<div id="box"></div>
<div id="msg"></div>

<audio id="music" src="music.mp3"></audio>

<script>
const text = "Suwdaa\nби чамд хайртай ❤️";
let i=0;

box.onclick = () =>{
  box.style.display="none";
  msg.style.display="block";
  music.play();
  type();
  setInterval(fallHeart,200);
}

function type(){
  if(i<text.length){
    msg.innerHTML += text[i]==="\n"?"<br>":text[i];
    i++;
    setTimeout(type,80);
  }
}

function fallHeart(){
  const h=document.createElement("div");
  h.className="heart";
  h.innerHTML="❤️";
  h.style.left=Math.random()*100+"vw";
  h.style.animationDuration=2+Math.random()*3+"s";
  document.body.appendChild(h);
  setTimeout(()=>h.remove(),5000);
}
</script>

body{
  margin:0;
  height:100vh;
  display:flex;
  justify-content:center;
  align-items:center;
  background:radial-gradient(circle at top,#ff5f8a,#8b0000);
  overflow:hidden;
  font-family:-apple-system;
}

/* wrapper fixes centering */
#wrapper{
  width:200px;
  height:200px;
  display:flex;
  justify-content:center;
  align-items:center;
}

/* heart */
#box{
  width:160px;
  height:140px;
  background:#ff1a1a;
  position:relative;
  transform:rotate(-45deg);
  cursor:pointer;
  animation:pulse 1.5s infinite;
}

#box:before,
#box:after{
  content:"";
  width:160px;
  height:140px;
  background:#ff1a1a;
  border-radius:50%;
  position:absolute;
}

#box:before{
  top:-70px;
  left:0;
}

#box:after{
  left:70px;
  top:0;
}
</html>
