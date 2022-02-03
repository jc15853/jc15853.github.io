---
title: "<small>[Algorithm]</small> 동적 계획법(Dynamic Programing, DP)"
excerpt: ""

categories:
  - Algorithm
tags:
  - [Algorithm, DP]

permalink: /algorithm/dp/

toc: true
toc_sticky: true
 
date: 2022-01-27
last_modified_at: 2022-01-27
---

## 📌 동적 계획법이란?
  
  > **큰 문제**를 **작은 문제**로 나눠서 풀어 **큰 문제**를 해결하는 방법 

## 📌 예) n번째 Fibonacci 항 구하기

### 재귀 함수로 구현
    
  ```java
  int fib(int n) {
    if (n <= 1)
      return n;
    else 
      return fib(n-1) + fib(n-2);
  }
  ```
  - 똑같은 함수가 재귀적으로 호출됩니다.  
    fib(4)를 구하기 위해서 fib(3)과 fib(2)를, f(3)을 구하기 위해서 fib(2)와 fib(1)을, ...  
    <img src="/assets/images/posts_img/algorithm_dp/00.png" width="300">{: .align-center}
  - n이 커지면 커질수록 수행 시간이 기하급수적으로 늘어나고 엄청난 스택이 쌓입니다.

  - 이때 동적 계획법을 사용하면 효율적으로 문제를 해결할 수 있습니다.

    **다만!** 아래의 조건을 만족할 때 사용이 가능합니다.  
    ① <mark>큰 문제를 작은 문제로 나눌 수 있다.</mark>  
    ② <mark>작은 문제에서 구한 정답은 그것을 포함하는 큰 문제에서도 동일하다.</mark>  

<br>

### 동적 계획법으로 구현

#### <font color="#C0392B">메모이제이션(memoization)</font>

- 동적 계획법을 구현하는 방법 중 하나로,  
      
  > 중복된 계산을 막기 위해<br>**한 번 구한 결과를 배열에 저장한 다음, 후에 다시 호출할 때 저장된 값을 이용하는 것**입니다.

- 따라서, 시간 복잡도가 훨씬 줄어들게 됩니다.  
- 캐싱(Caching)이라고도 합니다.

<br>

#### Top-down 방식
  
```java
int[] f = new f[100]; // 배열 초기화
int fib2(int n) {
  if (n <= 1)
    return n;
      
  if (f[n])
    return f[n];

  f[n] = fib2(i-1) + fib2(i-2);
  return f[n];
}
```
- <mark>메모이제이션</mark>을 사용합니다.
- 하위의 결과를 계속 참조하면서 피보나치 수열의 큰값을 단계적으로 구하고 있다.
- fib2(4)를 호출할 경우, fib2(2)의 결과는 이미 f[2]에 저장되어 있습니다
    <img src="/assets/images/posts_img/algorithm_dp/01.png" width="300">{: .align-center}
- 값이 필요하면 배열에 이미 저장된 값을 불러오면 됩니다. (여러번 계산할 필요 X)

<br>

#### Bottom-up 방식
```java
int[] f = new f[100]; // 배열 초기화
int fib2(int n) {
  f[0] = 0;
  f[1] = 1;      

  for (i=2; i<=n; i++) {
    f[i] = f[i-1] + f[i-2];
  }

  return f[n];
}
```
Top-down 방식과 달리, for문을 이용해서 앞의 값으로부터 다음 값을 계산해 나가는 방식입니다.

<br>

## 📌 알고리즘 개발절차
  
  1. 주어진 문제를 여러 개의 <mark>작은 문제로 <b>분할</b></mark>한다.  
  2. 가장 작은 부분 문제<font color="grey">(종료 조건, 주로 0 또는 1일 때)</font>부터 해를 구하여 <b>저장</b>한다 → <mark>메모이제이션</mark>  
  3. 더 큰 문제의 해를 구할 때 메모이제이션된 부분 문제들의 해를 사용합니다.
  4. (3) 과정을 가장 큰 문제에 도달할 때까지 반복합니다.

  - 작은 문제의 해로부터 큰 문제의 해를 구하는 **<mark>점화식을 설정</mark>**해야 합니다.
    > 동적 프로그래밍은 '**점화식 + 반복문**'으로 구성됩니다.

    - ex) 피보나치 수열 점화식
      <img src="/assets/images/posts_img/algorithm_dp/02.png" width="300">{: .align-center}

<br>

## 📌 장단점

  - 장점

    프로그램을 구현할 때에는 필요한 <mark>모든 가능성을 고려해서 구현</mark>하게 됩니다.  
    따라서 동적 프로그래밍을 이용하여 항상 <mark>최적</mark>의 결과를 얻을 수 있습니다.
        
  - 단점

    <mark>모든 가능성에 대한 고려가 불충분할 경우</mark> 최적의 결과를 보장할 수 없으므로 구현하기 위해서는 충분히 많은 가능성에 대한 고려를 해야 합니다.  
    다른 방법론에 비해 많은 배열을 이용하므로 <mark>메모리를 많이 요구</mark>합니다.  

💡 개인 기록용 블로그입니다. 오류가 있을 경우 언제든지 댓글 혹은 메일로 말씀해주시면 감사하겠습니다!
{: .notice}
[BACK TO TOP ↑](#){: .back-to-top }{: .align-right}