# sound1551

//1주차 선 그리기 ,stroke를 이용해서 선을 그리고 if(mousePressed)이하를 이용해서 마우스의 클릭과 이동에 따라 선이 그려나가게 되는 코드이다.
void setup(){
  size(550,550);
  strokeWeight(16);
  stroke(0,0,255);
 }
 void draw(){
   if(mousePressed)
   line(pmouseX,pmouseY,mouseX,mouseY);
 }
 
 //2주차 한글 배너 만들기 , f = createFont("굴림", 64);를 이용하여 폰트를 변환하고 화면에 맞춘 계산식을 통해 글자가 위아래로 천천히 움직일수 있도록 설계되었다.
 PFont f;
void setup() {
  size(800, 300);
  textSize(6);
  f = createFont("굴림", 64);
  textFont(f);
}

int i, dir=1, sp=1;
void draw() {
  fill(255);
  background(0, 0, 0);
  text("안동대 컴공 사랑합니다", 20, i+50);
  if (i>width-550) dir=-1;
  if (i<0) dir=1;
  i = i+dir*sp;
}

//3주차 투명도 조절 Transparency ,  image(img, 0, 0); 를 이용해 불투명한 이미지를 호출하고 tint(255, 127); 를 이용해 반투명한 사진을 덮어씌우고 마우스의 좌우 위치에 따라 사진이 이동할수있게 만들었다. 
PImage img;
float offset = 0;
float easing = 0.05;

void setup() {
  size(640, 360);
  img = loadImage("moonwalk.jpg");
}

void draw() { 
  image(img, 0, 0); 
  float dx = (mouseX-img.width/2) - offset;
  offset += dx * easing; 
  tint(255, 127);
  image(img, offset, 0);
}

//4주차 도형 만들기 , 원 circle과 사각형 quad, 삼각형 triangle을 이용해 만든 간단한 케이크이다.
size(300, 300);
fill(139, 69, 19);
triangle(150, 110, 200, 140, 60, 170);
quad(60, 170, 200, 140, 200, 200, 60, 230);
fill(255, 255, 240);
quad(60, 210, 200, 180, 200, 190, 60, 220);
quad(60, 180, 200, 150, 200, 160, 60, 190);
fill(69, 29, 19);
circle(150, 120, 40);
fill(255, 255, 240);
circle(173, 124, 11);
circle(129, 124, 11);
circle(150, 140, 11);
circle(160, 137, 11);
circle(168, 130, 11);
circle(140, 137, 11);
circle(132, 130, 11);

//6주차 빛을받는 구 만들기 , p3d로 3d환경을 구축하고 sphere와 noStroke로 깔끔한 구를 생성후  pointLight를 통해 Z좌표 380에서 부터 노란색의 빛을 구에 보낸다.
size(400,400,P3D);
noStroke();
pointLight(255,255,0,0,0,380);
translate(200,200,0);
sphere(160);

