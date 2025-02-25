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

** 표기법** 
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


