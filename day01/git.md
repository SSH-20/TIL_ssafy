# Git
>Git 이란 무엇인가?
- 분산 버전 관리 시스템

>버전 관리
- 변화를 기록하고 추적하는 것
- 개발을 하게되면 작업을 진행할 떄 어떠한 버전에서 작성된 것인지가 중요하기 때문
* ex) 파이썬 3.11.7, major.minor.

> 중앙
- 버전은 중앙 서버에 저장되고 중앙 서버에서 파일을 가져와 작업을 진행
> 분산식
- 버전을 여려 개의 복제된 저장소에 저장 및 관리

> Git의 역할
- 개발의 히스토리 관리

# Git의 세 가지 영역
- Working Directory (작업영역)
- Staging Area (다음 버전에 포함시킬 내용만 저장하는 중간 영역)
- Repository (수정된 사항이 버전별로 저장되는 저장소)

* hub, lab 등의 원격 저장소는 포함되지 않음

- 실제 수정은 WD에서 이뤄지고, 수정한 결과물 중 다음 버전에 수정될 것만 SA에 저장하고 Commit 하면 버전을 찍어서 Repo에 저장한다.
- 위 과정이 끝나면 Staging Area는 지워진다.

# Git의 동작
- git init (깃 초기화)
- git status (현재 상태 조회, 커밋을 했는가 안 했는가)
- git add (깃에 추가)

* 자리 변경할때 git에게 알려준 global을 지워야한다. 

> 자리 옮기거나 이메일 정보가 잘못 되었을때 수정하는 방법
code ~/.gitconfig 

파일 내부의 이메일 지우기

# Commit하는 방법
* git commit 을 실행하면 메모장이 나온다
- 커밋 -> 어떠한 수정사항이 있는지 작성하기
- 무엇을 작성했는지

commit을 통해 수정된 파일은 status를 쳤을 때 나오지 않는다.
-> 수정된 파일은 Log에 남는다

> 작업을 진행할 때
* git init -> status -> add -> status -> commit -> status -> log

> Commit할 때 vim 창에 들어가고 싶지 않다면?
* git commit -m "메세지 입력"

> commit한 내용 메모를 한 줄로 간결하게 보고싶다면?
* git log --oneline

> commit한 내용을 ?? 하게 보고싶다면?
* git log --onelin --graph

> Commit은 언제 하는가?
* 본래 commit은 기능의 Update 마다 해야하는 것이다.
* 우리는 아직 익숙하지 않기 때문에 강사님이 쉬자고 하실 떄마다 commit 하는 습관을 들이자
* 파일의 무엇을 수정하고 무엇을 추가하였는지

# SUbModule
* 현재 작업중인 디렉토리에서 git 을 생성한 후에 상위 폴더로 이동하여 git을 또 생성하면 현재와 상위 디렉토리 둘 다 master가 된다.
* 그러한 경우 하위 디렉토리는 서브모듈이 된다.