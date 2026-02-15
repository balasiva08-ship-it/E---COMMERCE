<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Photo Wall</title>

<style>
body{
    margin:0;
    height:100vh;
    display:flex;
    justify-content:center;
    align-items:center;
    background:#f5f5f5;
    font-family:Arial, sans-serif;
}

.container{
    display:grid;
    grid-template-columns: repeat(5, 120px);
    grid-template-rows: repeat(3, 120px);
    gap:15px;
    justify-content:center;
    align-items:center;
}

/* All images */
.container div{
    background-size:cover;
    background-position:center;
    border:6px solid #111;
    box-shadow:0 4px 10px rgba(0,0,0,0.2);
}

/* Positioning like diamond layout */
.img1 { grid-column:3; grid-row:1; }
.img2 { grid-column:2; grid-row:2; }
.img3 { grid-column:3; grid-row:2; }
.img4 { grid-column:4; grid-row:2; }
.img5 { grid-column:3; grid-row:3; }

.img6 { grid-column:1; grid-row:2; }
.img7 { grid-column:5; grid-row:2; }
.img8 { grid-column:2; grid-row:3; }
.img9 { grid-column:4; grid-row:3; }

/* Make center image bigger */
.img3{
    width:150px;
    height:150px;
    z-index:2;
}

.container div:not(.img3){
    width:120px;
    height:120px;
}
</style>
</head>

<body>

<div class="container">
    <div class="img1" style="background-image:url('https://picsum.photos/300?1');"></div>
    <div class="img2" style="background-image:url('https://picsum.photos/300?2');"></div>
    <div class="img3" style="background-image:url('https://picsum.photos/300?3');"></div>
    <div class="img4" style="background-image:url('https://picsum.photos/300?4');"></div>
    <div class="img5" style="background-image:url('https://picsum.photos/300?5');"></div>
    <div class="img6" style="background-image:url('https://picsum.photos/300?6');"></div>
    <div class="img7" style="background-image:url('https://picsum.photos/300?7');"></div>
    <div class="img8" style="background-image:url('https://picsum.photos/300?8');"></div>
    <div class="img9" style="background-image:url('https://picsum.photos/300?9');"></div>
</div>

</body>
</html>
