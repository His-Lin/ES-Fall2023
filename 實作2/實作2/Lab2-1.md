# 實作2: 會呼吸的RGB LED,  按鍵控制, 狀態輸出 (2W) 

## 實作2-1, analogWrite(): 並且觀查LED亮度變化是否有像"呼吸的效果"和示波器的波形有什麼關連性?

## 電路圖

![2-1](https://github.com/His-Lin/ES-Fall2023/assets/144580635/c0ffdce8-f068-4ed4-9522-b5cdee877139)

## 影片
https://github.com/His-Lin/ES-Fall2023/assets/144580635/9aaa59bd-f6b6-444c-9db0-a31f61b269fc

## 程式碼
````c
int brightness = 0;

void setup()
{
  pinMode(9, OUTPUT);
}

void loop()
{
  for (brightness = 0; brightness <= 255; brightness += 5) {
    analogWrite(9, brightness);
    delay(60); // Wait for 30 millisecond(s)
  }
  for (brightness = 255; brightness >= 0; brightness -= 5) {
    analogWrite(9, brightness);
    delay(60); // Wait for 30 millisecond(s)
  }
}
