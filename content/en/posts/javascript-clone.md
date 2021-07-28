---
title: "Javascript Object Clone"
date: 2021-07-25T10:03:22+09:00
description: "How to clone javascript object"
featured: true
tags: ["clone"]
categories: ["javascript"]
---

## Javascript Object Clone

```javascript
let objA = { a: 5, b: 'title' }
let objB = obj.clone()
```
### 참고 링크
* https://hyunseob.github.io/2016/02/08/copy-object-in-javascript/
https://velog.io/@ddalpange/%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-
%EA%B0%9D%EC%B2%B4-%EB%B3%B5%EC%82%AC%ED%95%98%EA%B8%B0
* http://hochulshin.com/javascript-best-deepcopy/
* https://medium.com/@gamshan001/javascript-deep-copy-for-array-and-object-97e3d4bc401a

### 얕은 복사 (hallow copy)
* [ES6 자바스크립트 내장]
  * let copy = Object.assign({}, object);
  * let copy = Object.clone(object);
* [ES6 spread 문법]
  * let copy = {...object};
* [lodash or underscore]
  * let copy = _.clone(object);
* [자바스크립트 직접 구현]
  ```javascript
  function clone(obj) {
    if (obj === null || typeof obj !== "object") return obj
    
    var copy = obj.constructor()
    for (var attr in obj) {
      if (obj.hasOwnProperty(attr)) {
        copy[attr] = obj[attr]
      }
    }

    return copy
  }

  let copy = clone(object)
  ```
* [jQuery or Angular 함수 이용]
  * angular.copy, $.extend

### 깊은복사 (deep copy)
* [lodash or underscore]
  * let copy = _.cloneDeep(object);
* [JSON 문자열 변환 후 다시 JSON parsing]
  * JSON.parse(JSON.stringify(object));
  * 단, object 내에 function 또는 Date type이 있으면 그것에 대해서는 동작 안함.
  * 가장 느릴 것으로 판단됨.
* [자바스크립트 직접 구현]
  ```javascript
  function deepClone(obj) {
    if (obj === null || typeof obj !== "object") return obj

    var copy = obj.constructor()
    for (var attr in obj) {
      if (obj.hasOwnProperty(attr)) {
        copy[attr] = clone(obj[attr])
      }
    }
    return copy
  }

  let copy = deepClone(object)
  ```

* [jQuery or Angular 함수 이용]
  * angular.copy, $.extend
