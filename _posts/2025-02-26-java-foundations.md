---
title: "Java 기본"
date: 2025-02-26
categories: [Java]
layout: post
tags: [Java, Array]
mermaid: true
---

# Java Foundations

## 다차원 배열
- 일차원 배열
<pre><code>
int[] myArray1 = {1, 2, 3, 4, 5};
</code></pre>

- 이차원 배열
<pre><code>
int[][] myArray3 = { {1, 2, 3}, {4, 5, 6} };
int[][][] myArray4 = { { {1, 2}, {3, 4} },{ {5, 6}, {7, 8} } };
</code></pre>
<br>

<details>
<summary>📘 Java 다차원 배열 예제(Click!)</summary>

<pre><code>
package array;

public class Main {
    public static void main(String[] args) {

        // 1. 일차원 배열
        System.out.println("== 일차원 배열 ==");
        int[] myArray = {1, 2, 3};
        System.out.println("myArray[1] = " + myArray[1]);

        for (int i = 0; i < myArray.length; i++) {
            System.out.println(myArray[i]);
        }

        for (int i : myArray) {
            System.out.println(i);
        }

        // 2. 이차원 배열
        System.out.println("== 이차원 배열 ==");
        int[][] myArray2 = { {1, 2, 3}, {4, 5, 6} };
        System.out.println("myArray2[1][2] = " + myArray2[1][2]);

        for (int i = 0; i < myArray2.length; i++) {
            for (int j = 0; j < myArray2[i].length; j++) {
                System.out.println(myArray2[i][j]);
            }
        }

        for (int[] ints : myArray2) {
            for (int anInt : ints) {
                System.out.println("anInt = " + anInt);
            }
        }

        // Q1. 아래와 같이 3x3 행렬을 2차원 배열로 초기화 되어있다.
        // 모든 원소를 1로 변경, 대각 원소는 10으로 변경
        int[][] testArray1 = { {0, 0, 0}, {0, 0, 0}, {0, 0, 0} };

        for (int i = 0; i < testArray1.length; i++) {
            for (int j = 0; j < testArray1[i].length; j++) {
                testArray1[i][j] = 1;

                if (i == j) {
                    testArray1[i][j] = 10;
                }
            }
        }

        for (int[] itemRow : testArray1) {
            for (int itemCol : itemRow) {
                System.out.print(itemCol + " ");
            }
            System.out.println();
        }
    }
}
</code></pre>
</details>

<br><br>

> #### 주요 내용
> 이차원 배열의 사용방식 <br>
{: .block-tip }
<br>

## 클래스(Class) & 객체(Object)
- 실체와 그것을 정의하는 설계도<br>
- 클래스로부터 객체를 선언 (Instance)<br>
<br>
### 클래스의 기본 구조
  
```java
public class 클래스명{
    //객체 변수
    //메소드
    //+접근제어자
    //+static
}

클래스명 객체명 = new 클래스명();
```

<br><br>
### 생성자(Constructor)
- 객체가 생성될 때 자동으로 호출
- 생성자 규칙<br> 1.클래스명과 이름맞추기<br> 2.리턴 타입 없음<br>
<br>

```java
public class 클래스명{
    클래스명(){}
}
```

<br><br>

**this,this()**
- this : 객체 자신을 의미<br>
- this() : 생성자<br>
<br>

<details markdown="1">
<summary>📘 Java Class 예제(Click!)</summary>
    
```java
// Java 프로그래밍 - 클래스와 객체_1

// Car 클래스 - 객체변수, 메서드
class Car {
    String name;
    String type;

    // Car() {}

    public void printCarInfo() {
        System.out.println("== Car Info ==");
        System.out.println("name = " + name);
        System.out.println("type = " + type);
    }

    public void move() {
        System.out.println("이동!");
    }

    public void brake() {
        System.out.println("정지!");
    }
}

// Car2 클래스 - 생성자, this
class Car2 {
    String name;
    String type;

    // Car2() {}

    Car2(String name, String type) {
        this.name = name;
        this.type = type;
        System.out.println("생성자 출력!");
    }

    public void printCarInfo() {
        System.out.println("== Car Info ==");
        System.out.println("name = " + name);
        System.out.println("type = " + type);
    }

    public void load() {
        System.out.println("짐을 주세요!");
    }

    public void horn() {
        System.out.println("빵빵!!");
    }
}

public class Main {
    public static void main(String[] args) {

        // Car 클래스 사용
        Car myCar1 = new Car();
        myCar1.name = "a";
        myCar1.type = "suv";
        myCar1.printCarInfo();
        myCar1.move();
        myCar1.brake();

        // Car2 클래스 사용
        Car2 myCar2 = new Car2("b", "sedan");
        myCar2.printCarInfo();
        myCar2.load();
        myCar2.horn();
    }
}


===========================================================

class Animal {
    String name;
    Double weight;
    String classification;

    Animal(String name, Double weight, String classification) {
        this.name = name;
        this.weight = weight;
        this.classification = classification;
    }

    public void printInfo() {
        System.out.println("name = " + name);
        System.out.println("weight = " + weight);
        System.out.println("classification = " + classification);
    }

    public void eat() {
        System.out.println("냠냠!");
    }

    public void sleep() {
        System.out.println("쿨쿨!");
    }

    public void walk() {
        System.out.println("걷기!");
    }

    public void run() {
        System.out.println("뛰기!");
    }
}

public class Practice {
    public static void main(String[] args) {
        // Test code
        Animal animal1 = new Animal("강아지", 5.0, "포유류");
        Animal animal2 = new Animal("구피", 0.01, "어류");

        animal1.printInfo();
        animal2.printInfo();
    }
}

```
</details>

<br><br>


> #### 주요 내용
> 1. Class의 형태와 사용방식 <br>
> 2. Method의 사용방식 <br>
{: .block-tip }

<br><br>



### 오버로딩(Overloading)
- 한 클래스 내에서 같은 이름의 메소드를 여러 개 정의<br>
- 오버로딩 조건<br>
1. 메소드의 이름이 같아야함<br>
2. 매개변수의 개수 또는 타입이 달라야 함<br>
(리턴타입의 차이로는 오버로딩이 되지 않음)<br>

```java
public class 클래스명{
    클래스명(){}
    클래스명(String name, String type){
        구현 내용;
    }
}
```
<br><br>

### 접근제어자(Access Modifiers)
-  private : 해당 클래스에서만 접근 가능<br>
-  public : 어디서든 접근 가능 <br>
-  default : 해당 패키지 및 상속받은 클래스에서 접근 가능 <br>

<br><br>

### Static
> 변수나 메소드의 특성을 바꾸는 키워드<br>
- Static 특징<br>
1. 메모리에 한번만 할당<br>
2. Static 변수나 메소드는 공유되는 특성을 가짐<br>
- Static 클래스 변수 : 해당 클래스의 각 객체들이 값을 공유<br>
- Static 클래스 메소드 : 객체를 생성하지 않아도 호출 가능
<br><br>


<details markdown="1">
<summary>📘 Java Overloding & Modifier & Static 예제</summary>
```java
// Java 프로그래밍 - 클래스와 객체_2

class Car {
    String name;
    String type;

    Car(String name, String type) {
        this.name = name;
        this.type = type;
    }

    public void printCarInfo() {
        System.out.println("=== Car Info ===");
        System.out.println("name: " + name);
        System.out.println("type: " + type);
    }

    // 오버로딩 구현
    public void printCarInfo(String date) {
        this.printCarInfo();
        System.out.println("date : " + date);
    }

    public void printCarInfo(int number) {
        this.printCarInfo();
        System.out.println("number : " + number);
    }

    public void printCarInfo(String date, int number) {
        this.printCarInfo();
        System.out.println("date : " + date);
        System.out.println("number : " + number);
    }
}

// 접근 제어자 예제
package car;

public class Car2 {
    public String name1;
    private String name2;
    protected String name3;
    String name4;

    public Car2(String name1, String name2, String name3, String name4) {
        this.name1 = name1;
        this.name2 = name2;
        this.name3 = name3;
        this.name4 = name4;
    }
}

// Static 예제
class Car3 {
    // 스태틱 변수
    static String name = "None";
    String type;

    Car3(String name, String type) {
        this.name = name;
        this.type = type;
    }

    public void printCarInfo() {
        System.out.println("=== Car Info ===");
        System.out.println("name: " + name);
        System.out.println("type: " + type);
    }

    // 스태틱 메서드
    public static void getName() {
        System.out.println("Car name: " + name);
    }
}

public class Main {
    public static void main(String[] args) {
        // Car 클래스 사용
        Car myCar1 = new Car("a", "sedan");
        myCar1.printCarInfo();

        // 1. 오버로딩 사용
        System.out.println("=== 오버로딩 사용 ===");
        myCar1.printCarInfo("2022");
        myCar1.printCarInfo(1234);
        myCar1.printCarInfo("2022", 1234);

        // 2. 접근 제어자
        System.out.println("=== 접근 제어자 ===");
        Car2 myCar2 = new Car2("a", "b", "c", "d");
        System.out.println(myCar2.name1);
        // System.out.println(myCar2.name2);  // private 필드라 접근 불가
        // System.out.println(myCar2.name3);  // protected 필드라 같은 패키지에서만 접근 가능
        // System.out.println(myCar2.name4);  // default 필드라 같은 패키지에서만 접근 가능

        // 3. Static
        System.out.println("=== Static ===");
        Car3.getName();
        Car3 myCar3_1 = new Car3("a", "sedan");
        Car3 myCar3_2 = new Car3("b", "suv");
        Car3 myCar3_3 = new Car3("c", "rv");
        myCar3_1.printCarInfo();
        myCar3_2.printCarInfo();
        myCar3_3.printCarInfo();
    }
}

// Practice
// 계산기 덧셈의 여러 타입 오버로딩

class Calculator {
    public int sum(int a, int b) { 
        return a + b; 
    }

    public double sum(double a, double b) {
        return a + b;
    }

    public double sum(String a, String b) {
        return Double.parseDouble(a) + Double.parseDouble(b);
    }

    public int sum(int a, int b, int c) {
        return a + b + c;
    }
}

public class Practice {
    public static void main(String[] args) {
        // Test code
        Calculator c = new Calculator();
        System.out.println(c.sum(1, 2));         // 정수 덧셈
        System.out.println(c.sum(1.0, 2.0));     // 실수 덧셈
        System.out.println(c.sum("1", "2"));     // 문자열 숫자 덧셈
        System.out.println(c.sum(1, 2, 3));      // 세 개의 정수 덧셈
    }
}


```
</details>

<br>

> #### 주요 내용
> Overloading, Access Modifier, Static 의 개념과 사용방식

<br><br>

## 상속(Inheritance)
> 기존 클래스에 기능 추가 및 재정의하여 새로운 클래스를 정의<br>
> - 부모 클래스 : 상속대상이 되는 기존 클래스→ 상위 클래스, 기초클래스
> - 자식 클래스 : 기존 클래스를 상속하는 클래스→ 하위 클래스, 파생 클래스
> 부모 클래스의 필드와 메소드가 상속 (단 생성자, 초기화 블록은 상속되지 않음)
> **다중 상속은 불가능**
> private, default Member는 자식 클래스에서 접근 불가(default의 경우 내부 패키지의 자식 클래스는 가능)

### super,super()
- super : 부모클래스와 자식 클래스의 멤버 이름이 같을 때 구분하는 키워드
- super() : 부모 클래스의 생성자 호출

### 오버라이딩(Overriding)
- 부모 클래스의 메소드를 자식 클래스에서 재정의
- 오버라이딩 조건
1. 메소드의 선언부는 부모 클래스의 메소드와 동일해야함
2. 반환 타입에 한하여 부모 클래스의 반환 타입으로 변환할 수 있는 타입으로 변경 가능
3. 부모 클래스의 메소드보다 접근제어자를 더 좁은 범위로 변경 불가
4. 부모 클래스의 메소드보다 더 큰 범위의 예외 선언 불가

<details markdown="1">
<summary>📘 Java Inheritance & Overriding 예제(Click!)</summary>
```java
// Java 프로그래밍 - 상속

class Person {
    String name;
    int age;
    public int a1;
    private int a2;

    Person() {}

    Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public void printInfo() {
        System.out.println("Person.printInfo");
        System.out.println("name: " + name);
        System.out.println("age: " + age);
    }
}

// Student 클래스 - Person 상속, 접근제어자 확인
class Student extends Person {
    Student() {
        a1 = 1;
        // a2 = 1; // private 변수이므로 접근 불가
    }
}

// Student2 클래스 - Person 상속, super 사용, 오버라이딩
class Student2 extends Person {
    String name;
    int stdId;

    Student2(String name, int age, int stdId) {
        this.name = name;
        // super.name = name; // 부모 클래스의 멤버 변수 직접 접근은 불가
        super(name, age);
        this.age = age;
        this.stdId = stdId;
    }

    @Override
    public void printInfo() {
        System.out.println("Student2.printInfo");
        System.out.println("name: " + name);
        System.out.println("age: " + age);
        System.out.println("stdId: " + stdId);
    }
}

public class Main {
    public static void main(String[] args) {
        // Test code

        // 1. 상속
        System.out.println("===============");
        Student s1 = new Student();
        s1.name = "a";
        s1.age = 25;
        s1.printInfo();

        // 2. super, super(), 오버라이딩
        System.out.println("===============");
        Student2 s2 = new Student2("b", 32, 1);
        s2.printInfo();
    }
}
======================================================================================

// Practice1
// 아래의 클래스 및 상속 관계에서 Test code를 수정하지 않고
// Cat 클래스 내에서 super 또는 super()를 이용하여
// "고양이 입니다." 가 출력될 수 있도록 변경해보세요.

class Animal {
    String desc;

    Animal() {
        this.desc = "동물 클래스 입니다.";
    }

    Animal(String desc) {
        this.desc = desc;
    }

    public void printInfo() {
        System.out.println(this.desc);
    }
}

class Cat extends Animal {
    String desc;

    Cat() {
        super("고양이 입니다.");
    }
}

public class Practice1 {
    public static void main(String[] args) {
        // Test code
        Cat cat = new Cat();
        cat.printInfo();
    }
}

======================================================================================

// Practice2
// 아래 클래스와 상속 관계에서
// Test code를 수정하지 않고, 아래와 같이 출력될 수 있도록 오버라이딩 해보세요.
//
// 빵빵!
// 와이잉!
// 빵빵!
// 삐뽀삐뽀!

class Car {
    Car() {}

    public void horn() {
        System.out.println("빵빵!");
    }
}

class FireTruck extends Car {
    @Override
    public void horn() {
        super.horn();
        System.out.println("와이잉!");
    }
}

class Ambulance extends Car {
    @Override
    public void horn() {
        super.horn();
        System.out.println("삐뽀삐뽀!");
    }
}

public class Practice2 {
    public static void main(String[] args) {
        // Test code
        FireTruck truck = new FireTruck();
        truck.horn();

        Ambulance amb = new Ambulance();
        amb.horn();
    }
}

```
</details>

<br><br>


> #### 주요 정리
> Inheritance의 개념과 사용 및 제한사항 정리 

<br><br>

## 다형성(Polymorphism)
> 한 객체가 여러 가지 타입을 가질 수 있는 것<br>
> 부모클래스 타입의 참조 변수로 자식클래스 인스턴스 참조<br>


```java
class Person{}
class Student extends Person{}

Person p1 = new Student();
// Student s1 = new Person();
```
<br><br>

### instanceof
- 실제 참조하고 있는 인스턴스의 타입 확인

<br>
```java
class Person{}
class Student extends Person{}

Person p1 = new Student();
// Student s1 = new Person();
System.out.println(p1 instanceof Person);
```

<br><br>
<details markdown="1">
<summary>📘 Java Polymorphism 예시(Click!)</summary>
```java
class Person {
    public void print() {
        System.out.println("Person.print");
    }
}

class Student extends Person {
    public void print() {
        System.out.println("Student.print");
    }

    public void print2() {
        System.out.println("Student.print2");
    }
}

class CollegeStudent extends Person {
    public void print() {
        System.out.println("CollegeStudent.print");
    }
}

public class Main {
    public static void main(String[] args) {
        // 1. 다형성
        System.out.println("== 다형성 ==");
        Person p1 = new Person();
        Student s1 = new Student();

        Person p2 = new Student();

        p1.print();
        s1.print();
        s1.print2();
        p2.print();

        Person p3 = new CollegeStudent();
        p3.print();

        // 2. 타입 변환
        System.out.println("== 타입 변환 ==");
        Person pp1 = null;
        Student ss1 = null;

        Person pp2 = new Person();
        Student ss2 = new Student();
        Person pp3 = new Student(); // 업캐스팅

        pp1 = pp2;
        pp1 = ss2;

        ss1 = ss2;
        ss1 = (Student) pp3; // 다운캐스팅

        CollegeStudent cc1;
        CollegeStudent cc2 = new CollegeStudent();
        ss1 = (Student) cc2;
        cc1 = (CollegeStudent) ss2;
    
//      3. instanceof  
        System.out.println("== instanceof ==");
        Person pe1 = new Person();
        Student st1 = new Student();
        Person pe2 = new Student();
        Person pe3 = new CollegeStudent();

        System.out.println(pe1 instanceof Person);
        System.out.println(pe1 instanceof Student);

        System.out.println(st1 instanceof Student);
        System.out.println(st1 instanceof Person);

        System.out.println(pe2 instanceof Person);
        System.out.println(pe2 instanceof Student);

        System.out.println(pe3 instanceof Person);
        System.out.println(pe3 instanceof CollegeStudent);

        if (pe1 instanceof Student) {
            Student stu1 = (Student) pe1;
        }       

        if (st1 instanceof Person) {
            Person per1 = (Person) st1;
        }


    }
}

=============================================================================

// Practice
// 아래의 클래스와 상속 관계에서 다형성을 이용하여
// Car 객체를 통해 아래와 같이 출력될 수 있도록 Test code 부분을 구현해보세요.
// 
// 빵빵!
// 위이잉!
// 삐뽀삐뽀!

class Car {
    Car() {}

    public void horn() {
        System.out.println("빵빵!");
    }
}

class FireTruck extends Car {
    public void horn() {
        System.out.println("위이잉!");
    }
}

class Ambulance extends Car {
    public void horn() {
        System.out.println("삐뽀삐뽀!");
    }
}

public class Practice {
    public static void main(String[] args) {
        // Test code
        Car car = new Car();
        car.horn();

        car = new FireTruck();
        car.horn();

        car = new Ambulance();
        car.horn();

        Car car2[] = {new Car(), new FireTruck(), new Ambulance()};

        for (Car item : car2) {
            item.horn();
        }
    }
}


```
</details>

<br><br>
> ### 주요 사항
> Polymorphism에 대한 개념과 사용방식

<br><br>

## 추상클래스 (Abstract Class)
> 하나 이상의 **추상 메소드**를 포함하는 클래스 <br>
> 반드시 구형해야 하는 부분에 대해 명시적으로 표현 <br>
> 추상 클래스 자체는 객체 생성 불가
```java
abstract class 클래스명{
    ...
    abstract void print();
}
```

<br>

### 추상메소드 (Abstract Method)
- 자식 클래스에서 반드시 오버라이딩 해야하는 메소드
- 선언만하고 구현 내용 없음
```java
abstract void print();
```

<br>

<details markdown="1">
<summary>📘 Java Abstract Class 예시(Click!)</summary>
```java
// Java 프로그래밍 - 추상 클래스

// 추상 클래스 Person
abstract class Person {
    abstract void printInfo();
}

// 추상 클래스 상속
class Student extends Person {
    public void printInfo() {
        System.out.println("Student.printInfo");
    }
}

public class Main {
    public static void main(String[] args) {

        // 추상 클래스의 사용
        // Person p1 = new Person();  // 추상 클래스는 직접 인스턴스화할 수 없음
        Student s1 = new Student();
        s1.printInfo();

        Person p2 = new Person() {  // 익명 클래스 사용
            @Override
            void printInfo() {
                System.out.println("Main.printInfo");
            }
        };
        p2.printInfo();
    }
}

===============================================================================================

// Practice
// 아래 Device 추상 클래스를 이용하여
// UsbPort1 클래스와 WiFi 클래스를 자유롭게 구현해보세요.

abstract class Device {
    int deviceId;

    abstract void deviceInfo();
    abstract void connect();
    abstract void disconnect();
    abstract void send();
    abstract void receive();
}

// UsbPort1 클래스
class UsbPort1 extends Device {
    UsbPort1(int id) {
        this.deviceId = id;
    }

    void deviceInfo() {
        System.out.println("id = " + this.deviceId);
    }

    void connect() {
        System.out.println("연결 하였습니다.");
    }

    void disconnect() {
        System.out.println("연결이 해제되었습니다.");
    }

    void send() {
        System.out.println("데이터를 전송합니다.");
    }

    void receive() {
        System.out.println("데이터를 수신합니다.");
    }
}

// WiFi 클래스
class WiFi extends Device {
    public WiFi(int id) {
        this.deviceId = id;
    }

    @Override
    void deviceInfo() {
        System.out.println("WiFi Device id: " + this.deviceId);
    }

    @Override
    void connect() {
        System.out.println("WiFi에 연결되었습니다.");
    }

    @Override
    void disconnect() {
        System.out.println("WiFi 연결이 해제되었습니다.");
    }

    @Override
    void send() {
        System.out.println("WiFi로 데이터를 전송합니다.");
    }

    @Override
    void receive() {
        System.out.println("WiFi로 데이터를 수신합니다.");
    }
}

public class Practice {
    public static void main(String[] args) {
        // Test code
        UsbPort1 usb1 = new UsbPort1(1);
        WiFi wifi = new WiFi(0);

        usb1.deviceInfo();
        usb1.connect();
        usb1.send();
        usb1.receive();
        usb1.disconnect();

        wifi.deviceInfo();
        wifi.connect();
        wifi.send();
        wifi.receive();
        wifi.disconnect();
    }
}


```
</details>

<br><br>

> #### 주요 내용
> 1. Abstract Class, Method의 사용 및 개념, Inheritance의 사용
> 2. Anonymous class 

<br><br>

### Interface
- 다중 상속처럼 사용할 수 있는 기능
- 추상 메소드와 상수만으로 이루어짐

```java
접근제어자 interface 인터페이스이름{
    public static final 타입 상수이름=값;
    public abstract 반환타입 메소드이름(매개변수);
    ...
}

class 클래스이름 implements 인터페이스이름{
    ...
}
```

- 상속과 동시 사용

```java
접근제어자 interface 인터페이스이름{
...
}

접근제어자 class 클래스이름{
...
}

class 클래스이름 extends 클래스이름 implements 인터페이스이름{
    ...
}
```
<details>
<summary>📘 Java Interface 예제(Click!)</summary>
```java
interface School {
    public static final int MAX_CLASS = 20;
    public static final int MAX_PERSON_PER_CLASS = 40;
    public abstract void printSchool();
}

class Student implements School {
    public void printSchool() {
        System.out.println("00 University");
    }
}

class Person {
    public String name;

    public void printName() {
        System.out.println("Name: " + name);
    }
}

class Student2 extends Person implements School {
    Student2(String name) {
        super.name = name;
    }

    public void printSchool() {
        System.out.println("11 University");
    }
}

public class Main {
    public static void main(String[] args) {

        // 1. 인터페이스 기본 사용
        System.out.println("== 기본 인터페이스 ==");
        Student s1 = new Student();
        s1.printSchool();
        System.out.println(s1.MAX_CLASS);
        System.out.println(s1.MAX_PERSON_PER_CLASS);

        // 2. 다중 상속처럼 사용하기
        System.out.println("== Like 다중 상속 ==");
        Student2 s2 = new Student2("A");
        s2.printSchool();
        s2.printName();
    }
}

===============================================================

// 추상 클래스 GreenOrc
abstract class GreenOrc {
    public final String SKIN_COLOR = "녹색";
    public int health;
    public int attackDamage;
    public int defense;

    public abstract void setHealth();
    public abstract void setDamage();
    public abstract void setDefense();
}

// NPCSystem 인터페이스
interface NPCSystem {
    public abstract void conversationSystem();
    public abstract void questionSystem();
}

// UserSystem 인터페이스
interface UserSystem {
    public abstract void partySystem();
    public abstract void tradeSystem();
}

// OrkNPC1 클래스 - NPCSystem 구현
class OrkNPC1 extends GreenOrc implements NPCSystem {
    @Override
    public void setHealth() {
        this.health = 100;
    }

    @Override
    public void setDamage() {
        this.attackDamage = 10;
    }

    @Override
    public void setDefense() {
        this.defense = 5;
    }

    @Override
    public void conversationSystem() {
        System.out.println("안녕");
        System.out.println("요즘 새로운 소식 없나요?");
    }

    @Override
    public void questionSystem() {
        System.out.println("새로운 퀘스트");
        System.out.println("퀘스트 완료");
    }
}

// OrkUser1 클래스 - UserSystem 구현
class OrkUser1 extends GreenOrc implements UserSystem {
    @Override
    public void setHealth() {
        this.health = 200;
    }

    @Override
    public void setDamage() {
        this.attackDamage = 20;
    }

    @Override
    public void setDefense() {
        this.defense = 10;
    }

    @Override
    public void partySystem() {
        System.out.println("파티 초대");
        System.out.println("파티 수락");
    }

    @Override
    public void tradeSystem() {
        System.out.println("거래 신청");
        System.out.println("거래 완료");
    }
}


```
</details>

<br>

#### 주요 내용
> interface의 사용

<br><br>
