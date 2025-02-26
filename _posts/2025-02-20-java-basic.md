---
layout: post
title: "Java 기초"
date: 2025-02-25
categories: [Java]
tags: [Java]
---

# Java basic

## Java Platform
> 📌 Java의개발 환경
- Java SE (Standard Edition) : 기본 개발 환경
- Java EE (Enterprise Edition) : 서버 기반 프로그램 개발 환경
- Java ME(Micro Edition) : 모바일, 임베디드 시스템 개발 환경


## Variable & Data Type

> 📌 Java의 변수와Naming Convention

### **변수** : 데이터를 저장하는 메모리 공간에 붙여준 이름
```java
int age = 20;
String country = "Korea";
```

|               변수 규칙               |      예시      |
|:------------------------------:|:--------------:|
| 문자와 숫자,\_(underscore),$ 사용 가능| int apple = 2000;<br>int apple3 = 6000;<br>int \_apple=2000;|
| 숫자로 시작 X | int 3apple = 6000;|
| 대문자와 소문자 구분 | int apple = 2000;<br>int Apple=3000;<br>int APPLE=3500;|
| 공백 사용 X | int one apple = 2000; |
| 미리 예약된 이름 사용 X | int true = 1;<br>int if=2;<br>int coutinue = 10;|

### **표기법** 
- 카멜 표기법(camelCase) : 가장 앞의 문자는 소문자, 나머지 단어의 첫 문자는 대문자로 표기<br> ex) myName, zeroBase, iPhone, powerPoiont
- 파스칼 표기법(PascalCase) : 각 문자의 첫 문자를 대문자로 표기<br> ex) MyName, ZeroBase, IPhone, PowerPoint
- 스네이크 표기법(snake_case) : 띄어쓰기를 \_(underscore)로 표기<br> ex) my\_name, zero\_base, iphone, power\_point



<details markdown="1">
<summary>📘 Java Variable 코드 예제(Click!)</summary>

```java
package variable.java_02_1;

public class Var1 {
    public static void main(String[] args) {

//      1. 변수 사용하기
        System.out.println("== 변수 사용하기 ==");
        int age = 10;
        System.out.println(age);

        String country = "korea";
        System.out.println(country);

//      2. 변수 이름 규칙
        System.out.println("== 변수 이름 규칙 ==");
//      2-1. 문자, 숫자, _(underscore), $ 사용 가능
        int apple = 2000;
        int apple3 = 2000;
        int _apple = 2000;
        int $apple = 2000;

        System.out.println($apple);
        System.out.println("$apple = " + $apple);

//      2-2. 숫자로 시작 X
//      int 3apple = 2000;

//      2-3. 대소문자 구분
        int apple5 = 1000;
        int Apple5 = 2000;

//      2-4. 공백 사용 X
        int one_apple = 1000;
        int oneApple = 1000;

//      2-5. 예약어 사용 X
//      예약어 예시 : true, false, if, switch, for, continue, break;


//      참고) 한글 사용 가능
        int 사과 = 1000;
        System.out.println("사과 = " + 사과);

//      3.표기법
//      3-1. 카멜 표기법 (camelCase)
//      변수, 함수
        int myAge = 10;
        int oneApplePrice = 1000;

//      3-2. 파스칼 표기법 (PascalCase)
//      클래스
        int MyAge = 10;
        int OneApplePrice = 1000;


//      참고) 스네이크 표기법 (snake_case)
//      사용 X
        int my_age = 10;
        int one_apple_price = 1000;

    }
}

```
</details>
<br>

> #### 주요 내용
>
> 1. 예약어 사용 X <br>
> 2. 공백 사용 X <br>
> 3. 숫자로 시작 X 
{: .block-tip }

<br>


### **자료형(Data Type)**: 변수의 종류,단위로 변수의 종류에 따라 담을 수 있는 데이터의 타입과 크기가 다름
- 숫자(Number)
- 부울(Boolean)
- 문자 (Character)
- 문자열(String)

<details markdown="1">
<summary>📘 Java Data Type 코드예제(Click!)</summary>
```java
package variable.java_02_2;

public class Var2 {
    public static void main(String[] args) {

//      1. 자료형 - 숫자
        System.out.println("== 숫자 ==");

//      1-1. 정수
        int intNum = 10;
        System.out.println("intNum = " + intNum);

        System.out.println(Integer.MIN_VALUE);
        System.out.println(Integer.MAX_VALUE);

        int intNum2 = Integer.MAX_VALUE;
        System.out.println("intNum2 = " + intNum2);
        int intNum3 = Integer.MAX_VALUE + 1;
        System.out.println("intNum3 = " + intNum3);
        long longNum = (long) Integer.MAX_VALUE + 1;
        System.out.println("longNum = " + longNum);


//      1-2. 실수
        float floatNum = 1.23f;
        double doubleNum = 1.23;
        System.out.println(Float.MAX_VALUE);
        System.out.println(Double.MAX_VALUE);


//      1-3. 2진수 / 8진수 / 16진수
        int numBase2 = 0b1100;
        System.out.println("numBase2 = " + numBase2);
        int numBase8 = 014;
        System.out.println("numBase8 = " + numBase8);
        int numBase16 = 0xC;
        System.out.println("numBase16 = " + numBase16);

        System.out.println("0b" + Integer.toBinaryString(numBase2));
        System.out.println("0" + Integer.toOctalString(numBase8));
        System.out.println("0x" + Integer.toHexString(numBase16));

//      2. 자료형 - 부울
        System.out.println("== 부울 ==");
        boolean isPass = true;
        System.out.println("isPass = " + isPass);
        boolean isOk = false;
        System.out.println("isOk = " + isOk);

//      3. 자료형 - 문자
        System.out.println("== 문자 ==");
        char keyFirst = 'a';
        System.out.println("keyFirst = " + keyFirst);
        char keyLast = 'z';
        System.out.println((int)keyFirst);
        System.out.println((int)keyLast);
    }
}

```
</details>

<br>
> #### 주요 내용
>
> 1. float의 경우 f를 뒤에 붙여줄 것 (ex. 1.23f) <br>
> 2. 2진수 → 0b, 8진수 → 0, 16진수 → 0x <br>
> 3. Integer.MIN_VALUE, MAX_VALUE <br>
> 4. Integer.toBinaryString,toOctalString,toHexString <br>
> 5. Type Casting
{: .block-tip }

<br><br>


### **문자열(String)**
- 문자들로 이루어진 집합
- String Method : equals, indexOf, replace, substring, toUpperCase

### **StringBuffer**
- 문자열을 자주 추가하거나 변경할 때 사용하는 자료형
```java
StringBuffer sb1 = new StringBuffer("Hello World!");
```
- StringBuffer Method : append, insert, substring

### **배열(Array)**
- 많은 수의 데이터를 담을 수 있는 자료형
```java
int[] myArray1 = {1,2,3,4,5};
char[] myAraay2 = {'a','b','c','d','e'};
```

<br>
<details markdown="1">
<summary>📘 Java String,Array 예제(Click!)</summary>
```java
package variable.java_02_3;

public class Var3 {
    public static void main(String[] args) {

//      1.자료형 - 문자열
        System.out.println("== 문자열 ==");
        String s1 = "Hello World!";
        System.out.println("s1 = " + s1);
        String s2 = "01234";
        System.out.println("s2 = " + s2);


//      1-1. equals
        String s3 = "Hi";
        String s4 = "Hi";
        System.out.println(s3.equals(s4));
        System.out.println(s3 == s4);
        String s5 = new String("Hi");
        System.out.println(s3.equals(s5));
        System.out.println(s3 == s5);

//      1-2. indexOf
        String s6 = "Hello! World!";
        System.out.println(s6.indexOf("!"));
        System.out.println(s6.indexOf("!", s6.indexOf("!") + 1));

//      1-3. replace
        String s7 = s6.replace("Hello", "Bye");
        System.out.println("s7 = " + s7);

//      1-4. subString
        System.out.println(s7.substring(0, 3));
        System.out.println(s7.substring(0, s7.indexOf("!") + 1));

//      1-5. toUpperCase
        System.out.println(s7.toUpperCase());

//      2. 자료형 - StringBuffer
        System.out.println("== StringBuffer ==");
        StringBuffer sb1 = new StringBuffer();
        sb1.append("01234");
        System.out.println("sb1 = " + sb1);
        sb1.append("56789");
        System.out.println("sb1 = " + sb1);

        String a = "01234";
        String b = "56789";
        String bak = a;
        System.out.println(a == bak);

        a += b;
        System.out.println(a);
        System.out.println(a == bak);


//      3. 자료형 - 배열
        System.out.println("== 배열 ==");
        int[] myArray1 = {1, 2, 3, 4, 5};
        System.out.println(myArray1[0]);
        System.out.println(myArray1[1]);
        System.out.println(myArray1[2]);
        System.out.println(myArray1[3]);
        System.out.println(myArray1[4]);

        char[] myArray2 = {'a', 'b', 'c', 'd', 'e'};
        System.out.println(myArray2[2]);

        String[] myArray3 = new String[3];
        myArray3[0] = "Hello";
        myArray3[1] = " ";
        myArray3[2] = "World!";
        System.out.println(myArray3[0] + myArray3[1] + myArray3[2]);
    }
}
```
</details>

<br>
> #### 주요 내용
> 1. equals와 == 의 차이 (equality, identity)<br>
> 2. indexOf, replace, subString, toUpperCase 등의 문자열 Method<br>
> 3. StringBuffer의 사용방식<br>
> 4. Array의 사용방식
{: .block-tip }


<br><br>
### **리스트(List)**
- 배열과 같이 여러 데이터를 담을 수 있는 자료형
- 추가로 여러가지 Method 제공
```java
ArrayList l1 = new ArrayList();
l1.add(1);
```
- 리스트 Method : add, get, size, remove, clear, sort, contains


### **맵(Map)**
- key,value 형태로 데이터를 저장하는 자료형
```java
HashMap<String,String>map = new HashMap<String,String>();
map.put("product","kiwi");
map.put("price","9000");
```
- Map Method : put, get, size, remove, containsKey


### **제네릭스(Generics)**
- 자료형을 명시적으로 지정
- 제한적일 수 있으나 안정성을 높여주고 형변환을 줄여줌
```java
ArrayList<String> l1 = new ArrayList<String>();
HashMap<String,Integer> map1 = new HashMap<String,Integer>();
```
<br>

<details markdown="1">
<summary>📘 Java List,Map 예제(Click!)</summary>
```java
package variable.java_02_4;

import java.util.ArrayList;
import java.util.Comparator;
import java.util.HashMap;

public class Var4 {
    public static void main(String[] args) {

//      1. 자료형 - 리스트
        System.out.println("== 리스트 ==");
        ArrayList l1 = new ArrayList();

//      1-1. add
        l1.add(1);
        l1.add("hello");
        l1.add(2);
        l1.add(3);
        l1.add(4);
        l1.add("world");
        System.out.println("l1 = " + l1);

        l1.add(0, 1);
        System.out.println("l1 = " + l1);

//      1-2. get
        System.out.println(l1.get(0));
        System.out.println(l1.get(3));


//      1-3. size
        System.out.println(l1.size());

//      1-4. remove
        System.out.println(l1.remove(0));
        System.out.println("l1 = " + l1);

        System.out.println(l1.remove(Integer.valueOf(2)));
        System.out.println("l1 = " + l1);

//      1-5. clear
        l1.clear();
        System.out.println("l1 = " + l1);

//      1-6. sort
        ArrayList l2 = new ArrayList();
        l2.add(5);
        l2.add(3);
        l2.add(4);
        System.out.println("l2 = " + l2);

        l2.sort(Comparator.naturalOrder());
        System.out.println("l2 = " + l2);
        l2.sort(Comparator.reverseOrder());
        System.out.println("l2 = " + l2);

//      1-7. contains
        System.out.println(l2.contains(1));
        System.out.println(l2.contains(3));

//      2. Maps
        System.out.println("== Maps ==");
        HashMap map = new HashMap();

//      2-1. put
        map.put("kiwi", 9000);
        map.put("apple", 10000);
        map.put("mango", 12000);
        System.out.println("map = " + map);

//      2-2. get
        System.out.println(map.get("mandarine"));
        System.out.println(map.get("kiwi"));

//      2-3. size
        System.out.println(map.size());

//      2-4. remove
        System.out.println(map.remove("kiwi"));
        System.out.println(map.remove("mandarine"));
        System.out.println(map.remove("map = " + map));

//      2-5. containsKey
        System.out.println(map.containsKey("apple"));
        System.out.println(map.containsKey("kiwi"));

//      3. Generics
        System.out.println("== Generics ==");
        ArrayList l3 = new ArrayList();
        l3.add(1);
        l3.add("hello");
        System.out.println("l3 = " + l3);

        ArrayList<String> l4 = new ArrayList<String>();
        l4.add("hello");
        System.out.println("l4 = " + l4);

        HashMap map1 = new HashMap();
        map1.put(123, "id");
        map1.put("appple", 10000);
        System.out.println("map1 = " + map1);
        
        HashMap<String, Integer> map2 = new HashMap<>();
//      map2.put(123, "id");
        map2.put("apple", 10000);
        System.out.println("map2 = " + map2);
    }
}

```
</details>


<br>
> #### 주요 내용
> 1. sort → Comparator.reverseOrder
> 2. contains → list.contains(찾을 값);
{: .block-tip }

<br><br>

## Operation

### **Term & Operator**
- 단항 연산자 : 항이 한 개 
```java
num++
```
- 이항 연산자 : 항이 두 개 
```java
1 + 1
```
- 삼항 연산자 : 항이 세 개 
```java
(3 > 1) ? 1 : 0
```
- 대입 연산자 : 우측의 데이터를 좌측의 변수에 대입 
```java
int num = 100;
```
- 부호 연산자 : 부호를 나타내는 연산자 
```java
+10, -10
```
- 산술 연산자 : +,-,\*,/,% 
```java
10 % 3
```
- 증가/감소 연산자 : 값을 1만큼 늘리거나(++), 1만큼 줄임(--) 
```java
num++, ++num, num--, --num
```
- 관계 연산자(>, <, >=, <=, ==, !=) : 두 항의 값 크기를 비교하며 결과 값은 true,false 
```java
10 > 9 // true
```
- 논리 연산자(&&, ||, !) : 논리식에 대해 참 거짓을 판단하며 결과값은 ture,false 
```java
(10 > 9) && (1 == 0)
```
- 복합 대입 연산자: 대입 연산자와 다른 연산자를 조합한 연산
```java
num1 += num2; // num1 = num1 + num2 
```
<br>
<details markdown="1">
<summary>📘 Java opration 예제(Click!)</summary>
```java
package variable.java_03_1;

public class Operation {
    public static void main(String[] args) {

//      1. 대입 연산, 부호 연산자
        int num = 100;
        num = +10;
        num = 10;
        num = -10;

//      2. 산술 연산자, 증가/감소 연산자
        System.out.println("== 산술 연산자, 증가/감소 연산자 ==");
        int numX = 10;
        int numY = 3;
        int result = 0;
        result = numX + numY;
        result = numX - numY;
        result = numX * numY;
        result = numX / numY;
        result = numX % numY;
        System.out.println("result = " + result);

        int numZ = 1;
        System.out.println(numZ++);
        System.out.println(numZ);

        numZ = 1;
        System.out.println(numZ--);
        System.out.println(numZ);

        numZ = 1;
        System.out.println(--numZ);
        System.out.println(numZ);

//      3. 관계 연산자
        System.out.println("== 관계 연산자 ==");
        int numA = 10;
        int numB = 9;

        System.out.println(numA > numB);
        System.out.println(numA < numB);
        System.out.println(numA == numB);
        System.out.println(numA != numB);


//      4. 논리 연산자
        System.out.println("== 논리 연산자 ==");
        System.out.println((10 > 9) && (1 == 0));
        System.out.println((10 > 9) || (1 == 0));

//      5. 복합 대입 연산자
        System.out.println("== 복합 대입 연산자 ==");
        int num1 = 10;
        int num2 = 5;
        num1 += num2;
        System.out.println("num1 = " + num1);
        num1 -= num2;
        num1 *= num2;

//      6. 삼항 연산자
        System.out.println("== 삼항 연산자 ==");
        int a = 100;
        String aResult = (a == 100) ? "yes" : "no";
        System.out.println("aResult = " + aResult);

    }
}

```
</details>
<br><br>

> #### 주요 내용
> 각 연산자의 사용법<br>
> Prifix,Postfix의 차이점 → 현재값의 증감시기의 반환 전/후로 나눠짐
{: .block-tip }
<br>

### **비트 연산자(Bitwise Operators)**
- 비트 단위의 연산 (2진법 - Binary)
| 연산자 | 설명 | 예제 (`a = 5 (0101)`, `b = 3 (0011)`) |
|:--------:|:-----------------:|:------------------:|
| `&` (AND) | 둘 다 1일 때만 1 | `a & b` → `0001` (1) |
| `|` (OR) | 하나라도 1이면 1 | `a | b` → `0111` (7) |
| `^` (XOR) | 다르면 1 | `a ^ b` → `0110` (6) |
| `~` (NOT) | 비트를 반전 (1 → 0, 0 → 1) | `~a` → `1111...1010` (-6, 2의 보수 표현) |
| `<<` (Left Shift) | 왼쪽으로 N비트 이동 | `a << 1` → `1010` (10) |
| `>>` (Right Shift) | 오른쪽으로 N비트 이동 (부호 유지) | `a >> 1` → `0010` (2) |
| `>>>` (Unsigned Right Shift) | 부호 비트 포함하여 이동 | `a >>> 1` → `0010` (2, 부호 고려 X) |

<br>
<details markdown="1">
<summary>📘 Java Bitwise Operators 예제 (Click!)</summary>
```java
package variable.java_03_2;

public class Operation2 {
    public static void main(String[] args) {

//      1. 비트 논리 연산자
        System.out.println("== 비트 논리 연산자 ==");
//      1-1. AND 연산자 (&)
        System.out.println("== & ==");
        int num1 = 5; // 0101
        int num2 = 3; // 0011
        int result = 0;

        result = num1 & num2; // 0001
        System.out.println("result = " + result);
        System.out.println(Integer.toBinaryString(num1));
        System.out.printf("%04d\n", Integer.parseInt(Integer.toBinaryString(num1)));
        System.out.printf("%04d\n", Integer.parseInt(Integer.toBinaryString(num2)));
        System.out.printf("%04d\n", Integer.parseInt(Integer.toBinaryString(result)));

//      1-2. OR 연산자 (|)
        System.out.println("== | ==");

        result = num1 | num2; // 0111
        System.out.println("result = " + result);
        System.out.printf("%04d\n", Integer.parseInt(Integer.toBinaryString(num1)));
        System.out.printf("%04d\n", Integer.parseInt(Integer.toBinaryString(num2)));
        System.out.printf("%04d\n", Integer.parseInt(Integer.toBinaryString(result)));

//      1-3. XOR 연산자 (^)
        System.out.println("== XOR ==");

        result = num1 ^ num2;
        System.out.println("result = " + result);
        System.out.printf("%04d\n", Integer.parseInt(Integer.toBinaryString(num1)));
        System.out.printf("%04d\n", Integer.parseInt(Integer.toBinaryString(num2)));
        System.out.printf("%04d\n", Integer.parseInt(Integer.toBinaryString(result)));

//      1-4. 반전 연산자 (~)
        System.out.println("== ~ ==");
        num1 = 5;

        result = ~num1;
        System.out.println("result = " + result);
        System.out.printf("%04d\n", Integer.parseInt(Integer.toBinaryString(num1)));
        System.out.printf("%s\n", Integer.toBinaryString(result));

//      2. 비트 이동 연산자
        System.out.println("== 비트 이동 연산자 ==");

//      2-1. <<  연산자
        int numA = 3;
        result = numA << 1;

        System.out.println("numA = " + numA);
        System.out.printf("%04d\n", Integer.parseInt(Integer.toBinaryString(numA)));
        System.out.printf("%04d\n", Integer.parseInt(Integer.toBinaryString(result)));

//      2-2. >> 연산자
        result = numA >> 1;
        System.out.println("result = " + result);
        System.out.printf("%04d\n", Integer.parseInt(Integer.toBinaryString(numA)));
        System.out.printf("%04d\n", Integer.parseInt(Integer.toBinaryString(result)));

//      2-3. >>> 연산자
        numA = -5;
        result = numA >> 1;
        System.out.printf("%s\n", Integer.toBinaryString(numA));
        System.out.printf("%s\n", Integer.toBinaryString(result));

        result = numA >>> 1;
        System.out.printf("%s\n", Integer.toBinaryString(numA));
        System.out.printf("%s\n", Integer.toBinaryString(result));
    }
}

```
</details>

<br><br>

> #### 주요 내용
> 논리 연산 (AND, OR, XOR, NOT) <br>
> 비트 이동 연산 (<<, >>, >>>) → Shift Operation<br>
{: .block-tip }
<br>

## 조건문(Conditional Statement)
### **if**
- 조건에 따라 무엇을 실행할지 판단하는 분기 구조
```java
if(조건문1) {
    조건문1을 만족할 때 실행
} else if(조건문2){
    조건문2를 만족할 때 실행
} else {
    그 외의 상황에서 실행
}
```
<br>

### **Switch**
- 입력 값에 따라 어떤 case를 실행할지 판단하는 분기 구조
```java
switch(입력값){
    case 입력값1:
        실행할 내용;
        break;
    case 입력값2:
        실행할 내용;
        break;
    ...
    default:
        실행할 내용;
        break;
}
```

<br>
<details markdown="1">
<summary>📘 Java Conditional Statements 예제(Click!)</summary>
```java
package conditional;

public class Main {
    public static void main(String[] args) {

//      1. 조건문 - if
        System.out.println("== if ==");
        int waterTemperature = 100;

        if(waterTemperature >= 100){
            System.out.println("물이 끓습니다.");
        } else {
            System.out.println("물을 끓이는 중입니다.");
        }

        int score = 90;
        char grade = 'A';

        if(score >= 90) {   // 조건이 true 일 때 else if는 실행하지 않는다.
            grade = 'A';
        } else if(score >= 80){
            grade = 'B';
        } else if(score >= 70){
            grade = 'C';
        } else {
            grade = 'D';
        }
        System.out.println("grade = " + grade);

//      2. 조건문 - switch
        System.out.println("== switch ==");
        String fruit = "apple2";

        switch(fruit){
            case "apple" :
                System.out.println(fruit + "은 500원 입니다.");
                break;
            case "blueberry" :
                System.out.println(fruit + "은 10000원 입니다.");
                break;
            default:
                System.out.println("해당 과일이 없습니다.");
                break;
        }

//      Q1. number의 값이 홀수인지 짝수인지 판단하는 코드를 작성하세요.
        int number = 5;
        if(number % 2 == 0){
            System.out.println("짝수 입니다.");
        } else {
            System.out.println("홀수 입니다.");
        }

//      Q2. 아래 주석은 위의 실습에서 진행한 score에 따라 grade를 출력하는 코드이다.
//        이를 switch 조건문 기반으로 바꿔보세요.
//        int score = 90;
//        char grade = 0;
//
//        if(score >= 90) {   // 조건이 true 일 때 else if는 실행하지 않는다.
//            grade = 'A';
//        } else if(score >= 80){
//            grade = 'B';
//        } else if(score >= 70){
//            grade = 'C';
//        } else {
//            grade = 'D';
//        }
//        System.out.println("grade = " + grade);

        score = 85;
        grade = 0;

        switch(score / 10){
            case 9:
                grade = 'A';
                break;
            case 8:
                grade = 'B';
                break;
            case 7:
                grade = 'C';
                break;
            default:
                grade = 'F';
                break;
        }
        System.out.println("grade = " + grade);
    }
}

```
</details>

<br><br>

> #### 주요 내용
> if와 switch문의 사용법<br>
{: .block-tip }
<br><br>

## 반복문(Loop Statement)

### **for**
- 주어진 횟수만큼 반복하여 실행하는 구조
```java
for(초기치;조건문;증가치;){
    반복하여 실행할 내용;
}
```

<br><br>

### **while/do-while**
- 조건문이 만족하는 동안 반복하여 실행하는 구조
```java
while(조건문){
    반복하여 실행할 내용;
}

do{
    반복하여 실행할 내용;
}while(조건문);
```
<br>

<details markdown="1">
<summary>📘 Java Loop Statements(Click!) </summary>
```java
package loop;

public class Main {
    public static void main(String[] args) {

//       1. 반복문 - for
         System.out.println("== for ==");
//       1-1. 기본 사용 방법
         for (int i = 0; i < 5; i++) {
             System.out.println(i);
         }

         for(int i = 0; i < 5; i++){
             for(int j = 0; j < i + 1; j++){
                 System.out.print("*");
             }
             System.out.println();
         }

         System.out.println();
         for (int i =0; i < 5; i++){
             if(i == 2){
                 continue;
             }

             for(int j = 0; j < i + 1; j++){
                 System.out.print("*");
             }
             System.out.println();
         }


        System.out.println();
        for (int i =0; i < 5; i++){
            if(i == 2){
                break;
            }

            for(int j = 0; j < i + 1; j++){
                System.out.print("*");
            }
            System.out.println();
        }


//      1-2. for each
        System.out.println("== for each ==");
        int[] nums = {1, 2, 3, 4, 5};
        for (int i = 0; i < nums.length; i++) {
            System.out.println(nums[i]);
        }

        for(int num : nums){
            System.out.println(num);
        }


//      2. 반복문 - while
        System.out.println("== while ==");
//      2-1. while
        int i = 0;
        while (i < 5) {
            System.out.println(i++);
        }

        System.out.println();
        i = 0;
        while (i < 5) {
            if(i == 2){
                i++;
                continue;
            }

            System.out.println(i++);
        }


//      2-2. do-while
        System.out.println("== do-while ==");
        boolean knock = false;
        do{
            System.out.println("knock");
        } while(knock);


        System.out.println("== Q1 ==");
//      Q1. 아래와 같은 출력 결과를 반복문과 조건문을 이용하여 출력해보세요.
//      *
//      ***
//      *****
//      *******
        for(int j = 0; j < 8; j++){
            if(j % 2 == 0){
                continue;
            }

            for(int k = 0; k < j; k++){
                System.out.print("*");
            }
            System.out.println();
        }


        System.out.println("== Q2 ==");
//      Q2. 반복문을 실행할 때마다 물 온도를 1도씩 올리고 100도가 되면 종료한다.
//        추가로, 10도, 20도, ... 10도 간격으로 물 온도를 출력하시오.
        int waterTemperature = 0;

        while(waterTemperature < 100){
            waterTemperature++;

            if(waterTemperature % 10 == 0){
                System.out.println(waterTemperature + "도 입니다.");
            }
        }

    }
}

```
</details>
<br><br>

> #### 주요 내용
> 1. countinue, break의 사용법<br>
> 2. for, while, do-while의 사용법과 차이 <br>
{: .block-tip }
<br>


