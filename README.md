# IT

1. 시나리오 및 작성 소감
아두이노와 조도센서를 이용하여 화면에 밝기로 현재 조도를 알 수 있게 해주도록 코딩을 하였습니다. 이런 경험을 가질 수 있어 좋았고, 너무 재밌어서 더욱 공부 하고 싶어지는 강의였습니다.

2. 아두이노 코드

void setup() {

  Serial.begin(9600);
  
}

int a;

void loop() {

  a = analogRead(A0);
  
  Serial.println(a);
  
  delay(500);
  
}

3. 프로세싱 코드
import processing.serial.*;

Serial p;

void setup() {

  size(300, 300);
  
  p = new Serial(this, "COM3", 9600);
  
}

void draw() {

  if (p.available() > 0) {
  
    String m = p.readString();
    
    int a = int(m.trim());
    
    println(a);
    
    if (a > 46) fill(0, 255, 0);
    
    else        fill(255, 0, 0);
    
    ellipse(150, 150, 150, 150);
    
  }
  
}
