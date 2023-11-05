# 按下按鍵, Green LED亮 & Red LED滅; 放開按鍵, Green LED滅 & Red LED亮. 

## 影片

https://github.com/His-Lin/ES-Fall2023/assets/144580635/689029e1-0163-4389-8411-41d1b89b7ab0

## 電路圖
![image](https://github.com/His-Lin/ES-Fall2023/assets/144580635/f66349c0-8ff3-46a9-9549-149afe47a0b3)

##程式碼
````c
int buttonState = 0;
int GLED = 13;
int RLED = 8;
void setup()
{
  pinMode(2, INPUT);
  
  pinMode(GLED, OUTPUT);
  pinMode(RLED, OUTPUT);
  
  Serial.begin(9600);
}

void loop()
{
  // read the state of the pushbutton value
  buttonState = digitalRead(2);
  // check if pushbutton is pressed.  if it is, the
  // buttonState is HIGH
  if (buttonState == HIGH) {
    // turn LED on
    digitalWrite(GLED, HIGH);
    digitalWrite(RLED, LOW);
    
  } else {
    // turn LED off
    digitalWrite(GLED, LOW);
    digitalWrite(RLED, HIGH);
  }
  Serial.println(buttonState);
  delay(10); // Delay a little bit to improve simulation performance
}
