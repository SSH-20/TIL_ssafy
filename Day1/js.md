# 7월 21일
# JavaScript

### JavaScript의 현재
- 기존에 JavaScript는 브라우저에서만 웹 페이지의 동적인 기능을 구현하는 데에만 사용됨.
- 이후 Node.js로 인해 브라우저에서 벗어나 서버 사이드 분야 뿐만 아니라, 클라이언트 사이드 등 다양한 프레임워크와 라이브러리들이 개발되면서 웹 개발 분야에서는 필수적인 언어로 자리 잡게 됨

## 변수
### 식별자(변수명) 작성 규칙
- 반드시 문자, 달러($) 또는 밑줄 (_)로 시작
- 대소문자를 구분
- 예약어 사용 불가 ex) for, if, function 등

* 달러와 밑줄은 Vue와 같은 변수명을 사용하여 문제가 발생하는 것을 방지하기 위함

### 식별자(변수명) Naming case
- 카멜 케이스(camelCase)
  - 변수, 객체, 함수에 사용
  - ex) Variable Name

- 파스칼 케이스(PascalCase)
  - 클래스, 생성자에 사용

- 대문자 스네이크 케이스(SNAKE_CASE)
  - 상수(constants)에 사용


### 변수 선언 키워드 3가지
1. let
2. const
3. var

### let 
- 블록 스코프(block scope)를 갖는 지역 변수를 선언
- 재할당 가능
- 재선언 불가능
- ES6에서 추가
- 자료형과 상관없이 할당 가능

```
// 재할당
let number = 10
number = 20

// 재선언 불가능
let number = 10 
let number = 20
```


### const
- 블록 스코프를 갖는 지역 변수를 선언
- 재할당 불가능
- 재선언 불가능
- ES6에서 추가

### 블록 스코프 (block scope)
- if, for, 함수 등의 '중괄호 ({}) 내부'를 가리킴
- 블록 스코프를 가지는 변수는 블록 바깥에서 접근 불가능

### 어떤 변수 선언 키워드를 사용해야 하는가?
- 기본적으론 const 사용을 권장
- 재할당이 필요하면 그때 let으로 변경해 사용

## 데이터 타입
- 원시 자료형 (Primitive type)
  - 변수에 값이 직접 저장되는 자료형 (불변, 값이 복사)
  - number, String, Boolean, Null, undefined

- 참조 자료형 (Reference type)
  - 객체의 주소가 저장되는 자료형 (가변, 주소가 복사)
  - Object, Array, Function

### Template literals
- 내장된 표현식을 허용하는 문자열 작성 방식
- Backtick (``)을 이용하여, 여러 줄에 걸쳐 문자열을 정의할 수 있고 JavaScript의 변수를 문자열 안에 바로 연결할 수 있음
- 표현식은 '$'와 중괄호 (#{expression})로 표기
- ES6+ 부터 지원

### null과 undefined
- null
  - 변수의 값이 없음을 의도적으로 표현할 때 사용
  - typeof null 을 실행해보면 object로 나온다.

- undefined
  - 변수 선언 이후 직접 값을 할당하지 않으면 자동 할당
  - typeof undefined 를 실행해보면 undefined가 나온다.

* null이 원시 자료형 임에도 불구하고 object로 출력되는 이유는 JavaScrpit 설계 당시의 버그를 해결하지 않은 것
* 해결하지 못하는 이유는 이미 null 타입에 의존성을 띄고 있는 수 많은 프로그램들이 망가질 수 있기 때문 (하위 호환 유지)

### 동등 연산자 (==)
- '암묵적 타입 변환'을 통해 타입을 일치시킨 후 같은 값인지 비교

### 일치 연산자 (===)
- 두 연산자의 값과 타입이 모두 같은 경우 true를 반환

### 논리 연산자
- and 연산 : &&
- or 연산 : ||
- not 연산 : !

### 삼항 연산자
- condition ? expression1 : expression2
  - condition : 평가할 조건 (true or false)
  - expression1 : 조건이 True일 경우 반환
  - expression2 : 조건이 false일 경우 반환

## 반복문
### 반복문 종류
- while
  - 조건문이 참이면 문장을 계속 수행
- for
  - 특정한 조건이 거짓으로 판별될 때까지 반복
- for...in
  - 객체의 열거 가능한 속성에 대해 반복 (객체를 순회)
- for...of
  - 반복 가능한 객체(배열, 문자열 등)에 대해 반복 (배열을 순회)

### 반복문 사용 시 const 사용 여부
- for 문
```
for (let i=0; i<arr.length; i++) {} 의 경우에는 최초 정의한 i를 "재할당" 하면서 사용하기 떄문에 const를 사용하면 에러 발생
```

- for...in , for...of
  - 재할당이 아니라, 매 반복마다 다른 속성 이름이 변수에 지정되는 것이므로 const를 사용해도 에러가 발생하지 않음
  - 단, const 특징에 따라 블록 내부에서 변수를 수정할 수 없음

# DOM
웹 페이지 (Document)를 구조화된 객체로 제공하여 프로그래밍 언어가 페이지 구조에 접근할 수 있는 방법을 제공
> 문서 구조, 스타일, 내용 등을 변경할 수 있도록 함

## JavaScript 실행 환경 종류
1. HTML script 태그
2. js 확장자 파일
3. 브라우저 Console

### DOM API
- 다른 프로그래밍 언어가 웹 페이지에 접근 및 조작 할 수 있도록 페이지 요소들을 객체 형태로 제공하며 이에 따른 메서드 또한 제공

### DOM 특징
- DOM에서 모든 요소, 속성, 텍스트는 하나의 객체
- 모두 doucument 객체의 하위 객체로 구성 됨

### DOM tree
- 브라우저는 HTML 문서를 해석하여 DOM tree라는 객체 트리로 구조화
> 객체 간 상속 구조가 존재

## DOM의 핵심
문서의 요소들을 객체로 제공하여 다른 프로그래밍 언어에서 접근하고 조작할 수 있는 방법을 제공하는 API

## Document 객체
- 웹페이지 객체
- DOM Tree의 진입점
- 페이지를 구성하는 모든 객체 요소를 포함

## Dom 조작 시 기억해야 할 것
웹 페이지를 동적으로 만들기 == 웹 페이지를 조작하기

> 조작순서
1. 조작 하고자 하는 요소를 선택 (또는 탐색)
2. 선택된 요소의 콘텐츠 또는 속성을 조작

## 선택 메서드 
- document.querySelector()
  - 요소 한 개 선택

- document.querySelectorAll()
  - 요소 여러 개 선택

### DOM 조작
1. 속성(attribute) 조작
  - 클래스 속성 조작
  - 일반 속성 조작
2. HTML 콘텐츠 조작
3. DOM 요소 조작
4. 스타일 조작

### 클래스 속성 조작
- 'ClassList' property
  - 요소의 클래스 목록을 DOMTokenList(유사 배열) 형태로 변환

1. classList 메서드
  - element.classList.add()
    -지정한 클래스 값을 추가
  
  - elemen.classtList.remove()
    - 지정한 클래스 값을 제거

  - element.classList.toggle()
    - 클라스가 존재한다면 제거하고 false를 반환
    - 존재하지 않으면 클래스 추가하고 true 반환

2. 일반 속성 조작 메서드
  - element.getAttribute()
    - 해당 요소에 지정된 값을 반환
  
  - element.setAttribute(name, value)
    - 지정된 요소의 속성 값을 설정
    - 속성이 이미 있으면 기존 값을 갱신

  - element.removeAttirbute()
    - 요소에서 지정된 이름을 가진 속성 제거

## Node
- DOM의 기본 구성 단위
- DOM 트리의 각 부분은 Node라는 객체로 표현됨
  - Document Node
  - Element Node
  - Text Node
  - Attribute Node

# 함수

## Function
참조 자료형에 속하며 모든 함수는 Function object

## 함수 구조
```
function name(param) {
  statement
  return value
}
```
- function 키워드
- 함수의 이름
- 함수의 매개변수
- 함수의 body를 구성하는 statement
* return 값이 없다면 undefined를 반환

## 함수 정의 2가지 방법
1. 선언식
```
function funcName() {
  statements
}
```
2. 표현식 (평가에 한계의 의해 값을 반환하는 식)
```
const funcName = function () {
  statements
}
```

### 함수 표현식 특징
- 함수 이름이 없는 '익명 함수'를 사용할 수 있음
- 선언식과 달리 표현식으로 정의한 함수는 호이스팅이 되지 않으므로 함수를 정의하기 전에 먼저 사용할 수 없음

## 매개변수
### 매개변수 정의 방법
1. 기본 함수 매개변수
- 전달하는 인자가 없거나 undefined가 전달될 경우 이름 붙은 매개변수를 기본값을 ㅗ초기화

2. 나머지 매개변수
- 임의의 수의 인자를 '배열'로 허용하여 가변 인자를 나타내느 방법

* 작성 규칙
  - 함수 정의 시 나머지 매개변수는 하나만 작성할 수 있음
  - 나머지 매개변수는 함수 정의에서 매개변수 마지막에 위치해야 함.
```
const myFunc = function (param1, param2, ... restPrams) {
  return [param1, param2, restPrams]
}
```

## 화살표 함수
- Arrow Functions 으로 작성하면 동작 방식이 바뀐다.
### 화살표 함수 표현식
```
const arrow = function (name) {
  return 'hello, ${name}'
}
```
->
```
const arrow = name => 'hello, ${name}'
```

### Arrow function 작성 과정
1. function 키워드 제거 후 매개변수와 중괄호 사이에 화살표(=>) 작성

2. 함수의 매개변수가 하나뿐이라면, 매개변수의 '()' 제거 가능 (단 생략하지 않는 것을 권장)

3. 함수 본문의 표현식이 한 줄이라면, '{}' 와 'return' 제거 가능

# 참고
## 세미콜론 (semicolon)
- 자바스크립트는 문장 마지막 세미콜론 (;)을 선택적으로 사용 가능
- 세미콜론이 없으면 ASI에 의해 자동으로 세미콜론이 삽입됨
- javaScript를 만든 Brendan Eich 또한 세미콜론 작성을 반대

# 이벤트
무언가 일어났다는 신호, 사건

## 이벤트 객체
- DOM에서 이벤트가 발생했을 때 생성되는 객체
- 이벤트 종류
  - mouse, input, keyboard, touch 등등

## Event handler
이벤트가 발생했을 때 실행되는 함수
> 사용자의 행동에 어떻게 반응할지를 javaScript 코드로 표현한 것

### .addEventListener()
특정 이벤트를 DOM 요소가 수신할 때마다 콜백 함수를 호출
```
EventTarget.addEventListener(type, handler)
```
" 대상에 특정 Event가 발생하면, 지정한 이벤트를 받아 할 일을 등록한다."

- type
  - 수신할 이벤트 이름
  - 문자열로 작성 (ex. 'click')

- handler
  - 발생한 이벤트 객체를 수신하는 콜백 함수
  - 콜백 함수는 발생한 event object를 유일한 매개변수로 받음


## 버블링
### 버블링 개요
- form > div > p 형태의 중첩된 구조에서 각각 이벤트 핸들러가 있을 때 만약 <p> 요소를 클릭하면 어떻게 될까?

- <p> 요소만 클릭했는데도 불구하고 모든 핸들러가 동작
> 와 p를 클릭했는데 div와 form에 할당된 핸들러까지 동작할까?

* 그래서 어떠한 객체가 호출되었는지 어떻게 아는가?
* 그래서 currentTarget이 존재하는 것이다.
* event.target.id 는 클릭된 객체를 반환, event.currentTarget.id 은 handler를 호출한 객체를 반환한다.
