---
title: "Javascript Object Clone"
date: 2021-07-25T10:03:22+09:00
description: "How to clone javascript object"
featured: true
tags: ["clone"]
categories: ["javascript"]
---

### 참고 링크
* https://hyunseob.github.io/2016/02/08/copy-object-in-javascript/
* [자바스크립트 객체 복사하기 - ddalpange velog](https://velog.io/@ddalpange/%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EA%B0%9D%EC%B2%B4-%EB%B3%B5%EC%82%AC%ED%95%98%EA%B8%B0)
* [Javascript - deep copy가 필요할 때 무얼 사용해야 할까?](http://hochulshin.com/javascript-best-deepcopy/)
* [medium - JavaScript Deep copy for array and object](https://medium.com/@gamshan001/javascript-deep-copy-for-array-and-object-97e3d4bc401a)
* [JavaScript로 Deep Copy 하는 여러 방법](https://chaewonkong.github.io/posts/js-deep-copy.html)

### 얕은 복사 (shallow copy)
* [ES6 자바스크립트 내장]
  ```javascript
  let copy = Object.assign({}, object);
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
* 기타
  * jQuery의 $.extend 이용
  * Angular의 angular.copy 이용

### 깊은복사 (deep copy)
* [lodash or underscore]
  ```javascript
  let copy = _.cloneDeep(object);
  ```
* [JSON 문자열 변환 후 다시 JSON parsing]
  ```javascript
  JSON.parse(JSON.stringify(object));
  ```
  * 단, object 내에 function, Date 객체, 정규표현식 등등 type의 데이터는 복사 안됨.
  * 가장 느림.
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

* 기타
  * jQuery의 $.extend 이용
  * Angular의 angular.copy 이용
