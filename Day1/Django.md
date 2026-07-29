# 7월 29일 수
# Django

## Framework
### '웹 서비스 개발' 에는 무엇이 필요할까?
- 로그인, 로그아웃, 회원관리, DB, 보안 등.. 너무 많은 기술 필요
- 하나부터 열까지 개발자가 모두 작성하는 것은 현실적으로 어려움
- 모든 걸 직접 만들 필요 X

## Web Framework
웹 애플리케이션을 빠르게 개발할 수 있도록 도와주는 도구
- 개발에 필요한 기본 구조, 규칙, 라이브러리 등을 제공

## Django
Python 기반의 대표적은 웹 프레임워크

### 왜 Django를 사용하는가?
- 다양성
  - Python 기반으로 소셜 미디어 및 빅데이터 관리 등 광범위한 서비스 개발에 적합

- 확장성
  - 대량의 데이터에 대한 빠르고 유연하게 확장할 수 있는 기능을 제공

- 보안
  - 취약점으로부터 보호하는 보안 기능이 기본적으로 내장되어 있음

- 커뮤니티 지원
  - 개발자를 위한 지원, 문서 및 업데이트를 제공하는 활성화 된 커뮤니티 

## Django Design Pattern
소프트웨어 설계에서 발생하는 문제를 해결하기 위한 일반적인 해결책  
( 공통적인 문제를 해결하는 데 쓰이는 형식화 된 관행 )

### MVC 디자인 패턴 (Model, View, Controll)
애플리케이션을 구조화하는 대표적인 패턴  
("데이터" & "사용자 인터페이스" & "비즈니스 로직"을 분리)

### MTV 디자인 패턴 (Model, Template, View)
Django에서 애플리케이션을 구조화하는 패턴  
( 기존 MVC 패턴과 동일하나 단순히 명칭을 다르게 정의한 것 )
- View &rarr; Template
- Controller &rightarrow; View

### Django Project
애플레케이션의 집합  
(DB 설정, URL 연결, 전체 앱 설정 등을 처리)

### Django application
독립적으로 작동하는 기능 단위 모듈  
(각자 특정한 기능을 담당하며 다른 앱들과 함께 하나의 프로젝트를 구성)

## API
두 소프트웨어가 서로 통신할 수 있게 하는 메커니즘

## REST
API Server를 개발하기 위한 일종의 소프트웨어 설계 "방법론"

### RESTful APi
- REST 원리를 따르는 시스템을 RESTful 하다고 부름
- "자원을 정의"하고 "자원에 대한 주소를 지정"하는 전반적인 방법을 서술

### REST에서 자원을 사용하는 법 3가지
1. 자원의 "식별"
  - URI
2. 자원의 "행위"
  - HTTP Methods
3. 자원의 "표현"
  - JSON 데이터

## 자원의 식별
### URI
인터넷에서 리소스(자원)를 식별하는 문자열

### URL
웹이서 주어진 리소스의 주소


### HTTP Request Methods
리소스에 대한 행위 (수행하고자 하는 동작)을 정의

1. GET
  - 서버에 리소스의 표현을 요청
  - GET을 사용하는 요청은 데이터만 검색해야 함
2. POST
  - 데이터를 지정된 리소스에 제출
  - 서버의 상태를 변경
3. PUT
  - 요청한 주소의 리소스를 수정
4. DELETE
  - 지정된 리소스를 삭제

### HTTP response status codes
특정 HTTP 요청이 성공적으로 오나료 되었는지 여부를 나타냄

- 5개의 응답 그룹
  - Informational responses (100 ~ 199)
  - Successful responses (200 ~ 299)  `중요`
  - Redirection messages (300~399)
  - Client error responses (400 ~ 499)  `중요`
  - Server error responses (500 ~ 599)  `중요`


### DRF : Django REST framework
django에서 Restful API 서버를 쉽게 구축할 수 있도록 도와주는 오픈소스 라이브러리

