# 변수 호이스팅

자바스크립트 엔진(해석기)는 함수 소스 코드 전체를 실행 전에 한번 쫙 흟어보고, var 변수를 따로 기억해 놓는다.

즉, 변수를 실행하기 전에 ‘이러한 변수들이 있구나’ 하고 기억해 두기 때문에 마치 선언한 것과 같은 효과가 있다.

이것이 바로 호이스팅이다.

var 변수는 호이스팅이 있기 때문에 변수를 선언하기 전에 사용해도 오류가 생기지 않지만, 그로 인해 예상하지 못한 결과가 나올 수 있어 사용을 지양해야 한다.

> 그럼 let, const 는?
> 

- var 변수는 함수 레벨의 스코프를 갖는다.
- let, const는 블록 레벨의 스코프를 갖는다.

---

# 함수 표현식

### 익명 함수

```jsx
var add = function(a, b) {
	return a + b;
};

var sum = add(1,2);
cosnole.log(sum); // 3
```

### 즉시 실행 함수

> 정의와 동시에 실행하는 함수
> 

<aside>
💡

매우 많이 사용된다.

</aside>

즉시 실행 함수를 작성하는 4가지 방법

<img width="777" height="405" alt="image" src="https://github.com/user-attachments/assets/85300017-1d90-4443-8f2a-d547e6e7e831" />

```jsx
var result = (function() {
	return 1 + 2;
}());

console.log(result); // 30
```

### 즉시 실행 함수

```jsx
const hi = function() {
	return "hi";
}

// 화살표 함수

const hi = () => { return "안녕하세요" };

// 중괄호 생략 

const hello = () => "hello"; // 중괄호를 생략하면 return 문은 생략된 것으로 간주한다.
```

> 매개변수가 1개일 때 ⇒ 함수로 선언하기
> 

```jsx
let hi = function(user) {
	document.write(user + "님, 안녕하세요");
};

// 화살표 함수

let hi = (user) => { document.write(user + "님, 안녕하세요"); };

console.log(hi(harvey));
```

---

# 자바스크립트 객체 종류

### 1. 내장 객체(빌트인 객체)

- Date, Number, Boolean, Array, Math  등

### 2. 문서 객체 모델(DOM)

- 객체를 사용해 웹 문서를 관리하는 방식을 의미
- 이미지, 링크, 텍스트 필드 등 모두 각각 별도의 객체로 미리 만들어 두었음

### 3. 브라우저 객체 모델

- 웹 브라우저의 주소 표시줄이나 창 크기 등 웹 브라우저 정보를 다루는 객체
- Navigator, History, Locaiton, Screen 등

### 4. 사용자 정의 객체

- 그 외 사용자가 직접 정의한 객체

> 자바스크립트는 모든 것이 객체라고 봐도 무방하다.
> 

---

## 객체의 속성과 메서드

객체에서 값을 담고 있는 정보를 `속성`이라고 한다.

속성은 내장 객체에도 만들어져 있다.

그 값을 가져올 때는 객체 뒤에 마침표를 찍고 속성 이름을 적으면 된다.

```jsx
navigator.vendor
```

객체가 어떻게 동작할지를 선언해 놓은 것을 `메서드`라고 한다.

---

# 객체의 프로토타입과 인스턴스

웹 문서에 있는 요소를 프로그램에서 사용하려면 객체 형태여야 한다.

예를 들어 웹 문서에 있는 이미지를 자바스크립트에서 다룰 때는 `Image` 객체를 사용한다.

Image 객체는 모든 웹 이미지가 공통으로 가지는 `속성`과 `기능`을 모아 놓은 객체다.

> 이러한 기본 `틀`을 `프로토 타입`이라고 한다.
> 

그리고 프로토 타입을 이용해서 만들어낸 객체를 `인스턴스`라고 한다.

- 동일한 프로토 타입을 이용해 만들어낸 여러 인스턴스들은 모두 해당 프로토 타입이 제공하는 속성과 기능(함수)을 그대로 사용할 수 있다.
- 이는 마치 자바의 상속과 비슷하다.

<img width="724" height="539" alt="image" src="https://github.com/user-attachments/assets/d63ad319-4a3a-4ad2-8db1-2628acba5a1b" />

---

# 배열

- push, unshift

```jsx
nums = [1,2,3];

nums.push(4);

nums.unshift(0);

console.log(nums);

// 출력
[ 0, 1, 2, 3, 4 ]
```

- `push`는 배열 끝에, `unshift`는 배열 앞에 추가된다.

- pop, shift

```jsx
var study = ["html", "css", "js"]

study.pop();

// 출력
"js"

study.shift();
```

- `pop`은 끝에 원소를, `shift`는 앞에 원소를 제거한다.

### Array 객체 함수

- concat
- every
- filter
- forEach
- indexOf
- join

- pop
- push
- reverse
- shift
- slice
- sort
- splice
- toString
- unshift

---

# 브라우저 객체 모델

<img width="734" height="296" alt="image" src="https://github.com/user-attachments/assets/dfe7b828-4be5-45ef-b71e-0f634765fd3f" />

> 자주 사용하는 브라우저 내장 객체
> 

<img width="1026" height="435" alt="image" src="https://github.com/user-attachments/assets/af56b7dd-1483-43b7-aa55-4a4fd343b491" />

---

# DOM - 웹 문서를 다루는 문서 객체 모델

<img width="632" height="181" alt="image" src="https://github.com/user-attachments/assets/10d09568-a44f-4785-b464-33d229c6563b" />

DOM 트리는 웹 문서 요소를 다음과 같이 표현한다.

- 웹 문서의 태그는 요소 노드로 표현
- 태그가 품고 있는 텍스트는 해당 요소 노드의 자식 노드인 텍스트 노드로 표현
- 태그의 속성은 모두 해당 요소 노드의 자식 노드인 속성 노드로 표현
- 주석은 주석 노드로 표현

<img width="788" height="686" alt="image" src="https://github.com/user-attachments/assets/f6ac1817-f95d-47de-8b46-d5fd9cbd8a60" />
