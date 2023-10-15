# Lab 3-2: 超音波感測器 + LED (紅色LED:亮<70cm, 藍色LED: 亮>270cm, 緑色LED:亮, 介於70cm ~ 270cm之間) + RS232 Output

## 圖片

![image](https://github.com/His-Lin/ES-Fall2023/assets/144580635/294edf93-6774-4a47-98e4-b9fb4314f297)

## 影片

https://github.com/His-Lin/ES-Fall2023/assets/144580635/6e3344a8-296a-4e09-b315-b17bddf60afe

## 程式碼
````c

int inches = 0;
int GLED = 8;
int RLED = 12;
int BLED = 10;
int cm = 0;

void LED(int RH, int GH, int BH)
{
  digitalWrite(RLED, RH);  
  digitalWrite(GLED, GH);
  digitalWrite(BLED, BH);   
}

long readUltrasonicDistance(int triggerPin, int echoPin)
{
  pinMode(triggerPin, OUTPUT); 
  digitalWrite(triggerPin, LOW);
  delayMicroseconds(2);
  
  digitalWrite(triggerPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(triggerPin, LOW);
  pinMode(echoPin, INPUT);
  
  return pulseIn(echoPin, HIGH);
}

void setup()
{
  Serial.begin(9600);
  digitalWrite(GLED, OUTPUT);
  digitalWrite(RLED, OUTPUT);  
  digitalWrite(BLED, OUTPUT);    
  
}

void loop()
{
  
  cm = 0.01723 * readUltrasonicDistance(7, 7);
  
  inches = (cm / 2.54);
  Serial.print(inches);
  Serial.print("in, ");
  Serial.print(cm);
  
  if(cm<70){
    LED(1, 0, 0);   
  }
  else if(cm>270){
    LED(0, 0, 1);     
  }
  else{
    LED(0, 1, 0);   
  }
    
  Serial.println("cm");
  delay(100); 
   
}
