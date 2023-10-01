# 實作2: 會呼吸的RGB LED,  按鍵控制, 狀態輸出 (2W) 

## 實作2-2, RGB LED燈全彩模組, 分別讓LED輪流表現正紅、正綠、正藍，三個顏色，時間間隔1秒鐘。並且觀查LED顏色和波形或是電壓有什麼關連性? 可將個人說明在更新GitHub時一起加入. (互動2), (1W: ~02:20pm)

## 電路圖

![2-2](https://github.com/His-Lin/ES-Fall2023/assets/144580635/6927c5a0-3844-4c8e-8428-408bfd268ef5)


## 影片

https://github.com/His-Lin/ES-Fall2023/assets/144580635/121948cf-1f2c-4f0f-b992-8db91f4e0c81

## 程式碼
````c

const int Red = 11;
const int Green = 9;
const int Blue = 10;

void setup()
{
  pinMode(Red, OUTPUT);
  pinMode(Green, OUTPUT);
  pinMode(Blue, OUTPUT);
}

void loop()
{
  analogWrite(Red,255);
  analogWrite(Green,0);
  analogWrite(Blue,0);
  delay(1000);
  
  analogWrite(Red,0);
  analogWrite(Green,255);
  analogWrite(Blue,0);
  delay(1000);
  
  analogWrite(Red,0);
  analogWrite(Green,0);
  analogWrite(Blue,255);
  delay(1000);
}
