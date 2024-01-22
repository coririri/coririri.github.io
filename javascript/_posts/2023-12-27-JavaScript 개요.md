---
layout: post
title:  "JavaScript 개요"
date:   2023-12-27 22:09:24 +0900
categories: javascript
---
# JavaScript 개요
ECMAScript는 JavaScript의 표준형이다.  
ES는 2015년을 기준으로 매년 새로운 기능이 추가 되는 중  
- 자바스크립트는 컴파일 없이 실행 가능한 언어지만, V8엔진이 JIT(Just-In-Time) 컴파일러를 도입해 필요한 부분들만 컴파일해서 성능을 개선 해 사용 한다.
- 자료형은 존재하지만, 변수에 저장되는 값의 타입은 언제든지 바꿀 수 있는 동적 타입 언어이다.

## javascript만의 강점 3가지
1. HTML/CSS와 완전히 통합할 수 있음
2. 간단한 일은 간단하게 처리할 수 있게 해줌
3. 모든 주요 브라우저에서 지원하고, 기본 언어로 사용됨

## javascript로 transfile되는 언어들
1. CoffeeScript (짧은 문법을 도입하여 명료하고 이해하기 쉬운 코드를 작성할 수 있습니다. Ruby 개발자들이 좋아합니다.)
2. TypeScript ('자료형의 명시화(strict data typing)'에 집중해 만든 언어입니다. Microsoft가 개발)
3. Flow 자료형을 강제하는데, TypeScript와는 다른 방식을 사용합니다. Facebook이 개발
4. Dart 모바일 앱과 같이 브라우저가 아닌 환경에서 동작하는 고유의 엔진을 가진 독자적 언어입니다. Google이 개발

## 표기법
- dash-case
사용처: HTML, CSS  
ex the-quick-brown-for  

- snake_case
사용처: HTML, CSS  
ex the_quick_brown_for

- camelCase
사용처: JS(거의 대부분)  
ex theQuickBrownFor

- PascalCase
사용처: JS(new 생성자 함수 이름 )  
ex. TheQuickBrownFor  

## 데이터 종류

- String
' ', " ", ``, 이렇게 3가지로 묶어서 표한 가능하고,  
(백틱을 활용하면 문자열 내부에 변수를 넣을 수 있다.)  
js는 문자열 비교 시 사전 순이 아닌, 유니코드 순으로 진행됩니다.(대문자 < 소문자)
- Number
정수 및 부동소수점 숫자를 나타냅니다.  
NAN는 타입자체는 Number인데, 숫자가 아닌 다른 값이다.  
Infinity, -Infinity, NaN같은 특수 문자 값도 포함한다.  
Infinity는 어떤 숫자를 0으로 나누면 확인 가능하다.
ex 123, 1.57
- Boolean
true, false 두 가지 값밖에 없는 논리 데이터
- Undefined
값이 할당되지 않은 상태를 나타냅니다.  
local empty;
- Null
어떤 값이 (의도적)!!으로 비어있음을 의미합니다.  
다른 언어에서는 존재하지 않는 객체에 대한 참조를 나타내지만, js에서는 알수 없거나, 의도적으로 빈 값
local empty = null;
- Object
객체 데이터 (여러 데이터를 Key:Value 형태로 저장합니다)  
```JavaScript
let user = {
  name: 'Heropy',
  age: 85,
}
```
- Array
배열 데이터 (여러 데이터를 순차적으로 저장합니다.)
```JavaScript
let fruits = ['Apples', 'Bananan', 'Cherry']
```

## 변수 선언
var(사용 안함 권장), let, const
- let
재 할당이 가능!
- const
재 할당이 불 가능!

## 예약어
특별한 의미가 있어, 변수명이나 함수명으로 사용할 수 없는 이름  
this, if, for, break ...

## DOM API
Documment Object Model (div, span, input ...)
Script를 html파일에서 불러오면 순차적으로 읽히기 때문에, body테그 끝에 넣거나 defer를 넣어줘야 한다.
1. quertSelector()
HTML 요소 1개 검색/찾기
2. addEventListener(event, function)
실행할 함수를 이벤트 헨들러라고 부른다.
3. 요소.classList
요소가 가지고 있는 classList 반환
4. 요소.classList.add("active)
클래스 추가 add  
클래스 검색 contains
클래스 삭제 remove
5. querySelectorAll()
HTML 요소 모두 검색/찾기
유사 배열 반환

## 메소드 체이닝
```javascript
const a = 'Hello';
const b = a.split('').reverse().join('')
```