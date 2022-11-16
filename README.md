# Space Game
------------------------------------------------
![a](/screen.PNG)

* 사진과 점수,사운드
```html
function startGame() {
    //우주선 사진이랑 배경 사진, 점수
    myGamePiece = new component(30, 30, "spaceship.png", 115, 440, "image");
    myBackground = new component(270, 656, "spacemap.jpg",0,0,"image")
    myScore = new component("30px", "Consolas", "black", 80, 40, "text");
    //사운드 추가
    
    mySound = new sound("boom.mp3");
    myMusic = new sound("space.mp3");
    //크롬은 사용자의 명시적인 액션이 없는 상태에서의 음원 재생을 허용하지 않는다.
    btnPlay.onclick = function () {
        myMusic.play();
    }
    myGameArea.start();
}
```
------------------------------------------------
* 벽 추가
```html
this.newPos = function() {
        this.x += this.speedX;
        this.y += this.speedY;
        this.hitBottom();
        this.hitleft();
        this.hitright();
    }
    //벽 안 넘어가게
    this.hitBottom = function() {
        var rockbottom = myGameArea.canvas.height - this.height;
        if (this.y > rockbottom) {
            this.y = rockbottom;
        }
    }

    this.hitleft = function(){
        var hitleft = myGameArea.canvas.width - myGameArea.canvas.width ;
        if (this.x < 0) {
            this.x = hitleft;
        }
    }

    this.hitright = function(){
        var hitright = myGameArea.canvas.width - this.width ;
        if (this.x > hitright) {
            this.x = hitright;
        }
    }
```
----------------------------------------------------
* 사운드 추가
```html
//사운드 추가
function sound(src) {
    this.sound = document.createElement("audio");
    this.sound.src = src;
    this.sound.setAttribute("preload", "auto");
    this.sound.setAttribute("controls", "none");
    this.sound.style.display = "none";
    document.body.appendChild(this.sound);
    this.play = function(){
        this.sound.play();
    }
    this.stop = function(){
        this.sound.pause();
    }    
}
```
--------------------------------------------------
* 키보드 입력 추가
//키보드 입력
```html
        window.addEventListener('keydown', function (e) {
            myGameArea.keys = (myGameArea.keys || []);
            myGameArea.keys[e.keyCode] = true;
        })
        window.addEventListener('keyup', function (e) {
            myGameArea.keys[e.keyCode] = false;
        })
        },
```
```html
 // 키보드 입력으로 속도 조절
    if (myGameArea.keys && myGameArea.keys[37]) {myGamePiece.speedX = -1.5; }
    if (myGameArea.keys && myGameArea.keys[39]) {myGamePiece.speedX = 1.5; }
    if (myGameArea.keys && myGameArea.keys[38]) {myGamePiece.speedY = -1.5; }
    if (myGameArea.keys && myGameArea.keys[40]) {myGamePiece.speedY = 1.5; }
```


-------------------------------------------------
* 게임 링크 : https://aestura.github.io/Aestura2.io/
* 참고 : https://www.w3schools.com/graphics/game_intro.asp
