1. 아두이노

void setup() {
  Serial.begin(9600);
  pinMode(13, OUTPUT);
}

void loop() {
  if (Serial.available() > 0) {
    String m = Serial.readString();
    if (m.indexOf('0') == 0) {
      digitalWrite(13, LOW);
    }
    if (m.indexOf('1') == 0) {
      digitalWrite(13, HIGH);
    }
  }
}

2. 프로세싱

import processing.serial.*;
import processing.net.*;
Serial p;
Server s;
Client c;
void setup(){
  p = new Serial(this, "COM8", 9600);
  s = new Server(this, 1597);
}

void draw(){
  c = s.available();
  if (c != null) {
    String m = c.readString();
    m = m.substring(m.length()-1);
    p.write(m);
  }
}
