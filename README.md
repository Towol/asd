# asd
dsa

<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<title>예약하기</title>
<style>
body{
    font-family: Arial;
    max-width:500px;
    margin:50px auto;
}
input,button{
    width:100%;
    padding:10px;
    margin:5px 0;
}
button{
    background:#007bff;
    color:white;
    border:none;
}
</style>
</head>
<body>

<h1>예약하기</h1>

<input type="text" id="name" placeholder="이름">
<input type="date" id="date">
<button onclick="reserve()">예약하기</button>

<p>
<a href="admin.html">관리자 페이지</a>
</p>

<script>
function reserve() {
    const name = document.getElementById('name').value;
    const date = document.getElementById('date').value;

    if(!name || !date){
        alert('모든 항목을 입력하세요.');
        return;
    }

    let reservations =
        JSON.parse(localStorage.getItem('reservations')) || [];

    reservations.push({
        name,
        date
    });

    localStorage.setItem(
        'reservations',
        JSON.stringify(reservations)
    );

    alert('예약 완료!');
}
</script>

</body>
</html>
