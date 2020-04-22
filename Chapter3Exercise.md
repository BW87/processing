# 3장 Processing Example 변형 예제

### Processing Example 중 하나를 골라 예제를 변형 시켜 보았습니다.

### 제가 선택한 Example은 Transparency 입니다.

### 제가 변형할 내용은 투명화된 사진은 원본사진보다 작고 단순히 좌우가 아닌 상하좌우 모든곳으로 움직이게 할것입니다.

##### 소스코드 

```
PImage img;
float offset1 = 0;
float offset2 = 0;
float easing = 0.05;

void setup(){
  size(640,360);
  img = loadImage("test.jpg");
}

void draw(){
  image(img, 0,0,width, height);
  float dx = (mouseX - img.width/2) - offset1;
  float dy = (mouseY - img.height/2) - offset2;
  offset1 += dx * easing;
  offset2 += dy * easing;
  tint(255,128);
  image(img, offset1, offset2);
}
```
