# 7월 20일 

# HTML  
> HTML  

- Hyper Text Markup Language  
HTML 이란 웹 페이지의 의미와 구조를 정의하는 마크업 언어

> HyperText
- 웹 페이지를 다른 페이지로 연결하는 링크

> Markup Language
- 태그 등을 이용하여 문서나 데이터의 구조를 명시하는 언어


## HTML의 구조
> < !DOCTYPE html >
- 해당 문서가 html로 문서라는 것을 나타냄

> < html>< /html>
- 전체 페이지의 콘텐츠를 포함

> < head>< /head>
- HTML 문서에 관련된 설명, 설정 등
- 사용자에게 보이지 않음

> < body>< /body>
- 페이지에 표시되는 모든 콘텐츠

* HTML의 내용물을 메타 데이터에 저장? (강의 돌려보기 53분)

> HTML Element 
- 기본 형테 : <여는태그> (콘텐트) </닫는태그>

> HTML 속성
- 여러 개 존재하는 태그를 class로 묶어낼 수 있다.

- 규칙
  - 속성은 요소 이름과 속성 사이에 공백이 있어야함
  - 하나 이상의 속성들이 있는 경우엔 속성 사이에 공백으로 구분
  - 속성 값은 열고 닫는 따옴표로 감싸야 함

- 목적
  - 나타내고 싶지 않지만 추가적인 기능, 내용을 담고 싶을 때 사용
  - CSS에서 해당 요소를 선택하기 위한 값으로 활용


* 사전 설치한 open in browser 확장자로 alt + b 하면 웹이 열린다

* 서버의 경로로 요청을 보내면 이미지도 띄울 수 있다.

* html에 태그를 붙이는 것은 기능적인 의미를 붙이는 것이지 스타일링적인 기능이 아니다.
  - 태그마다 의미를 부여하는 것이 목적

* 접근성 측면의 UX 강화

# CSS
- Cascading Style Sheet
- 웹 페이지의 디자인과 레이아웃을 구성하는 언어

* 종종 웹페이지에 접속하면 보이는 텍스트만 쭉 적혀있는 것이 CSS가 전송 받아지지 않아 랜더링이 되지 않아 그런 것임.

![스크린샷]

## CSS 적용 방법
1. 인라인 스타일
  - HTML 요소 안에 style 속성 값으로 작성 (최대한 사용 X)
2. 내부 스타일 시트
  - head 태그 안에 style 태그에 작성 (권장 x)
3. 외부 스타일 시트
  - 별도의 CSS 파일 생성 후 HTML link 태그를 사용해 불러오기

## CSS 선택자
- HTML 요소를 선택하여 스타일을 적용할 수 있도록 하는 선택자

> 기본 선택자
- 전체("*") 선택자
- 요소(tag) 선택자
- 클래스(class) 선택자
- 아이디(id) 선택자
- 속성(attr) 선택자 등

> 결합자 
- 자손 결합자 (" " (space))
- 자식 결합자 (">")

> 클래스 선택자 ('.' (dot))
- 주어진 클래스 속성을 가진 모든 요소를 선택

> 아이디 선택자 ('#')
- 주어진 아이디 속성을 가진 요소 선택
- 문서에는 주어진 아이디를 가진 요소가 하나만 있어야 함

> 자손 결합자 (" " (space))
- 첫 번째 요소의 자손 요소를 선택
- 예) < p> < span> 은 < p> 안에 있는 모든 < span>를 선택

> 자식 결합자 (">")
- 첫 번째 요소의 직계 자식만 선택


# 명시도 Specificity
- 결과적으로 요소에 적용할 CSS 선언을 결정하기 위한 알고리즘

- CSS Selector에 가중치를 계싼하여 어떤 스타일을 적용할지 결정

> 명시도가 높은 순
1. Importance (디버깅용)
   - !important
2. Inline 스타일 (디버깅용)

3. 선택자
   - id 선택자 > class 선택자 > 요소 선택자
4. 소스 코드 선언 순서


* 대부분 class를 가지고 스타일링 할 것이다
* id를 갖는 요소는 딱 하나만 존재할때 사용

## !important
- 다른 우선순위 규칙보다 우선하여 적용하는 키워드
* Cascade의 구조를 무시하고 강제로 스타일을 적용하는 방식이므로 사용을 권장하지 않음

# Box Model 
- 모든 HTML 요소를 사각형 박스로 표현하는 개념

> Box 구성 요소
- Margin
  - 이 박스와 다른 요소 사이의 공백 가장 바깥쪽 영역
- content 
  - 콘텐츠가 표시되는 영역
- Boder
  - 콘텐츠와 패딩을 감싸는 영역
- Padding
  - 콘텐츠 주위에 위치하는 공백 영역

> width & height 속성
- 요소의 너비와 높이를 지정, 이때 지정되는 요소의 너비와 높이는 콘텐츠 영역을 대상으로 함

> CSS가 width 값을 계산하는 기준
- CSS는 border가 아닌 content의 크기를 width 값으로 지정

* content 기준인지 boder 기준인지에 따라 box의 사이즈가 달라진다.

### block 타입 특징
- 항상 새로운 행을 나뉨
- width와 height 속성을 사용하여 너비와 높이를 지정할 수 있음
- 기본적으로 width 속성을 지정하지 않으면 박스는 inline 방향으로 사용 가능한 공간을 모두 차지함
(너비를 사용 가능한 공간의 100%로 채우는 것)
- 대표적인 block 타입 태그
  - h1 ~ 6 , P, div

### inline 타입 특징
- 새로운 행으로 나뉘지 않음
- width와 height 속성을 사용할 수 없음
- 수직방향
  - padding, margins, boders가 적용되지만 다른 요소를 밀어낼 수는 없음
- 수평 방향
  - padding, margins, boders가 적용되어 다른 요소를 밀어낼 수 있음 (왼쪽 정렬이 디폴트)
- 대표적인 inline 타입 태그
  - a, img, span

### inline-block
- inline과 block 요소 사이의 중간 지점을 제공하는 display 값
- block 요소의 특징을 가짐
  - width 및 height 속성 사용 가능
  - padding, margin 및 border로 인해 다른 요소가 밀려남
* 요소가 줄 바꿈 되는 것을 원하지 않으면서 너비와 높이를 적용하고 싶은 경우에 사용

* float도 있다. 택스트와 어울리기 위해?

### flex
- 요소를 행과 열 형태로 배치하는 1차원 레이아웃 방식
  - 공간 배열 & 정렬

- Flex Container 관련 속성
  - display, flex-direction, flex-wrap, justify-contnet

* flex는 축이 있다. 자신의 영역 안에서 자식들을 메인 축을 기준으로 정렬한다.

### none
- 요소를 화면에 표시하지 않고, 공간조차 부여되지 않음
* 보통 btn을 눌러야 보일 때 사용한다.
* 공간도 사용하지 않지만 element는 lendering 되어 있어 메모리에 road 되어있다.
* visiblitysms 선택도 못 하고 보이지도 않지만 공간은 차지한다.
* opacity는 선택은 가능하다.

### shorthand 속성
> Border
- border-width, border-style, border-color를 한번에 설정하기 위한 속성

> margin & padding
- 4방향의 속성을 각자 지정하지 않고 한번에 지정할 수 있는 속성
* 상우하좌, 상/좌우/하, 상하/좌우, 공통

### Margin collapsing (마진상쇄)
- 두 block 타입 요소의 margin top과 bottom이 만나 더 큰 margin으로 결합되는 현상
- 웹 개발자가 레이아웃을 더욱 쉽게 관리할 수 있도록 함
- 각 요소에 대한 상/하 margin을 각각 설정하지 않고 한 요소에 대해서만 설정하기 위함


# CSS Position
요소를 Normal Flow에서 제거하여 다른 위치로 배치하는 것
* Position의 이동방향은 사실 z축이 있다.

### Position 유형
1. Static (기본값)
2. Relative (상대값 : normal flow 상의 내 위치를 기준으로)
3. Absolute (절대값 : 가장 가까운 부모 요소를 기준으로)
4. Fixed (고정 : 특정 위치에 고정?)
5. Sticky

### Position 유형별 특징
- static
  - 기본값
  - 요소를 normal flow에 따라 배치

- relative
  - 요소를 normal flow에 따라 배치
  - 자기 자신을 기준으로 이동
  - 요소가 차지하는 공간은 static일 때와 같음

- absolute
  - 요소를 normal flow에서 제거
  - rkwkd rkRKdns relative 부모 요소를 기준으로 이동
  - 문서에서 요소가 차지하는 공간이 없어짐 

- fixed
  - 요소를 normal flow에서 제고
  - 현재 화면영역(viewport)을 기준으로 이동
  - 문서에서 요소가 차지하는 공간이 없어짐

- sticky
  - 요소를 normal flow에 따라 배치
  - 요소가 일반적인 문서 흐름에 따라 배치되다가 스크롤이 특정 임계점에 도달하면 그 위치에서 고정됨

<br>* flexbox froggy로 연습해보자

# CSS 상속
기본적으로는 CSS는 상속을 통해 부모 요소의 속성을 자식에게 상소해 재사용성을 높임

- 상속되는 속성
  - Text 관련 요소 (font, color, text-align), opacity, visibility 등

- 상속 되지 않는 속성
  - Box model 관련 요소(width, height, border, box-sizing ...)
  - position 관련 요소(position, top/right/bottom/left, z-index) 등

* 상속 되지 않는 속성은 주로 크기와 관련된 것들
* 상속 되는 속성은 일관성을 갖게 하고 싶은 요소들

