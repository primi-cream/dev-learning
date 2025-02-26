---
title: "Java 기초"
date: 2025-02-26
categories: [Java]
layout: post
tags: [Java, Array]
mermaid: true
---


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
