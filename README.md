# Circle-to-square-animation
 .......HTML..........
 <!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>repl.it</title>
    <link href="style.css" rel="stylesheet" type="text/css" />
  </head>
  body>  
  <div class="circle">
    <div></div>
    <div></div>
    <div></div>
    <div></div>
    <div></div>
    </div> 
  <div class="big">
    <div></div>
    <div></div>
    <div></div>
    <div></div>
    <div></div>
  </div>
  <div class="tri"></div>
  <div class="squ">
    <div></div>
    <div></div>
    <div></div>
    <div></div>
  </div>
  <div class="fun">
    <div>F</div>
    <div>U</div>
    <div>N</div>
  </div>
  </body>
</html>
.................css..............
@charset "UTF-8";
/*********** reset **********/
html,
body,
div {
  margin:0;
  padding:0;
  border:0;
}

/* ------------------------------------------------------ */
html,
body {
  position: relative;
  width: 100vw;
  height: 100vh;
  overflow: hidden;
}

/* -----------------------
animation circle 回る玉 ~4s
----------------------- */
.circle {
  position: absolute;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background: #00ffff;
}

.circle div {
  position: absolute;
  top: calc((50% - 10px));
  left: calc((50% - 10px));
  width: 20px;
  height:20px;
  background: #ffe4c4;
  border-radius: 50%;
}

.circle div:nth-child(1) { animation: anim_01 2s forwards;}
.circle div:nth-child(2) { animation: move_01 2s 2s; }
.circle div:nth-child(4) { animation: move_03 2s 2s; }
.circle div:nth-child(3) { animation: move_02 2s 2s; }
.circle div:nth-child(5) { animation: move_04 2s 2s; }

@keyframes anim_01 {
  0% {   transform: scale(0);}
  20% {  transform: scale(3);}
  50% {  transform: scale(1);}
  90% {  transform: scale(5);}
  100% { transform: scale(0);}
}

@keyframes move_01 {
  0% {   transform: translate(0) scale(0);}
  20% {  transform: translate(-100px, -100px) scale(1);}
  40% {  transform: translate(-100px, 100px) scale(1);}
  60% {  transform: translate(100px, 100px) scale(1);}
  80% {  transform: translate(100px, -100px) scale(1);}
  100% { transform: translate(0) scale(1);}
}

@keyframes move_02 {
  0% {   transform: translate(0) scale(0);}
  20% {  transform: translate(-100px, 100px) scale(1);}
  40% {  transform: translate(100px, 100px) scale(1);}
  60% {  transform: translate(100px, -100px) scale(1);}
  80% {  transform: translate(-100px, -100px) scale(1);}
  100% { transform: translate(0) scale(1);}
}

@keyframes move_03 {
  0% {   transform: translate(0px) scale(0);}
  20% {  transform: translate(100px, 100px) scale(1);}
  40% {  transform: translate(100px, -100px) scale(1);}
  60% {  transform: translate(-100px, -100px) scale(1);}
  80% {  transform: translate(-100px, 100px) scale(1);}
  100% { transform: translate(0) scale(1);}
}

@keyframes move_04 {
  0% {   transform: translate(0px) scale(0);}
  20% {  transform: translate(100px, -100px) scale(1);}
  40% {  transform: translate(-100px, -100px) scale(1);}
  60% {  transform: translate(-100px, 100px) scale(1);}
  80% {  transform: translate(100px, 100px) scale(1);}
  100% { transform: translate(0) scale(1);}
}

/* -----------------------
animation big 広がる玉 4s~5.6s
----------------------- */
.big {
  position: absolute;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
}
.big div{
  position: absolute;
  top: calc((50% - 1500px));
  left: calc((50% - 1500px));
  width: 3000px;
  height: 3000px;
  border-radius: 50%;
  transform: scale(0);
}

.big div:nth-child(1) { background: #d2691e; animation: big .5s 4s forwards;}
.big div:nth-child(2) { background: #afeeee; animation: big .5s 4.5s forwards;}
.big div:nth-child(3) { background: #d8bfd8;  animation: big .5s 5s forwards;}

@keyframes big {
  0% {  transform: scale(0);}
  100% {transform: scale(1);}
}

/* -----------------------
animation tri 突き上げる三角 ~5.9s
----------------------- */
.tri {
  position: absolute;
  bottom: -300vw;
  left: -100vw;
  width: 0;
  height: 0;
  border-left: 150vw solid rgba(56, 240, 19, 0);
  border-right: 150vw solid rgba(255, 0, 0, 0);
  border-bottom: 300vw solid  rgb(255, 251, 189);
  animation: tri .6s 5.3s linear forwards;
}

@keyframes tri {
  100% {transform: translateY(-300vw); }
}

/* -----------------------
animation squ 現れる四角 7.3s
----------------------- */
.squ {
  position: absolute;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
}

.squ div {
  position: absolute;
  top: calc((50% - 50px));
  left: calc((50% - 50px));
  width: 100px;
  height:100px;
  background: #1589FF;
  border-radius: 50%;
  transform: scale(0);
}

.squ div:nth-child(1) { animation: squ .6s 5.8s cubic-bezier(0, 0.73, 0.54, 2.4) forwards;}
.squ div:nth-child(2) { animation: moveSqu_01 .8s 6.5s forwards;}
.squ div:nth-child(3) { animation: moveSqu_02 .8s 6.5s forwards;}
.squ div:nth-child(4) { animation: moveSqu_03 .8s 6.5s forwards;}

@keyframes squ {
  0% {   transform: translateY(100px) scale(0);}
  20% {  transform: translateY(100px) scale(1);}
  99% {  transform: translateY(0) scale(1);}
  100% { transform: translateY(0) scale(0);}
}

@keyframes moveSqu_01 {
  0% {   transform: translateX(0);}
  100% { transform: translateX(-300px); border-radius: 0;}
}

@keyframes moveSqu_02 {
  0% {   transform: translateX(0);}
  100% { transform: translateX(0px); border-radius: 0;}
}

@keyframes moveSqu_03 {
  0% {   transform: translateX(0);}
  100% { transform: translateX(300px); border-radius: 0;}
}

/* -----------------------
animation end  
----------------------- */
.fun {
  position: absolute;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
}

.fun div {
  position: absolute;
  top: calc((50% - 50px));
  left: calc((50% - 50px));
  width: 100px;
  height:100px;
  font-size: 70px;
  color: #8AFB17;
  line-height: 100px;
  text-align: center;
  opacity: 0;
  animation: end 1s 7.4s forwards;
}

.fun div:nth-child(1) {
  transform: translateX(-300px);
}

.fun div:nth-child(3) {
  transform: translateX(300px);
}

@keyframes end {
  100% { opacity: 1;}
}























