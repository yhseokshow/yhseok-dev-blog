---
title: "Javascript Object Clone"
date: 2021-07-25T10:03:22+09:00
description: "How to clone javascript object"
featured: true
tags: ["clone"]
categories: ["javascript"]
---

## Javascript Object Clone

### 참고 링크
* https://hyunseob.github.io/2016/02/08/copy-object-in-javascript/
* [자바스크립트 객체 복사하기 - ddalpange velog](https://velog.io/@ddalpange/%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EA%B0%9D%EC%B2%B4-%EB%B3%B5%EC%82%AC%ED%95%98%EA%B8%B0)
* [Javascript - deep copy가 필요할 때 무얼 사용해야 할까?](http://hochulshin.com/javascript-best-deepcopy/)
* [medium - JavaScript Deep copy for array and object](https://medium.com/@gamshan001/javascript-deep-copy-for-array-and-object-97e3d4bc401a)

### 얕은 복사 (hallow copy)
* [ES6 자바스크립트 내장]
  ```javascript
  let copy = Object.assign({}, object);
  let copy = Object.clone(object);
  ```
* [ES6 spread 문법]
  ```javascript
  let copy = {...object};
  ```
* [lodash or underscore]
  ```javascript
  let copy = _.clone(object);
  ```
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
  ```javascript
  let copy = _.cloneDeep(object);
  ```
* [JSON 문자열 변환 후 다시 JSON parsing]
  ```javascript
  JSON.parse(JSON.stringify(object));
  ```
  * 단, object 내에 function 또는 Date type이 있으면 그것에 대해서는 동작 안함.
  * 가장 느릴 것으로 판단됨.
* [자바스크립트 직접 구현]
  ```javascript
  function deepClone(obj) {
    if (obj === null || typeof obj !== "object") return obj

    var copy = obj.constructor()
    for (var attr in obj) {
      if (obj.hasOwnProperty(attr)) {
        copy[attr] = deepClone(obj[attr])
      }
    }
    return copy
  }

  let copy = deepClone(object)
  ```

* [jQuery or Angular 함수 이용]
  * angular.copy, $.extend
