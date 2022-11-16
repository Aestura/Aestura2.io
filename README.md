# Space Game
------------------------------------------------
![a](/screen.PNG)


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



-------------------------------------------------
* 게임 링크 : https://aestura.github.io/Aestura2.io/
* 참고 : https://www.w3schools.com/graphics/game_intro.asp
