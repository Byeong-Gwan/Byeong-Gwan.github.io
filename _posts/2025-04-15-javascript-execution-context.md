---
layout: single
title:  "실행 컨텍스트"
categories: 서적
tag: [JavaScript]
---

# Javascript는 어떻게 실행되는가?

## 실행 컨텍스트(Execution Context)

"자바스크립트는 코드 위에서 아래로 순서대로 읽으며 실행하지만,
실제로는 실행 컨텍스트(Execution Context)라는 개념 안에서 동작함
브라우저(또는 Node)는 먼저 변수 선언과 함수 선언을 등록(호이스팅) 하고,
그 다음에 코드를 실제로 실행함"

- 실행 컨텍스트: 코드를 실행할 때 필요한 환경 정보를 담고 있는 공간
   예) 변수, 함수, this 등
- 호이스팅: var, function 으로 선언된 것은 코드 맨 위로 끌어올려져 먼저 등록 됨.

``` Javascript
// 변수의 호이스팅
console.log(x); // undefined
var x = 10;
console.log(x); // 10
```
|❗ 변수 선언(var x)은 위로 끌어올려져 있으나, 값 할당(x = 10)은 그 줄에서 실행됨.

``` Javascript
// 함수의 호이스팅
sayHi(); // '안녕하세요!'

function sayHi() {
  console.log('안녕하세요!');
}
```
|❗ function으로 선언한 함수는 전체가 끌어올려지기 때문에 호출 가능.
<hr>
### 결론적으로
- 실행 컨텍스트 = 실행 시 필요한 정보를 기억해두는 공간("변수, 함수, this 등은 먼저 만들어진다")
<hr>
### 미션
🔹 실행 컨텍스트는 몇 개 만들어졌을까요?
```javascript
function hello() {
  var a = '안녕';
  console.log(a);
}

hello();
```
답: 2
1. 첫 번째 실행 컨텍스트
<br>👉 전역 컨텍스트 (브라우저 실행 시 자동 생성됨)
<br>→ hello 함수의 선언이 이 안에 등록됩니다.

2. 두 번째 실행 컨텍스트
<br>👉 hello() 함수가 호출될 때 생성되는 함수 실행 컨텍스트
<br>→ 이 안에 var a = '안녕' 이 저장되고, console.log(a)가 실행됩니다.

