<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>6 Side Cube</title>
       <style>
        *{margin: 0; padding: 0; box-sizing: border-box;}
        body{
            display: flex;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            background:  #000;
        }
        .cube{
            position: relative;
            width: 300px;
            height: 300px;
            transform-style: preserve-3d;
            transform: rotateX(-25deg);
            animation: rotate 4s linear infinite;
            background: linear-gradient(red, yellow);
            border-radius: 50%;
        }
        @keyframes rotate{
            0%{transform: rotateX(-25deg) rotateY(-360deg);}  
        }
        .cube::after{
            content: '';
            position: absolute;
            width: 80%;
            height: 50%;
            background: linear-gradient(yellow, red);
            border-radius: 50%;
            filter: blur(30px);
            top: 420px;
            opacity: .8;
        }
        .side_wrapper{
            position:absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            transform-style: preserve-3d;
        }
        .side_wrapper span{
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            background: linear-gradient(#151515, #00ec00);
            transform: rotateY(calc(60deg * var(--i))) translateZ(259px);
            animation: blur 4s linear infinite;
        }
        .top{
            position: absolute;
            top: 300px;
            left: -105px; 
            width: 525px;
            height: 525px;
            background: #00ec00;
            transform: rotateX(90deg) translateZ(150px);
            filter: blur(200px);
            position: relative;
            animation: blur 4s linear infinite;
        }
        @keyframes blur {
            0%{opacity: 1;}
            50%{opacity: .5;}
            100%{opacity: 1;}
        }
        h1{
           color:white;
           text-align:center;
           vertical-align: -25deg;
        }

    </style>
 
</head>
<body>
  
    <div class="cube">
        <div class="top"></div>
        <div class="side_wrapper">
            <span style="--i:0;"></span>
            <span style="--i:1;"></span>
            <span style="--i:2;"></span>
            <span style="--i:3;"></span>
            <span style="--i:4;"></span>
            <span style="--i:5;"></span>
        </div>
    </div>  
</body>
</html>
