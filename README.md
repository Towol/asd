<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>예약센터</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

body{
    font-family:'Segoe UI',sans-serif;
    background:#f5f7fa;
}

header{
    background:#1e293b;
    color:white;
    padding:20px 50px;
    display:flex;
    justify-content:space-between;
    align-items:center;
}

.logo{
    font-size:24px;
    font-weight:bold;
}

nav a{
    color:white;
    text-decoration:none;
    margin-left:20px;
}

.hero{
    height:500px;
    background:linear-gradient(
    rgba(0,0,0,0.5),
    rgba(0,0,0,0.5)),
    url("https://images.unsplash.com/photo-1497366754035-f200968a6e72?q=80&w=1400");
    background-size:cover;
    background-position:center;
    display:flex;
    justify-content:center;
    align-items:center;
    text-align:center;
    color:white;
}

.hero h1{
    font-size:50px;
    margin-bottom:20px;
}

.hero p{
    font-size:20px;
    margin-bottom:30px;
}

.btn{
    background:#2563eb;
    color:white;
    padding:15px 30px;
    border:none;
    border-radius:8px;
    text-decoration:none;
}

.section{
    max-width:1200px;
    margin:auto;
    padding:80px 20px;
}

.cards{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
    gap:20px;
}

.card{
    background:white;
    padding:25px;
    border-radius:12px;
    box-shadow:0 3px 10px rgba(0,0,0,.1);
}

.booking{
    background:white;
    max-width:600px;
    margin:auto;
    padding:30px;
    border-radius:12px;
    box-shadow:0 3px 10px rgba(0,0,0,.1);
}

.booking input,
.booking button{
    width:100%;
    padding:12px;
    margin-top:10px;
}

.booking button{
    background:#2563eb;
    color:white;
    border:none;
    cursor:pointer;
}

footer{
    background:#1e293b;
    color:white;
    text-align:center;
    padding:30px;
}
</style>
</head>
<body>

<header>
    <div class="logo">예약센터</div>

    <nav>
        <a href="#about">소개</a>
        <a href="#service">서비스</a>
        <a href="#reserve">예약</a>
    </nav>
</header>

<section class="hero">
    <div>
        <h1>온라인 예약 시스템</h1>
        <p>언제 어디서나 간편하게 예약하세요</p>
        <a href="#reserve" class="btn">지금 예약하기</a>
    </div>
</section>

<section class="section" id="about">
    <h2>회사 소개</h2>
    <br>
    <p>
        고객을 위한 빠르고 편리한 예약 서비스를 제공합니다.
    </p>
</section>

<section class="section" id="service">
    <h2>서비스</h2>
    <br>

    <div class="cards">

        <div class="card">
            <h3>실시간 예약</h3>
            <p>간편한 예약 접수</p>
        </div>

        <div class="card">
            <h3>예약 관리</h3>
            <p>관리자가 쉽게 확인</p>
        </div>

        <div class="card">
            <h3>모바일 지원</h3>
            <p>휴대폰에서도 사용 가능</p>
        </div>

    </div>
</section>

<section class="section" id="reserve">

    <div class="booking">

        <h2>예약하기</h2>

        <input type="text" id="name" placeholder="이름">

        <input type="date" id="date">

        <button onclick="reserve()">
            예약 신청
        </button>

    </div>

</section>

<footer>
    © 2026 예약센터
</footer>

<script>
function reserve(){

    const name =
        document.getElementById("name").value;

    const date =
        document.getElementById("date").value;

    if(!name || !date){
        alert("모든 항목을 입력하세요.");
        return;
    }

    let reservations =
    JSON.parse(localStorage.getItem("reservations"))
    || [];

    reservations.push({
        name,
        date
    });

    localStorage.setItem(
        "reservations",
        JSON.stringify(reservations)
    );

    alert("예약이 완료되었습니다.");
}
</script>

</body>
</html>
