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
numbers[3] = 3;


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

foreach(int number : numbers) {
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

<mark>얇은 복사는 객체의 메모리 주소를 복사하는 방법이다.</mark>

<mark>원본과 복사본이 같은 객체를 가리키기 때문에, 복사본을 수정하면 원본에도 영향이 생긴다.</mark>


<br>   

<mark>깊은 복사는 새로운 객체를 생성하고 요소들을 하나하나 복사하는 방법이다.</mark>

<mark>원본과 복사본이 다른 객체를 가리키기 때문에, 복사본을 수정해도 원본에 영향이 생기지 않는다.</mark>

<mark>1차원 배열의 경우 for 문, System.arraycopy( ), clone( ) 등을 활용하면 깊은 복사가 수행된다. </mark>
