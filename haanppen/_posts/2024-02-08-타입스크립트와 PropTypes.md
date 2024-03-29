---
layout: post
title: '타입스크립트와 PropTypes'
date: 2024-02-08 00:01:24 +0900
categories: haanppen
---

# 타입스크립트와 PropTypes

## 요약

리액트 프로젝트의 타입 검사를 하는 방법을 결정하기 위해 조사 한 글

## 서론

1. 타입스크립트
2. PropTypes
   두가지 방식으로 타입을 체크하는데 두 방식의 장던짐이 있다.

## 본론

-   타입스크립트

1. 타입스크립트가 자바스크립트로 변환되는 컴파일 시점에 타입 체크 오류를 발생시킨다
2. PropTypes보다 더 성능이 뛰어난 자동화 도구가 존재하고, 많은 타입을 지원한다

-   PropTypes

1. 런타임 시점에서 타입 체크 오류를 발생 시킨다 (많은 사람들이 사용하는 라이브러리를 제작시 사용 권장)
2. 런타임 시점에서 오류가 발생하기 때문에, API 데이터들도 타입 체크를 할 수 있다
3. 부족한 자동화 도구, 적은 타입이 단점이다

## 결론

PropTypes를 사용하기로 했다. 이유는 런타임 데이터 체크도 해보고 싶고, 아직 한번도 써보지 못한 대중적인 툴이기 때문이다.
