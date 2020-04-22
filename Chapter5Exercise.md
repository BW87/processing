# 5장 PShape 예제 응용입니다.

### PShape 예제를 제가 변형해 보았습니다.

### 원래는 별 두개가 왼쪽에서 오른쪽으로 이동하는 예제입니다.

### 마우스 왼쪽 클릭을 하면 별이 생성되고, 오른쪽 클릭을 하면 사라지는게 변형했습니다.

### 또한 별의 움직임 속도도 랜덤하게 변형했습니다.

##### 소스코드

```
class Star {
  PShape s;
  float x, y;
  float speed;

  Star() {
    x = random(100, width-100);
    y = random(100, height-100); 
    speed = random(0.5, 3);
    s = createShape();
    s.beginShape();
    s.fill(0, 255, 255); 
    s.stroke(0,200,255);
    s.strokeWeight(5);
    s.vertex(0, -50);
    s.vertex(14, -20);
    s.vertex(47, -15);
    s.vertex(23, 7);
    s.vertex(29, 40);
    s.vertex(0, 25);
    s.vertex(-29, 40);
    s.vertex(-23, 7);
    s.vertex(-47, -15);
    s.vertex(-14, -20);
    s.endShape(CLOSE);
  }
  void move() {
    // Demonstrating some simple motion
    x += speed;
    if (x > width+100) {
      x = -100;
    }
  }
  void display() {
    // Locating and drawing the shape
    pushMatrix();
    translate(x, y);
    shape(s);
    popMatrix();
  }
}

ArrayList<Star> starList;
Star s1, s2;
void setup() {
  size(640, 360, P2D);
  
  s1 = new Star();
  s2 = new Star();
  
  starList = new ArrayList<Star>();
  starList.add(s1);
  starList.add(s2);
}

void draw() {
  background(255);

  for(Star star : starList){
    star.display();
    star.move();
  }
}

void mousePressed(){
  if(mouseButton == LEFT){
    Star addstar = new Star();
    starList.add(addstar);
  } else if(mouseButton == RIGHT){
    if(starList.size() > 0){
      starList.remove(0);
    }
  }
}
```
