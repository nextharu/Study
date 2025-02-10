## 01. 조건문

<br>   

**if-else 문**
```java
int age = 15;

if(age <= 13)
    System.out.println("어린이입니다.");
else if(age <= 19)
    System.out.println("청소년입니다.");    // 실행 후 조건문 탈출
else
    System.out.println("성인입니다.");
```

<br>   
<br>   

**삼항 연산자**
```java
int age = 25;

string group = (age >= 19) ? "성인" : "미성년자";
```

<br>   
<br>   

**switch 문**
```java
int month = 5;

switch(month) {
    case 12: case 1: case 2:
        System.out.println("겨울");
        break;
    case 3: case 4: case 5:
        System.out.println("봄");     // 실행 후 조건문 탈출
        break;
    case 6: case 7: case 8:
        System.out.println("여름");
        break;
    case 9: case 10: case 11:
        System.out.println("가을");
        break;
    default:
        System.out.println("이상한 계절");
}
```

<br>   
<br>   
<br>   
<br>   
<br>   

## 02. 반복문

<br>   

**for 문**
```java
// 1부터 10까지의 합을 출력하는 프로그램

int sum = 0;

for(int i = 1; i <= 10; i++) {
    sum += i;
}

System.out.println(sum); 
```

<br>   
<br>   

**foreach 문**
```java
// 배열의 요소들을 출력하는 프로그램

int[] primes = {2, 3, 5, 7, 11};

for(int prime : primes) {
    System.out.print(prime + " ");
}
```

<br>   

<mark>배열을 순회하면서 값을 출력할 때 foreach 문을 사용하면 가독성이 좋아진다.</mark>

<mark>하지만 foreach 문에서 요소를 수정해도 해당 배열/컬렉션은 변경되지 않는다.</mark>

<br>   
<br>   
<br>   

**while 문**
```java
// 제곱수를 출력하는 프로그램

int i = 2;

while(i <= 9) {
    System.out.println("i × i = " + (i * i));
    i++;
}
```

<br>   
<br>   

**do while 문**
```java
// 10부터 1까지 카운트다운하는 프로그램

int count = 10;

do { 
    System.out.print(count + " ");
    count--;
} while(count > 0)
```

<br>   

<mark>while 문은 처음부터 조건을 검사한다. </mark>

<mark>do while 문은 조건과 상관없이 최소 1회 실행된다.</mark>

<br>   
<br>   
<br>   
<br>   
<br>   

## 03. 점프문

<br>   

**break 문**

```java
// 소수를 판별하는 프로그램

int N = 43;
boolean isPrime = true;

for (int i = 2; i <= (int) Math.sqrt(N); i++) {

    // 1이 아닌 자연수로 나누어떨어지면 반복문을 종료한다.

    if (N % i == 0) {
        isPrime = false;
        break;
    }
}

if (isPrime)
    System.out.println("소수입니다.");
else
    System.out.println("소수가 아닙니다.");
```

<br>   
<br>   

**continue 문**
```java
// 3의 배수가 아닌 두자리 자연수들을 출력하는 프로그램

for (int i = 10; i <= 99; i++) {

    // 3의 배수이면 건너뛴다.

    if (i % 3 == 0) continue;

    System.out.print(i + " ");
}
```
