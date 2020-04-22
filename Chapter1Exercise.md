# 1장 펜 만들기 응용

## 펜 만들기 예제를 조금 변형해 보았습니다.

## 마우스 왼쪽 클릭을 하면 마우스 포인터에 따라서 선이 그어진다.

## 마우스 오른쪽 클릭을 하면 랜덤하게 선의 색이 달라진다.

## 랜덤하게 색을 바꾸는데에 random()를 이용했습니다.

### 코드

int count = 0;
void setup(){
  size(640,640);
  background(255);
  strokeWeight(16);
  stroke(0,0,0);
}
void draw(){
  if(mousePressed){
    if(mouseButton == LEFT){
      line(pmouseX, pmouseY, mouseX, mouseY);
    }
    else if(mouseButton == RIGHT){
       stroke(random(0,255), random(0,255), random(0,255));
    }
  }
}
