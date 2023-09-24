# 實作2: Welcome: GitHub入門, Tinker CAD, digitalWrite(), LED亮滅 (2W) 

## 1-2 在TinkerCAD開一個新的Circuit, 分別使甪R, G, B三種顏色的LED, ALL ON (亮) 0.5秒, OFF(滅) 0.5秒

## 影片

https://github.com/His-Lin/ES-Fall2023/assets/144580635/6a4e75b8-1b7d-45a6-9ad3-630148346b68

## 電路圖

![lab2](https://github.com/His-Lin/ES-Fall2023/assets/144580635/d6f1f54b-9a27-4a9a-b0e0-140abc160a2a)

## 程式

![lab2-1](https://github.com/His-Lin/ES-Fall2023/assets/144580635/21c9ab98-511f-43bd-9f04-3135a6b19ff5)

## 程式碼

// C++ code
//
/*
  This program blinks pin 13 of the Arduino (the
  built-in LED)
*/

void setup()
{
  pinMode(13, OUTPUT);
  pinMode(10, OUTPUT);
  pinMode(7, OUTPUT);
}

void loop()
{
  // turn the LED on (HIGH is the voltage level)
  digitalWrite(13, HIGH);
  digitalWrite(10, HIGH);
  digitalWrite(7, HIGH);
  delay(500); // Wait for 1000 millisecond(s)
  // turn the LED off by making the voltage LOW
  digitalWrite(13, LOW);
  digitalWrite(10, LOW);
  digitalWrite(7, LOW);
  delay(500); // Wait for 1000 millisecond(s)
}
