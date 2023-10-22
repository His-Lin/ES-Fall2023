# 七段顯示器, LCD 顯示器 + 超音波感測器 (2W)

## 影片

https://github.com/His-Lin/ES-Fall2023/assets/144580635/89d4ae4a-3fe3-416e-a1a5-39397e5f17c8

## 圖片
![image](https://github.com/His-Lin/ES-Fall2023/assets/144580635/1a2ff12a-7e89-43bd-9c2e-555dd2ca2731)

## 程式碼

````C
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
delay(500);
}

void loop()
{
//    a, b, c, d, e, f, g, h
seg71(0, 0, 0, 0, 0, 0, 0, 0); // OFF
seg71(1, 1, 1, 1, 1, 1, 1, 1); // 8
}
