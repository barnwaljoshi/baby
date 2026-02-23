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
