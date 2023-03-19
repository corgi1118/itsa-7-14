# itsa-7-14
## 題目7. 複數運算
### 問題描述 ：
在做傅立葉轉換時，常會用到複數，但每次都要分開來計算實部與虛部，非常的麻煩，現在透過operator overloading的方式來簡化程式設計師的負擔。須做加減乘。
## 輸入說明 ：
第一列輸入一個正整數n。其後有n列，每一列代表一個想要做運算的虛數，每一列之資料依序為運算元、虛數1、虛數2。虛數的格式為a b。
## 輸出說明 ：
每一列表一個運算結果。虛數的格式為a b。
## 範例 ：
![image](https://user-images.githubusercontent.com/126050259/226161395-61030d0b-f674-49fe-9851-9b946a63ede3.png)
## 程式說明:
```
#include <iostream>
using namespace std;

class Complex {
private:
    int re, im;
public:
    Complex(int r = 0, int i = 0) {
        re = r;
        im = i;
    }
    Complex operator + (Complex const& obj) {
        Complex result;
        result.re = re + obj.re;
        result.im = im + obj.im;
        return result;
    }
    Complex operator - (Complex const& obj) {
        Complex result;
        result.re = re - obj.re;
        result.im = im - obj.im;
        return result;
    }
    Complex operator * (Complex const& obj) {
        Complex result;
        result.re = re * obj.re - im * obj.im;
        result.im = re * obj.im + im * obj.re;
        return result;
    }
    void display() {
        cout << re << " " << im << endl;
    }
};

int main() {
    int n;
    Complex c[10];

    cin >> n;
    for (int i = 0; i < n; i++) {
        char oper;
        int ar, ai, br, bi;
        cin >> oper >> ar >> ai >> br >> bi;
        Complex a(ar, ai);
        Complex b(br, bi);

        switch (oper) {
        case '+':
            c[i] = a + b;
            break;
        case '-':
            c[i] = a - b;
            break;
        case '*':
            c[i] = a * b;
            break;
        }
    }
    for (int i = 0; i < n; i++) {
        c[i].display();
    }
    return 0;
}
```
Complex 代表複數，其中包含實部 re 和虛部 im，並定義了加法、減法和乘法運算符號的運算子輸入一個整數 n，接著使用迴圈讀取 n 行輸入，每行輸入一個字元 oper 和四個整數 ar、ai、br、bi，表示要進行的運算及兩個複數的實部和虛部。根據輸入的 oper 運算符號，對兩個複數 a 和 b 進行運算，並將結果存入 c 陣列中。最後，使用迴圈顯示 c 陣列中的所有複數。

## 題目8. 質數判別
### 問題描述：
試撰寫一個程式，由輸入一個整數，然後判別此數是否為質數。質數是指除了 1 和它本身之外，沒有其它的數可以整除它的數，例如， 2, 3, 5, 7 與 11 等皆為質數。
### 輸入說明：
輸入一個正整數。
### 輸出說明：
質數顯示 YES ；非質數顯示 NO 。
### 範例：
![image](https://user-images.githubusercontent.com/126050259/226162112-89645c5e-490d-4d8e-ab3f-070fd93fa406.png)
### 程式說明:
```
#include <iostream>
using namespace std;

int main()
{
    int n, a, ans;
    cin >> n;
    ans = 1;
    a = 2;
    while (a < n)
    {
        if (n % a == 0)
        {
            ans = 0;
        }
        a++;
    }
    if (ans == 1)
    {
        cout << "YES" << endl;
    }
    else
    {
        cout << "NO" << endl;
    }
    return 0;
}
```
這是一段判斷是不是質數的程式，n為輸入，ans為1表示預設數字是質數，a為2，從2開始依次遍歷2到n-1的所有數字，if (n % a == 0)檢查n能不能被a整除如果可以ans為0，表示n不是質數，a+1進入下一個循環循環結束後，如果 ans 等於1，則輸出 "YES"，否則輸出 "NO"，表示輸入的數字是否是一個質數

## 題目9. 計算正整數被3整除之數值之總和
### 問題描述：
試寫一個程式，輸入一正整數N，可計算出1到N之間可被3整除的數值之總和。
### 輸入說明：
輸入一正整數。
### 輸出說明：
輸出總和。
### 範例：
![image](https://user-images.githubusercontent.com/126050259/226162999-6f010e65-27a6-4801-8173-17aee3330924.png)
### 程式說明
```
#include <iostream> 

using namespace std;

int main() {
    int n, sum = 0;
    cin >> n;
    for (int i = 1; i <= n; i++) {
        if (i % 3 == 0) {
            sum += i;
        }
    }
    cout << sum << endl;
    return 0;
}

```
![image](https://user-images.githubusercontent.com/126050259/226165064-022463e0-2275-4b0b-93d5-5a878f61fa65.png)

## 題目10. 輾轉相除法
### 問題描述：
給定二個正整數，利用輾轉相除法求其最大公因數。
### 輸入說明：
給定二個正整數
### 輸出說明：
輸出最大公因數
### 範例：
假設輸入為 300 與 250, 則輸出為 50
### 程式說明
```

```


## 題目11. 矩陣反轉
### 問題描述 ：
請設計一程式，輸入一個陣列並且反轉後再輸出。
### 輸入說明 ：
第一行先輸入矩陣的行、列，之後再輸入陣列元素。
### 輸出說明 ：
反轉後的矩陣。
### 範例 ：
![image](https://user-images.githubusercontent.com/126050259/226163108-fc68b1e4-a45d-42fc-9424-7ee052d34ef7.png)
### 程式說明:
```
```

## 題目12. 遞迴程式練習
### 問題描述 ：
給定下列遞迴函式 :
![image](https://user-images.githubusercontent.com/126050259/226163198-eb2ea240-bf4c-40ae-8949-3287cf5151c1.png)
請計算出 f (k) 。
### 輸入說明 ：輸入值為一個大於 1 的整數。
### 輸出說明 ：f(k) 的計算結果。
### 範例 ：
![image](https://user-images.githubusercontent.com/126050259/226163308-2cc35e1c-6af1-4675-977f-96927569fc25.png)

### 程式說明:
```
#include <iostream>
using namespace std;

int f(int n){
    if(n==0||n==1) {
        return n+1;
    }
    else if(n>1){
        return f(n-1)+f(n/2);
    }
}

int main(){
    //ios::sync_with_stdio(0);
    //cin.tie(0);
    int n;
    cin>>n;
    cout<<f(n)<<"\n";

    return 0;
}
```
函數f(n):如果n為0或1，則回傳n+1 如果n大於1則回傳f(n-1) + f(n/2) 的結果 \
在 main() 函數中，程式先輸入一個整數 n，然後呼叫函數 f(n) 取得結果並輸出到標準輸出流



## 題目14. 判斷是否為迴文
### 問題描述 ：
迴文是指從前面讀和從後面讀都相同的一個數字或一段文字。例如下列每一五位數的整數都是迴文： 123321 ， 55555 ， 45554 ， 11611 。請撰寫一個程式，判斷它是否迴文。
### 輸入說明 ：
輸入一個正整數。
### 輸出說明 ：
迴文印出 ” 是 ” ；非回文印出 ” 否 ” 。
### 範例 ：
![image](https://user-images.githubusercontent.com/126050259/226163366-832b78ae-6c44-4ebb-9364-c9900d43deaa.png)

### 程式說明:
```
#include <iostream>
#include <string>
using namespace std;

int main() {
    string input, output;
    bool a = 1;

    cin >> input;
    for (int i = input.length() - 1; i >= 0; i--) {
        output += input[i];
    }
    for (int j = 0; j < input.length(); j++) {
        if (input[j] != output[j]) {
            a = 0;
            break;
        }
    }
    if (a) {
        cout << "YES" << endl;
    }
    else {
        cout << "NO" << endl;
    }

    return 0;
}
```
利用for迴圈將input字串的最後一個字元開始取出到output字串中，並檢查兩個字串對應位子的字元是否相同，並印出YES或NO
