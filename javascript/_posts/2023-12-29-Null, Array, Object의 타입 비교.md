---
layout: post
title:  "Null, Array, Object의 타입 비교"
date:   2023-12-29 17:13:24 +0900
categories: javascript
---
# Null, Array, Object의 타입 비교

1. typeof 사용
```javascript
console.log(typeof 'Hello' === 'string')
console.log(typeof 123 === 'number')
console.log(typeof false === 'boolean')
console.log(typeof undefined === 'undefined')
console.log(typeof function () {} === 'function')
console.log(typeof 'null' === 'object')
console.log(typeof [] === 'object')
console.log(typeof {} === 'object')
```

2. .contructor 사용
배열과 객체를 비교
```javascript
console.log([].constructor === Array)
console.log({}.constructor === Object)
```

3. null까지 비교하기 위해
```javascript
function checkType(data) {
  return Object.prototype.toString.call(data).slice(8, -1)
}
이 함수면 모든지 비교 가능.
```