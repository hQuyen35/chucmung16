# chucmung16
<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>1/6 Vui Vẻ</title>

<style>

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial,sans-serif;
}

body{
    overflow:hidden;
}

.page{
    width:100vw;
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    flex-direction:column;
}

/* ===== TRANG 1 ===== */

#page1{
    background:url("nen1.jpg") center center/cover no-repeat;
}

.btn{
    padding:18px 35px;
    border:none;
    border-radius:40px;
    font-size:22px;
    cursor:pointer;
    background:white;
    box-shadow:0 0 15px rgba(0,0,0,.2);
}

#dogText{
    display:none;
    margin-top:20px;
    font-size:32px;
    color:white;
    font-weight:bold;
    text-shadow:0 0 10px black;
}

/* ===== TRANG 2 ===== */

#page2{
    display:none;
    background:linear-gradient(
    135deg,
    #ff9a9e,
    #fad0c4,
    #ffd1ff);
    text-align:center;
    padding:30px;
    overflow:hidden;
}

h1{
    font-size:50px;
    margin-bottom:20px;
}

.message{
    max-width:800px;
    font-size:24px;
    line-height:1.8;
}

.nextBtn{
    margin-top:40px;
}

/* ===== TRANG 3 ===== */

#page3{
    display:none;
    background:#fff7fb;
    overflow-y:auto;
    padding:40px;
}

.gallery{
    display:grid;
    grid-template-columns:
    repeat(auto-fit,minmax(250px,1fr));
    gap:20px;
    width:100%;
}

.gallery img{
    width:100%;
    border-radius:20px;
    cursor:pointer;
    transition:.3s;
}

.gallery img:hover{
    transform:scale(1.05);
}

/* hoa rơi */

.flower{
    position:fixed;
    top:-20px;
    animation:fall linear forwards;
    z-index:999;
}

@keyframes fall{
    to{
        transform:
        translateY(110vh)
        rotate(360deg);
    }
}

</style>
</head>

<body>

<audio id="music" loop>
<source src="nhac.mp3" type="audio/mpeg">
</audio>

<!-- TRANG 1 -->

<div id="page1" class="page">

<button class="btn" onclick="startShow()">
Sẵn sàng chưa?
</button>

<div id="dogText">
Ấn vào sẽ là 🐶
</div>

</div>

<!-- TRANG 2 -->

<div id="page2" class="page">

<h1>🎉 Chúc Mừng 1/6 🎉</h1>

<div class="message">

🌷 Chúc bạn có một ngày thật vui vẻ.<br>

✨ Luôn hạnh phúc.<br>

💖 Luôn được yêu thương.<br>

🎁 Luôn gặp thật nhiều điều tốt đẹp.<br>

🌈 Mong mọi điều bạn mong muốn đều sẽ thành hiện thực.<br>

😊 Và nhớ cười thật nhiều nhé!

</div>

<button class="btn nextBtn"
onclick="openAlbum()">

Tiếp tục không nào?

</button>

</div>

<!-- TRANG 3 -->

<div id="page3" class="page">

<h1 style="margin-bottom:30px">
📸 Album Kỷ Niệm
</h1>

<div class="gallery">

<img src="album1.jpg">

<img src="album2.jpg">

<img src="album3.jpg">

<img src="album4.jpg">

</div>

</div>

<script>

function startShow(){

document.getElementById("music").play();

document.querySelector(".btn").style.display="none";

let dog=document.getElementById("dogText");

dog.style.display="block";

setTimeout(()=>{

document.getElementById("page1").style.display="none";

document.getElementById("page2").style.display="flex";

createFlowers();

},3000);

}

function openAlbum(){

document.getElementById("page2").style.display="none";

document.getElementById("page3").style.display="flex";

}

function createFlowers(){

setInterval(()=>{

const flower=document.createElement("div");

flower.className="flower";

const items=[
"🌸",
"💖",
"✨",
"🎊",
"🎉"
];

flower.innerHTML=
items[Math.floor(
Math.random()*items.length
)];

flower.style.left=
Math.random()*100+"vw";

flower.style.fontSize=
(Math.random()*20+20)+"px";

flower.style.animationDuration=
(Math.random()*5+5)+"s";

document.body.appendChild(flower);

setTimeout(()=>{
flower.remove();
},10000);

},200);

}

</script>

</body>
</html>
