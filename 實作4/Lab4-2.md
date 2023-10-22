# 用七段顯示器, 顯示  0→1→ ... → 9 → . → 全滅, 狀態改變的間隔時間為1秒

## 電路圖
![image](https://github.com/His-Lin/ES-Fall2023/assets/144580635/c36af19e-26d0-41e0-9c3c-acfca07ba081)

## 影片

https://github.com/His-Lin/ES-Fall2023/assets/144580635/bb2a8c7e-e203-4e2d-9332-ea2ada44368e


## 程式碼
````c
void setup()
{
for(int x = 1; x < 9; x++) {
pinMode(x,OUTPUT);
}
}

void seg71(int a, int b, int c, int d, int e, int f, int g, int h)
{
digitalWrite(1, a);
digitalWrite(2, b);
digitalWrite(3, c);
digitalWrite(4, d);
digitalWrite(5, e);
digitalWrite(6, f);
digitalWrite(7, g);
digitalWrite(8, h);
delay(1000);
}

void loop()
{
//    a, b, c, d, e, f, g, h
seg71(1, 1, 1, 1, 1, 1, 0, 0); //0
seg71(0, 1, 1, 0, 0, 0, 0, 0); //1
seg71(1, 1, 0, 1, 1, 0, 1, 0); //2
seg71(1, 1, 1, 1, 0, 0, 1, 0); //3
seg71(0, 1, 1, 0, 0, 1, 1, 0); //4
seg71(1, 0, 1, 1, 0, 1, 1, 0); //5
seg71(1, 0, 1, 1, 1, 1, 1, 0); //6
seg71(1, 1, 1, 0, 0, 1, 0, 0); //7
seg71(1, 1, 1, 1, 1, 1, 1, 0); //8
seg71(1, 1, 1, 1, 0, 1, 1, 0); //9
seg71(0, 0, 0, 0, 0, 0, 0, 1); //.
seg71(0, 0, 0, 0, 0, 0, 0, 0); //空白
}
