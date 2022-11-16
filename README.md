# Space Game
------------------------------------------------
![a](/screen.PNG)


```HTML
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

-------------------------------------------------
* 게임 링크 : https://aestura.github.io/Aestura2.io/
* 참고 : https://www.w3schools.com/graphics/game_intro.asp
