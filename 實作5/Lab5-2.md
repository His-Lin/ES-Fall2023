# LCD顯示溫度感應器的溫度;若溫度<38 綠LED亮; 若大於38度, 紅色LED亮
## 影片

https://github.com/His-Lin/ES-Fall2023/assets/144580635/9e31a505-e87b-44a6-8786-005f2f7a41e9

## 電路圖
![image](https://github.com/His-Lin/ES-Fall2023/assets/144580635/47c92b02-8ba7-4954-b5db-6b324ac106f1)
## 程式碼
````c
#include <LiquidCrystal.h>

LiquidCrystal lcd(12, 11, 5, 4, 3, 2);

int RLED = 9;
int GLED = 8;

void setup() {
  lcd.begin(16, 2);
  Serial.begin(9600);	
  pinMode(A1, INPUT); // Read analog voltage (2^10)

  digitalWrite(RLED,OUTPUT);
  digitalWrite(GLED,OUTPUT);
}

void loop() {
  int reading = analogRead(A1);  // read analog level (2^10)
  lcd.setCursor(0,0);  
  lcd.print("TMP Sensor Demo");

  float voltage = (reading/1024.0) * 5.0; // Convert to voltage
  
  // converting from 10mv per degree with 500mV offset  
  float tempC = (voltage - 0.5) * 100.0; 
  lcd.setCursor(0,1);
  lcd.print("Tmp:");
  lcd.print(tempC);
  lcd.print(" C");
  delay(500);
  lcd.clear();
  Serial.println(reading);
  Serial.println(voltage);
  
   if (tempC <38){
    digitalWrite(RLED,LOW);
  	digitalWrite(GLED,HIGH); 

  }  
   else {
    digitalWrite(RLED,HIGH);
  	digitalWrite(GLED,LOW); 

  }  
}
