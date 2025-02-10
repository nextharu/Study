## 01. 배열

<br>   

**배열이란?**

+ 배열(array)은 동일한 타입의 데이터들을 묶어 저장하는 자료구조이다. 
+ 배열의 크기를 한 번 지정하면 다시는 변경할 수 없다.
+ 인덱스를 통해 요소에 접근할 수 있는데, 인덱스는 0부터 하나씩 증가한다.

<br>   
<Br>   

**배열 생성하기**
```java
// (1) 요소를 하나씩 대입하기

int[] numbers = new int[3];
numbers[0] = 1;
numbers[1] = 2;
numbers[2] = 3;


// (2) 요소들을 한꺼번에 대입하기

String[] cities = new String[] {"서울", "부산", "인천"};


// (3) new 키워드 없이 요소들만 대입하기

String[] nations = {"영국", "미국", "캐나다", "호주", "뉴질랜드"};
```

<br>   

<mark>세번째 방법의 경우 변수 선언과 객체 대입을 따로 할 수 없다.</mark>

<br>   
<br>   
<br>   

**배열 접근하기**
```java
// (1) for 문을 이용해 접근하기

for(int i = 0; i < numbers.length; i++) {
    System.out.print(numbers[i] + " ");
}


// (2) foreach 문을 이용해 접근하기

for(int number : numbers) {
    System.out.print(number + " ");
}
```

<br>   

<mark>유효하지 않은 인덱스에 접근하면 ArrayIndexOutOfBoundsException이 발생한다.</mark>

<br>   
<br>   
<br>   

**배열 복사하기**
```java
// (1) 얇은 복사

int[] origin1 = {1, 2, 3, 4, 5};
int[] copy1 = origin1;

copy1[0] = 100;
System.out.println(origin1[0]);   // 100 


// (2) 깊은 복사

int[] origin2 = {1, 2, 3, 4, 5};
int[] copy2 = new int[origin2.length];

for(int i = 0; i < origin2.length; i++) {
    copy2[i] = origin2[i];
}

copy2[0] = 100;
System.out.println(origin2[0]);   // 1 
```

<br>  

+ 얇은 복사는 객체의 메모리 주소를 복사하는 방법이다.
+ 원본과 복사본이 같은 객체를 가리키기 때문에, 복사본을 수정하면 원본에도 영향이 생긴다.

<br>   

+ 깊은 복사는 새로운 객체를 생성하고 요소들을 하나하나 복사하는 방법이다.
+ 원본과 복사본이 다른 객체를 가리키기 때문에, 복사본을 수정해도 원본에 영향이 생기지 않는다.
+ 1차원 배열의 경우 `for 문`, `System.arraycopy()`, `clone()` 등을 활용하면 깊은 복사가 수행된다.

<br>   
<br>   
<br>  
<br>   
<br>  

## 02. 문자열

<br>   

**문자열 생성하기**
```java
// (1) new 연산자를 이용하기

String str1 = new String("Java");
String str2 = new String("Java");

System.out.println(str1 == str2);    // false


// (2) 리터럴만 입력하기

String str3 = "Java";
String str4 = "Java";

System.out.println(str3 == str4);    // true
```

<br>   

+ new 연산자를 이용하면 해당 문자열이 힙 영역에 저장된다.
+ 힙 영역에 동일한 문자열이 존재하더라도 항상 새로운 문자열이 생성된다. 

<br>   

+ 문자열 리터럴만을 입력하면 해당 문자열이 `String Pool`(힙 영역)에 저장된다.
+ `String Pool`에 동일한 문자열이 존재하면 새로 생성하지 않고, 기존 문자열을 재활용한다.

<br>   
<br>  
<br>   

**문자열 수정하기!?**
```java
String str = "Spring";
str = "Winter";

System.out.println(str); // "Winter"

```

<br>   

+ String 객체는 한 번 생성되면 수정될 수 없다.
+ 위의 예제는 기존 문자열을 수정하는 게 아니라 새로운 문자열을 재할당하는 것 뿐이다.
+ 문자열을 자주 수정하려면 가변 객체인 `StringBuilder`, `StringBuffer`를 사용하는 게 좋다.

<br>   
<br>  
<br>  
