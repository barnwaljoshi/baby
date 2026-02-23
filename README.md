<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Love Surprise</title>

<style>
body{
    margin:0;
    padding:0;
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    font-family:'Segoe UI',sans-serif;
    overflow:hidden;
    text-align:center;
    background: linear-gradient(135deg,#ff4e8a,#8e2de2);
}

.container{
    position:relative;
    padding:20px;
}

h1{
    color:white;
    font-size:28px;
    text-shadow:0 0 15px white;
}

button{
    padding:12px 25px;
    font-size:18px;
    border:none;
    border-radius:30px;
    cursor:pointer;
    margin:10px;
    transition:0.3s;
}

#yes{
    background:#ff2e63;
    color:white;
    box-shadow:0 0 20px #fff;
}

#yes:hover{
    transform:scale(1.1);
}

#no{
    background:#222;
    color:white;
    position:absolute;
}

#message{
    display:none;
    font-size:26px;
    color:white;
    margin-top:20px;
    animation: pop 1s ease forwards;
}

#signature{
    display:none;
    color:white;
    margin-top:10px;
    font-style:italic;
}

@keyframes pop{
    0%{transform:scale(0);}
    100%{transform:scale(1);}
}

.heart{
    position:absolute;
    font-size:24px;
    animation: floatUp 4s linear forwards;
}

@keyframes floatUp{
    0%{ transform:translateY(0); opacity:1;}
    100%{ transform:translateY(-120vh); opacity:0;}
}
</style>
</head>

<body>

<div class="container">
    <h1>Do you love me Priya Ji?</h1>
    <button id="yes">Yes</button>
    <button id="no">No</button>

    <div id="message">I LOVE YOU Priya Shivam Barnwal ❤️</div>
    <div id="signature">(~ your buggi)</div>
</div>

<script>
let noBtn = document.getElementById("no");
let yesBtn = document.getElementById("yes");
let message = document.getElementById("message");
let signature = document.getElementById("signature");

let hearts = ["❤️","💜","💖","💘"];

noBtn.addEventListener("mouseover", function(){
    let x = Math.random() * (window.innerWidth - 100);
    let y = Math.random() * (window.innerHeight - 100);
    noBtn.style.left = x + "px";
    noBtn.style.top = y + "px";
});

yesBtn.addEventListener("click", function(){

    message.style.display = "block";
    signature.style.display = "block";

    for(let i=0;i<40;i++){
        let heart = document.createElement("div");
        heart.classList.add("heart");
        heart.innerHTML = hearts[Math.floor(Math.random()*hearts.length)];
        heart.style.left = Math.random()*100 + "vw";
        heart.style.fontSize = (20 + Math.random()*30) + "px";
        heart.style.animationDuration = (3 + Math.random()*2) + "s";
        document.body.appendChild(heart);

        setTimeout(()=>{ heart.remove(); },5000);
    }
});
</script>

</body>
</html>
