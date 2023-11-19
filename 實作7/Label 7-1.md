# 實作7: AI-based ES? AI? ML? DL? 要如何入門 (How To Learn)?
## Lab 7-1 首先, 在你的Google Drive, 建立你的第一個Colab
### 圖片
![image](https://github.com/His-Lin/ES-Fall2023/assets/144580635/77d9fed2-a0ab-45ab-976b-6878fa0ae318)

##  新增文字儲存格: Colab也可使用markdown耶. (請用你的英文名字)
### 圖片

![image](https://github.com/His-Lin/ES-Fall2023/assets/144580635/801dad9f-9e19-4c5d-b92f-9b835be34e9e)
## Lab 7-2 建立我們的第二個Colab Notebook (Filename: 十分鐘學會Python.ipynb), 開始十分鐘學會Python囉
![image](https://github.com/His-Lin/ES-Fall2023/assets/144580635/7d88e644-778f-4ed7-a17b-96a40caa758e)
### 執行後

![image](https://github.com/His-Lin/ES-Fall2023/assets/144580635/da6acb9f-4bed-4ae5-a84e-3c0a9e4e9f5b)

### 程式碼
‵‵‵‵c
name = "His-Lin"
print(name)

number = 26
print(number)
print(number*3)
print(number/2)
print(number+number)
print(number-number)

def printName(firstName,lastName):
  print(lastName+" "+firstName)

printName("His-Lin","Chiang")

def printName(firstName,lastName,isCool):
  if isCool:
    print(lastName+" "+firstName+"very cool!")
  else:
    print(lastName+" "+firstName+"not cool!")

printName("His-Lin","Chiang",True)
printName("His-Lin","Chiang",False)


def printName(firstName,lastName,isCool,num):
  for i in range(1, num):
    if isCool:
      print(i,lastName+""+firstName+"very cool!")
    else:
      print(i,lastName+""+firstName+"not cool!")  
printName("His-Lin","Chiang",True,10)
