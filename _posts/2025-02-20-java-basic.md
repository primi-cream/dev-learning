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


## Variable

> 📌 Java의 변수와Naming Convention

**변수** : 데이터를 저장하는 메모리 공간에 붙여준 이름
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

**표기법** 
- 카멜 표기법(camelCase) : 가장 앞의 문자는 소문자, 나머지 단어의 첫 문자는 대문자로 표기<br> ex) myName, zeroBase, iPhone, powerPoiont
- 파스칼 표기법(PascalCase) : 각 문자의 첫 문자를 대문자로 표기<br> ex) MyName, ZeroBase, IPhone, PowerPoint
- 스네이크 표기법(snake_case) : 띄어쓰기를 \_(underscore)로 표기<br> ex) my\_name, zero\_base, iphone, power\_point



<details>
<summary>📘 Java Variable 코드 예제(Click!)</summary>

<pre><code>
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

</code></pre>
</details>

> #### 주요 내용
>
> 예약어 사용 X <br>
> 공백 사용 X <br>
> 숫자로 시작 X 
{: .block-tip }

**자료형(Data Type)**: 변수의 종류,단위로 변수의 종류에 따라 담을 수 있는 데이터의 타입과 크기가 다름
- 숫자(Number)
- 부울(Boolean)
- 문자 (Character)
- 문자열(String)

<details>
<summary>📘 Java Data Type 코드예제(Click!)</summary>
<pre><code>
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

</code></pre>
</details>

> #### 주요 내용
>
> float의 경우 f를 뒤에 붙여줄 것 (ex. 1.23f) <br>
> 2진수 → 0b, 8진수 → 0, 16진수 → 0x <br>
> Integer.MIN_VALUE, MAX_VALUE <br>
> Integer.toBinaryString,toOctalString,toHexString <br>
> Type Casting
{: .block-tip }

**문자열(String)**
- 문자들로 이루어진 집합
- String Method : equals, indexOf, replace, substring, toUpperCase

**StringBuffer**
- 문자열을 자주 추가하거나 변경할 때 사용하는 자료형
```java
StringBuffer sb1 = new StringBuffer("Hello World!");
```
- StringBuffer Method : append, insert, substring

**배열(Array)**
- 많은 수의 데이터를 담을 수 있는 자료형
```java
int[] myArray1 = {1,2,3,4,5};
char[] myAraay2 = {'a','b','c','d','e'};
```

<details>
<summary>📘 Java String,Array 예제(Click!)</summary>
<pre><code>
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
</code></pre>
</details>

> #### 주요 내용
> equals와 == 의 차이 (equality, identity)<br>
> indexOf, replace, subString, toUpperCase 등의 문자열 Method<br>
> StringBuffer의 사용방식<br>
> Array의 사용방식
{: .block-tip }

