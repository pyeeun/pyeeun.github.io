---
layout: post
title:  "[JS] 전역 변수의 최소화"
date:   2020-03-24 11:50
categories: javascript
permalink: /archivers/20200324-JS-Variable
summary: 유지보수 하기 편리한 코드 작성하기
tag: javascript hoisting variable design-pattern html
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
이때 result는 전역 네임스페이스에 남게되어  
이후 동일한 이름의 변수를 사용할 경우 문제가 발생할 수 있다.

위 코드를 아래와 같이 수정해보자.  

```javascript
function foo(x, y) {
    // use var keyword
    var result = x + y;
    return result;
}
```

var 키워드를 사용하여 지역변수 result를 선언하였다.  

이와 같이 함수 내에서만 사용하는 지역 변수로 선언하여  
전역 변수를 최소화 시키자.

추가로...  
var 키워드에 대해 공부하다 보니  
호이스팅이라는 개념에 대해 접하게 되었다.  

다음에는 호이스팅에 관해 포스팅을 해보자!