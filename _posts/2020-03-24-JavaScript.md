---
layout: post
title:  "[유지보수 가능한 코드 작성하기]<br/> 전역 변수의 최소화"
date:   2020-03-24 11:50
categories: javascript
permalink: /archivers/20200324-
--- 

## 개요
**전역 변수**란?  
**어떤 변수 영역 내에서도 접근할 수 있는 변수**를 의미한다.  

전역 변수는 애플리케이션이나 웹페이지 내   
모든 코드 사이에서 공유된다는 특징을 가진다.  

따라서, 목적이 다른 전역 변수를 동일한 이름으로 사용할 경우  
서로 덮어쓰게 되는 문제가 발생한다.

## 예제
예제를 살펴보자.  
   
```javascript
function foo(x, y) {
    // anti-pattern : implied globals
    result = x + y;
    return result;
}
```

이 코드는 result라는 변수를 선언하지 않고 사용하고 있다.  
이때, result는 전역 네임스페이스에 남게되어  
이후 동일한 이름의 변수를 사용할 경우 문제가 발생할 수 있다.

위 코드를 아래와 같이 수정해보자.

```javascript
function foo(x, y) {
    // use var keyword
    var result = x + y;
    return result;
}
```