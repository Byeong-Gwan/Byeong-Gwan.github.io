---
layout: single
title:  "08장 제어문"
categories: 서적
tag: [JavaScript]
---

### 📌 **제어문의 개요**

- 자바스크립트 코드는 **위에서 아래로 순차적으로 실행**됨이 기본.
    
- **제어문(control flow statements)**은
    
    - 조건에 따라 코드를 실행하거나
        
    - 특정 코드를 반복 실행하는 데 사용됨.
        
- 대표적인 제어문 종류: `if`, `switch`, `for`, `while`, `break`, `continue`
    

#### 🔸 제어문이 가진 문제

- 코드의 **실행 순서**가 바뀌므로 **직관적인 흐름을 해칠 수 있음**.
    
- 너무 많은 제어문은 가독성을 떨어뜨리고 **유지보수를 어렵게** 만듦.
    

#### 🔸 해결 방식

- **함수형 프로그래밍 방식** 도입  
    → `forEach`, `map`, `filter`, `reduce` 등의 **고차 함수**를 활용하여 흐름을 명확하게 유지.
    

---

### ✅ 8-1. 블록문 (`{ }`)

- **하나 이상의 문(statement)**을 **하나의 실행 단위로 묶는 문법**.
    
- 주로 `if`, `for`, `function` 등의 본문을 정의할 때 사용.
    
- 자체 종결성(문법적으로 닫힘)을 가지므로 **세미콜론 `;`을 붙이지 않음**.
    
``` javascript
{   
	const x = 1;   
	console.log(x); 
}
```

---

### ✅ 8-2. 조건문

#### 🔹 `if...else`

- 조건이 `true`일 때 블록 실행
    
``` javascript
if (age >= 18) {
	console.log('성인'); 
} else {
	console.log('미성년자'); 
}
```

#### 🔹 `switch`

- 여러 조건 분기 필요할 때 사용 (특히 **값 매칭**에 유리)
    
``` javascript
switch (fruit) {   
	case 'apple':     
		console.log('사과');     
		break;   
	case 'banana':     
		console.log('바나나');     
		break;   
	default:     
		console.log('기타'); 
}
```

---

### ✅ 8-3. 반복문

#### 🔹 `for`

일반적인 반복문

#### 🔹 `forEach`

배열 순회용 (return/break 사용 불가)

#### 🔹 `for...in`

객체의 **key(속성명)** 반복

#### 🔹 `for...of`

**배열/이터러블의 값** 순회

---

### ✅ 8-4. `break` 문

- 반복문 또는 `switch` 문에서 **즉시 탈출**할 때 사용
    
``` javascript
for (let i = 0; i < 5; i++) {   
	if (i === 2) break;   
	console.log(i); 
}
```

---

### ✅ 8-5. `continue` 문

- 현재 반복만 건너뛰고 **다음 반복으로 이동**.
    
``` javascript
for (let i = 0; i < 5; i++) {   
	if (i === 2) continue;   
	console.log(i); // 2 제외 출력 
}
```

---