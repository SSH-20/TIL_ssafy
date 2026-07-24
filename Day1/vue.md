# 7월 23일 목요일
# Frontend Development
웹사이트와 웹 애플리케이션의 사용자 인터페이스(UI) 사용자 경험(UX)을 만들고 디자인하는 것
> HTML, CSS, JavaScript 등을 활용하여 사용자가 직접 상호작용하는 부분을 개발

* Client-side Frameworks
  - 클라이언트 측에서 UI와 상호작용을 개발하기 위해 사용되는 JS 기반 프레임 워크 : Vue, React(라이브러리), A ?

### Client-side frameowrks가 필요한 이유 
"웹에서 하는 일이 많아졌다."  
1. 단순히 무언가를 읽는 곳 -> 무언가를 하는 곳
  - 음악 스트리밍, 영화시청, 영상 채팅 등등..

2. 다루는 데이터가 많아졌다.
  - SNS만 해도 친구가 이름을 변경한다면, 친구 목록, 타임라인, 스토리 등 친구 이름이 출력되는 모든 곳이 변경되어야 함.

## Single Page Application (SPA)
단일 페이지로 구성된 애플리케이션

- 하나의 HTML 파일로 시작하여, 사용자가 상호작용할 때마다 페이지 전체를 새로 로드하지 않고 화면의 필요한 부분만 동적으로 갱신
- 대부분 JS 프레임워크를 사용하여 클라이언트 측에서 UI 렌더링을 관리
- CSR 방식 사용 (Client-Side Rendering)

### CSR 장점
1. 빠른 페이지 전환
  - 페이지가 처음 로드된 후에는 필요한 데이터만 가져오면 되고 JS는 전체 페이지를 새로 고칠 필요 없이 페이지 일부를 다시 렌더링 할 수 있기 떄문
  - 서버로 전송되는 데이터 양 최소화

2. 사용자 경험
  - 새로고침이 발생하지 않아 빨라짐

3. Frontend 와 Backend의 명확한 분리
  - 대규모 애플리케이션을 더 쉽게 개발하고 유지 관리 가능

### CSR 단점
1. 느린 초기 로드 속도
  - 전체 페이지를 보기 전에 약간의 지연을 느낄 수 있음
  - JS가 다운로드, 구문 분석 및 실행될 때까지 페이지가 완전히 렌더링 되지 않기 때문

2. SEO(검색 엔진 최적화) 문제
  - 페이지를 나중에 그려 나가는 것이기 때문에 잘 노출되지 않을 수 있음.
  - 검색엔진 입장에서 HTML을 읽어서 분석해야 하는데 아직 콘텐츠가 모두 존재하지 않기 때문

### MPA
  - 여러 개의 HTML 파일이 서버로부터 각각 로드
  - 사용자가 다른 페이지로 이동할 때마다 새로운 HTML 파일이 로드됨

### SSR
  - 서버에서 화면을 렌더링 하는 방식
  - 모든 데이터가 담긴 HTML을 서버에서 완성 후 클라이언트에게 전달

# Vue
사용자 인터페이스를 구축하기 위한 JS 프레임워크

### Vue의 2가지 핵심 기능
1. 선언적 렌더링 (Declarative Rendering)
  - 표준 HTML을 확장하는 "템플릿 구문"을 사용하여 JS 상태(데이터)를 기반으로 화면에 출력될 HTML을 선언적으로 작성

2. 반응성 (Reactivity)
  - JS 상태(데이터) 변경을 추적하고, 변경사항이 발생하면 자동으로 DOM을 업데이트

* message에 부여된 ref(반응형 객체)의 value 속성 값을 수정하여 const로 선언된 변수의 값을 바꿀 수 있다?

### 템플릿 렌더링
- 반환된 객체의 속성은 템플리셍서 사용할 수 있음
- Mustache syntax(콧수염 구문)를 사용하여 메시지 값을 기반으로 동적 텍스트를 렌더링
- 콘텐츠는 식별자나 경로에만 국한되지 않으며 유효한 JS 표현식을 사용할 수 있음

### ref 객체가 필요한 이유
- 일반적인 변수가 아닌 객체 데이터 타입으로 사용하는 이유는?

# Single-file Components
컴포넌트의 템플릿, 로직 및 스타일을 하나의 파일로 묶어낸 특수한 파일 형식 (*.vue 파일)

## Component
재사용 가능한 블록

### Component 특징
- UI를 독립적이고 재사용 가능한 일부분으로 분할하고 각 부분을 개별적으로 다룰 수 있음.

### Node Package Manager (NPM)
Node.js의 기본 패키지 관리자

### Module 
프로그램을 구성하는 독립적인 코드 블록 (*.js 파일)

### Module의 필요성
- 개발하는 애플리케이션의 크기가 커지고 복잡해지면서 파일 하나에 모든 기능을 담기 어려워 짐.

### Module의 한계
- 애플리케이션이 점점 더 발전함에 따라 처리해야 하는 JS 모듈의 개수도 극적으로 증가
- 복잡하고 깊은 모듈 간 의존성 문제를 해결하기 위한 도구가 필요
  - Bundler

### Bundler
여러 모듈과 파일을 하나(혹은 여러 개)의 번들로 묶어 최적화하여 애플리케이션에서 사용할수 있게 만들어주는 도구

### Bundler의 역할
- 의존성 관리, 코드 최적화, 리소스 관리 등

## Vite
프론트 엔드 개발 도구
- 빠른 개발 환경을 위한 빌드 도구와 개발 서버를 제공

### Build
- 프로젝트의 소스 코드를 최적화하고 번들링하여 배포할 수 있는 형식으로 변환하는 과정
- 개발 중에 사용되는 여러 소스 파일 및 리소스 (JS, CSS, 이미지 등)를 최적화된 형태로 조합하여 최종 소프트웨어 제품을 생성하는 것

# 7월 24일
# VUE Syntax
## Template Syntax
DOM을 기본 구성 요소 인스턴스의 데이터 선언적으로 바인딩할 수 있는 HTML 기반 템플릿 구문을 사용

### Template Syntax 종류
1. Text Interpolation
- 데이터 바인딩의 가장 기본적인 형태
- 이중 중괄호 구문(콧수염 구문)을 사용
- 콧수염 구문은 해당 구성 요소 인스턴스의 msg 속성 값으로 대체
- msg 속성이 별경될 때마다 업데이트 됨

* text 값을 출력하고 싶으면 {{}}을 사용한다.
<!--
html이 원래 갖고 있던 속성이 아닌 
vue가 제공하는 특별한 속성 -> 이 경우, 화면에 렌더링 되기 위한 과정을 거칠때
속성에 할당된 값이 어떤 역할을 하는지 "계산" 해야만 한다.
-->

<!--
  v-html을 절대 사용해서는 안되는 상황이 있다.
  -> 사용자에게 input을 받아 값이 변할 때  
-->

<!--
  const dynamicId = ref('my-id')
 <div v-bind:id="dynamicId"></div> 
  html에 기본적으로 제공되는 각종 속성들에 내가 가진 state를 반영하고자 한다면?
  그냥 class="msg" <- 이렇게 작성하면 진짜 'msg' 문자열이 클래스로 등록되버림
  근데, 내가 바란건 msg 라는 변수에 할당된 'hello' 라는 문자열이 클래스로 등록되기를 바람
    이걸 통해서 어등ㄹ 수 있는 기대 효과는
      msg 변수에 할당된 값이 바뀌면 연결된 class의 이름도 바뀌길 기대한다.
-->
2. Raw HTML
- 콧수염 구문은 데이터를 일반 텍스트로 해석하기 때문에 실제 HTML을 출력하려면 v-html을 사용해야 함

3. Attrbute Bindings
- 콧수염 구문은 HTML 속성 내에서 사용할 수 없기 때문에 v-bind를 사용
- HTML의 id 속성 값을 vue의 dynamicId 속성과 동기화 되도록 함
- 바인딩 값이 null이나 undefined인 경우 렌더링 요소에서 제거 됨

4. JavaScript Expressions
- Vue는 모든 데이터 바인딩 내에서 JS 표현식의 모든 기능을 지원
- Vue 템플릿에서 JS 표현식을 사용할 수 있는 위치

## Directive
'v-' 접두사가 있는 특수 속성

## directive
- dirctive의 속성 값은 단일 JS 표현식이어야 함 (v-for, v-on 제외)
- 표현식 값이 변경될 때 DOM에 반응적으로 업데이트를 적용

## Directive 전체 구문
- (v-on):(submit)(.prevent)=("onSubmit")
- name, argument, modifiers, value

## v-bind
하나 이상의 속성 또는 컴포넌트 데이터를 표현식에 동적으로 바인딩

- 예를 들어 img 같은 태그에 bind를 하게 된다면 src, class, id, title 등을 붙이게 될 텐데 이 모든 html 속성을 v-bind 쓰기에는 귀찮다. 따라서 : 만 써도 사용이 되도록 숏컷을 제공한다.

## 사용처
1. Attribute Bindings
2. Class and Style Bindings

## Class and Style Bindings
하나의 오브젝트에 여러개의 class를 부여할 수 있다. 이럴때는 바인드를 어떻게 해야 하는가?

# v-on
DOM 요소에 이벤트 리스너를 연결 및 수신

## v-on 구성
- v-on:event="handler"
  - handler 종류
    1. inline handler : 이벤트가 트리거 될 떄 실행 될 JS 코드
    2. Method handler : 컴포넌트에 정의된 메서드 이름

- v-on Shorthand (약어)
- @event="handler"

* 오해하지 말 것. event 객체를 인자로 넘기고 싶다고
* 매개변수명이 반드시 event일 필요는 당연히 없다.
* 매개변수는 매개변수 일 뿐. 변수명은 내가 마음대로 정할 수 있다.

* 내가 이벤트 핸들러로 매개변수를 변수와 이벤트 객체를 받기로 했는데 이벤트 객체는 어떻게 보내야 하나?
  * ex. @click="warning('경고입니다.', $event)">Waning</button>

* v-bind 는 내 상태를 속성에 넘겨주는 단방향 바인딩이다. 양방향 바인딩은 input으로 state에 반영할 수 있고 state를 value에 반영할 수 있다.

## Form Input Bindings
- form을 처리할 떄 사용자가 inpu에 입력하는 값을 실시간으로 JS 상태에 동기화해야 하는 경우(양방향 바인딩)

## v-model
- 사용자 입력 데이터와 반응형 변수를 실시간 동기화

* IME가 필요한 언어(한국어, 중국어, 일본어 등)의 경우 v-model이 제대로 업데이트 되지 않음
* 한글의 경우 여러 글자를 합쳐 하나의 글자가 완성되기 때문

# Conditional Rendering
## v-if
- 표현식 값의 true/false를 기반으로 요소를 조건부 렌더링

- 'v-else' directive를 사용하여 v-if에 대한 else 블록을 나타낼 수 있음
```
<p v-if="isSeen">true일때 보여요</p>
<p v-else>false일때 보여요</p>
<button @click="isSeen" = !isSeen">토글</button>
```

* v-if와 v-else 사이에 다른 독립코드가 들어가면 안 된다.
* 다만 v-if 와 v-else 사이에 자식 코그 블럭은 가능하다.

## Template
- 페이지가 로드될 때 렌더링 되지 않지만 JS를 사용하여 나중에 문서에서 사용할 수 있도록 HTML을 보유하기 위한 메커니즘
- 보이지 않는 wrapper의 역할

* ex) div에 v-if 를 사용하면 쓸때없는 div가 생성된다. 이러한 div 없이 하위 요소들만 렌더링 하고 싶다면 template를 쓰면 된다.

* v-if를 사용해 요소들을 렌더링할 때, 조건에 해당되는 요소들은 렌더링 되어 트리에 포함되어 있지만 조건에 해당되지 않는 요소들은 아예 트리상에도 존재하지 않는 요소가 된다.
* 조건이 true가 될 때만 true가 된다.

## v-show
표현식 값의 true/false를 기반으로 요소의 가시성을 전환
- v-show는 항상 DOM에 렌더링 되어 있음

## v-if와 v-show 의 차이
- v-if는 DOM 트리 구조상에 아예 존재하지 않는다.
- v-show는 display가 none 이거나 block인 상태로 DOM에 존재

## v-if 와 v-show의 적절한 사용처
- v-if
  - 초기 조건이 false인 경우 아무 작업도 수행 안 함
  - 토글 비용이 높음

- v-show
  - 초기 조건에 관계없이 항상 렌더링
  - 초기 렌더링 비용이 더 높음

* 콘텐츠를 자주 전환해야 하는 경우에는 v-show를, 실행 중에 조건이 변경되지 않는 경우에는 v-if를 권장


## v-for
소스 데이터를 기반으로 요소 또는 템플릿 블록을 여러번 렌더링

### v-for 구조
- v-for는 alias in expression 형식의 특수 구문을 사용

```
const myArr = ref([
    { name: 'Alice', age: 20 },
    { name: 'Bella', age: 21 }
  ])
```
위 배열을 순회한다면  
(index, item) 이 아니라 (item, index) 순으로 엘레멘트가 나온다.

```
const myObj = ref({
    name: 'Cathy',
    age: 30
  })
```
위 오브젝트를 순회한다면  
(value, key, index) 으로 값이 나온다.
* 우리가 객체를 순회를 하는 이유는 결국 value 값을 찾기 위함이니까..

## v-for with key
내부 컴포넌트의 상태를 일관되게 하여 데이터의 예측 가능한 행동을 유지하기 위함

### 내장 특수 속성 key
- key는 반드시 각 요소에 대한 고유한 값을 나타낼 수 있는 식별자여야 함
- number 혹은 string으로만 사용해야 함
- Vue의 내부 가상 DOM 알고리즘이 이전 목록과 새 노드 목록을 비교할 때 각 node를 식별하는 용도로 사용

## 동일 요소에 v-for와 v-if를 함께 사용하지 않는다.
동일한 요소에서 v-if가 v-for 보다 우선순위가 더 높기 때문
* v-if에서 조건은 v-for 범위 변수에 접근할 수 없음
