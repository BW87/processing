# 2장 배너 위아래로 움직이기 응용

### 배너 위아래로 움직이기 예제를 응용했습니다.

### 원래 예제는 키보드의 숫자로 속도를 제어했습니다.

### 그런데 숫자가 아닌 다른 곳을 누르면 에러가 났었습니다.

### 그래서 저는 키보드의 위 아래 버튼으로 속도를 제어할수 있게 코딩하였습니다.(그외에는 이벤트 발생 x)

##### 소스코드

```
PFont f;
void setup(){
  size(800,300);
  textSize(72);
  f = createFont("굴림", 64);
  textFont(f);
}
  int i;
  int dir = 1;
  int sp = 1;
void draw(){
  background(0);
  fill(255,255,0);
  text("Chapter2 Exercise Test!", 60, i);
  if(i>width) dir = -1;
  if(i<0) dir = 1;
  i = i+dir*sp;
}
void keyPressed(){
  if(keyCode == UP){
    sp++;
  } else if(keyCode == DOWN){
    sp--;
  }
}

```
