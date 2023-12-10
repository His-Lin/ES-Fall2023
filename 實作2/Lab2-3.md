# digitWrite(), analogWrite(), 呼吸效果 
## 影片

https://github.com/His-Lin/ES-Fall2023/assets/144580635/8cb018a1-98bc-4d75-aa53-f1fe438af7de

## 電路圖
![image](https://github.com/His-Lin/ES-Fall2023/assets/144580635/16542d01-9993-4170-a829-73c5f8c9f5f5)

## 程式碼
````c
int R = 9;
int G = 10;
int B = 11;

int DR = 2;
int DG = 4;
int DB = 7;

void setup()
{
  pinMode(13, OUTPUT); // pin 13
  
  pinMode(R, OUTPUT);
  pinMode(G, OUTPUT);
  pinMode(B, OUTPUT);  
  
  pinMode(DR, OUTPUT);
  pinMode(DG, OUTPUT);
  pinMode(DB, OUTPUT);   
}

void loop()
{
  // digitalWrite: 2 state (i.e., 0, 1) Only
  digitalWrite(13, 1); // LED @ pin 13, ON
  
  delay(1000); 
  
  digitalWrite(DR, 1);
  digitalWrite(DG, 0);
  digitalWrite(DB, 0);
  delay(1000);
  digitalWrite(DR, 0);
  digitalWrite(DG, 1);
  digitalWrite(DB, 0);  
  delay(1000);
  digitalWrite(DR, 0);
  digitalWrite(DG, 0);
  digitalWrite(DB, 1);  
  delay(1000);

  digitalWrite(13, 0); // OFF
  digitalWrite(DR, 0); // OFF
  digitalWrite(DG, 0); // OFF
  digitalWrite(DB, 0); // OFF  
  delay(1000);
  
  // analogWrite: The brightness can be adjusted with 256 levels
  for (int i = 0; i<= 255; i++)
  {
  	analogWrite(R, i);
		analogWrite(G, 0);
		analogWrite(B, 0);
    delay(10);
  } // from dark to bright 

  for (int i = 255; i>= 0; i--)
  {
  	analogWrite(R, i);
		analogWrite(G, 0);
		analogWrite(B, 0);
    delay(10); // 10ms = 0.01s
  }  // from bright to dark
  delay(1000);
}
