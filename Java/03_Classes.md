## 01. 클래스

<br>   

**객체**

+ 객체는 고유한 속성과 기능을 가지는 유일무이한 존재로서, 서로 다른 객체들과 상호작용한다.
+ 객체의 속성은 `필드(field)`를 통해 표현되며, 기능은 `메소드(method)`를 통해 구현된다.
+ 객체는 메소드를 통해 다른 객체와 상호작용하면서 프로그램 내에서 다양한 작업을 수행한다.

<br>   
<br>   

**클래스**

+ 클래스는 동일한 요소를 가지는 객체들의 집합이며, 객체의 요소를 설계하는 템플릿이다.
+ 클래스에 기반하여 생성된 객체를 해당 클래스의 `인스턴스(instance)`라고 한다.
+ 클래스를 사용하면 코드가 재사용되며, 유지보수성과 모듈성을 향상시킬 수 있다.

<br>   
<br>   
<br>   
<br>   

## 02. 메소드

<br>   

**메소드 오버로딩**
```java
class Person {

    void introduce() {
        System.out.println("안녕하세요. 저는 사람입니다.");
    }

    void introduce(String name) {
        System.out.println("안녕하세요. 저는 " + name + "입니다.");
    }

    void introduce(String name, int age) {
        System.out.println("안녕하세요. 저는 " + age + "세 " + name + "입니다.");
    }

}
```

<br>   

```java
Person p = new Person();

p.introduce();               // 안녕하세요. 저는 사람입니다.
p.introduce("김진우");        // 안녕하세요. 저는 김진우입니다.
p.introduce("김진우", 30);    // 안녕하세요. 저는 30세 김진우입니다.
```

<br>   

+ `메소드 오버로딩`이란 이름이 같지만 매개변수 리스트가 다른 메소드들을 정의하는 것이다.
+ 입력된 매개변수에 따라 적절한 메소드가 호출된다.
+ 반환 타입만 다르게 해서는 오버로딩이 불가능하다.
  
<br>   
<br>   
<br>   

**가변인자 메소드**
```java
class Calculator {

    int sum(int... numbers) {

        int total = 0;

        for(int num : numbers) {
            total += num;
        }

        return total;

    }
}
```

<br>   

```java
Calculator calc = new Calculator();

System.out.println(calc.sum(1, 2, 3));         // 6
System.out.println(calc.sum(1, 2, 3, 4, 5));   // 15
```

<br>   

+ 오버로딩은 매개변수 개수에 따라 여러 개의 메소드를 선언해야 한다.
+ 가변인자 메소드는 개수와 상관없이 유연하게 전달받을 수 있다.

<br>   
<br>   
<br>   
<br>   
<br>   

## 03. 생성자

<br> 

**생성자란?**
```java
class Person {

    // 필드

    String name;
    int age;

    // 생성자

    Person() {
        this.name = "한유진";
        this.age = 15;
    }

    Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
```

<br>   

+ 생성자는 객체가 생성될 때 자동으로 호출되어, 객체를 초기화한다.
+ 생성자는 클래스와 이름이 같으며, 리턴 타입이 없다.
+ 생성자는 여타 메소드처럼 오버로딩이 가능하다.
+ 개발자가 생성자를 명시하지 않으면 컴파일러가 기본 생성자를 추가한다.

<br>   
<br>   
<br>   

**같은 클래스의 다른 생성자 호출하기**
```java
class Player {

    // 필드

    String name;
    String city;
    int grade;

    // 생성자

    Player(String name) {
        this(name, "무소속", 4);
    }

    Player(String name, String city) {
        this(name, city, 4);
    }

    Player(String name, String city, int grade) {
        this.name = name;
        this.city = city;
        this.grade = grade;
    }
}
```

<br>   

```java
Player p1 = new Player("엠버");
Player p2 = new Player("노엘", "몬드");
Player p3 = new Player("유라", "몬드", 5);
```

<br>   

+ this( ) 메소드를 활용하면 생성자들 간의 코드 중복을 줄일 수 있다.
+ this( ) 메소드는 생성자의 첫 번째 줄에서만 가능하다.

<br>   
<br>   
<br>   
<br>   
<br>   

## 04. 접근 제어자

<br>   

```java
package p1;

public class A {

    public int publicVar; 
    protected int protectedVar; 
    int defaultVar;
    private int privateVar;

    // 해당 클래스
    // 접근 가능 : publicVar, protectedVar, defaultVar, privateVar
}


class B {
    // 같은 패키지의 다른 클래스
    // 접근 가능 : publicVar, protectedVar, defaultVar
}
```

<br>   

```java
package p2;

class C {
    // 다른 패키지의 다른 클래스
    // 접근 가능 : publicVar
}

class D extends A {
    // 다른 패키지의 자식 클래스
    // 접근 가능 : publicVar, protectedVar
}
```

<br>   

+ private : 해당 클래스에서만 접근 가능
+ default : 같은 패키지의 모든 클래스에서 접근 가능
+ protected : 같은 패키지의 모든 클래스, 다른 패키지의 자식 클래스에서 접근 가능
+ public : 모든 클래스에서 접근 가능

<br>   
<br>   
<br>   
<br>   
<br>   

## 05. static

<br>   

```java
class Player {

    // 정적 필드
    static int count = 0;

    // 인스턴스 필드
    int salary;

    Player(int salary) {
        this.salary = salary;
        count++; 
    }

}
```

<br>   

```java
System.out.println(Player.count);  // 0

Player p1 = new Player(300);
Player p2 = new Player(200);

System.out.println(p1.count);      // 2
System.out.println(p2.count);      // 2

System.out.println(p1.salary);     // 300
System.out.println(p2.salary);     // 200
```

<br>   

+ 정적 멤버는 static 키워드가 붙어 있는 멤버다.
+ 정적 멤버는 클래스 자체에 속하기 때문에, 모든 객체들이 공유한다.
+ 객체를 생성하지 않아도 정적 멤버를 사용할 수 있다.
+ 정적 메소드에서는 인스턴스 멤버, this 키워드를 사용할 수 없다.

<br>   

+ 인스턴스 멤버는 static 키워드가 없는 멤버다.
+ 인스턴스 멤버는 각각의 객체에 속하며, 객체마다 개별적으로 갖고 있다.
+ 객체를 생성해야만 인스턴스 멤버를 사용할 수 있다.
+ 인스턴스 메소드에서는 정적 멤버와 인스턴스 멤버 모두 사용할 수 있다.

<br>   
<br>   
