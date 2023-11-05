# analogRead(), 1024解析度 (i.e.,10-bit): 可變電阻 + 序列監視器與輸出

## 影片

https://github.com/His-Lin/ES-Fall2023/assets/144580635/f83e55c0-f970-47b8-ad88-eb8e9549ba7b

## 電路圖

![image](https://github.com/His-Lin/ES-Fall2023/assets/144580635/7e6a32f5-5cf7-4b47-a9d7-b53b0828bca8)

## 程式碼
````c
int sensorValue = 0;

void setup()
{
  pinMode(A0, INPUT);
  pinMode(LED_BUILTIN, OUTPUT);
}

void loop()
{
  // read the value from the sensor
  sensorValue = analogRead(A0);
  // turn the LED on
  digitalWrite(LED_BUILTIN, HIGH);
  // stop the program for the <sensorValue>
  // milliseconds
  delay(sensorValue); // Wait for sensorValue millisecond(s)
  // turn the LED off
  digitalWrite(LED_BUILTIN, LOW);
  // stop the program for the <sensorValue>
  // milliseconds
  delay(sensorValue); // Wait for sensorValue millisecond(s)
}
