# Quest 00. 형상관리 시스템

## Introduction
* git은 2021년 현재 개발 생태계에서 가장 각광받고 있는 버전 관리 시스템입니다. 이번 퀘스트를 통해 git의 기초적인 사용법을 알아볼 예정입니다.

## Topics
* git
  * `git clone`, `git add`, `git commit`, `git push`, `git pull`, `git branch`, `git stash` 명령
  * `.git` 폴더
* GitHub

## Resources
* [Resources to learn Git](https://try.github.io)
* [Learn Git Branching](https://learngitbranching.js.org/?locale=ko)
* [Inside Git: .Git directory](https://githowto.com/git_internals_git_directory)

## Checklist
* 형상관리 시스템은 왜 나오게 되었을까요?

  수정 전 파일 상태로 돌아가고 싶을때

  사용자가 직접 파일 이름을 수정해가며 저장하지 않고도 전 파일로 돌아가는게 가능하게 하기 위해

  협업할 때

  동시에 같은 파일을 수정하더라도 충돌이 일어나지 않게 하기 위해

* git은 어떤 형상관리 시스템이고 어떤 특징을 가지고 있을까요? 분산형 형상관리 시스템이란 무엇일까요?
  
  git은 분산형 형상관리 시스템이다.
  
  분산형 형상관리 시스템은 중앙형 형상관리 시스템과 달리 각각의 클라이언트가 서버의 저장소를 통채로 불러와 작업한다
  
  따라서 중앙서버에 문제가 생겨도 복구 가능하다
  
  [깃(Git), 깃허브(Github) 간단요약 (velog.io)](https://velog.io/@gparkkii/GitGithub)
  
  * git은 어떻게 개발되게 되었을까요? git이 분산형 시스템을 채택한 이유는 무엇일까요?
  
    비트키퍼가 유료화되자 리누스 토르발스에 의해 개발되었다.
  
    분산형 시스템이 아니면 해킹에 취약하므로 각각의 호스트가 독립적으로 작동할 수 있도록 분산형 시스템을 채택했다.
  
    [깃 (소프트웨어) - 위키백과, 우리 모두의 백과사전 (wikipedia.org)](https://ko.wikipedia.org/wiki/깃_(소프트웨어))
  
* git과 GitHub은 어떻게 다를까요?

  깃허브는 깃의 내용을 올릴 수 있는 원격 저장소이다.

  깃허브를 통해 다른 사람의 깃 내용을 확인할 수 있다

* git의 clone/add/commit/push/pull/branch/stash 명령은 무엇이며 어떨 때 이용하나요? 그리고 어떻게 사용하나요?![image-20211008135228753](C:\Users\dyk62\AppData\Roaming\Typora\typora-user-images\image-20211008135228753.png)

  clone: 깃허브 등 원격 저장소의 repository를 pc에 불러옴

  add: 로컬 컴퓨터의 변경 기록을 staging area에 올림

  commit: staging area에 올려진 변경 기록을 커밋 메시지와 함께 head에 올림

  push: 로컬 저장소의 변경기록을 깃허브 원격 저장소에 올림

  pull: 깃허브 원격 저장소의 변경기록을 내 pc에 불러옴

  branch: 현재 어떤 브랜치를 사용하고 있는지 알려줌

  stash: 하던 작업을 커밋하기 전에 임시저장

  [Web Club :: Git 기초- 깃(git) 명령어 배워보기 (tistory.com)](https://webclub.tistory.com/317)

* git의 Object, Commit, Head, Branch, Tag는 어떤 개념일까요? git 시스템은 프로젝트의 히스토리를 어떻게 저장할까요?

  object: 깃은 4가지 object를 가진다. blob, tree, commit, tag가 그것이다.

  commit: commit을 하면 objects 폴더에 commit object, tree object가 생성된다.

  commit object에는 tree object 이름, 저자, 날짜, 커밋 메시지가 저장된다.

  head: 현재 브랜치를 가리킨다

  branch: 버전 관리, 협업을 가능하게 한다. 브랜치를 여러개 설정하면 각각의 브랜치의 변경내용이 다른 브랜치에 반영되지 않는다.

  tag: commit object를 가리킨다.

  objects 폴더 하위에 blob 파일들이 저장되어 프로젝트의 히스토리를 저장할 수 있다.

  [[Git\] 내부 동작 원리에 대한 이해 (tistory.com)](https://it-eldorado.tistory.com/4)

* 리모트 git 저장소에 원하지 않는 파일이 올라갔을 때 이를 되돌리려면 어떻게 해야 할까요?

  깃허브에서 쓰레기통 아이콘을 누른다

  혹은 터미널에서 git rm --cached 파일명을 입력한다.

  참고로 이런일이 반복되지 않으려면 .gitingnore 폴더를 이용하면 된다.

## Quest
* GitHub에 가입한 뒤, [이 커리큘럼의 GitHub 저장소](https://github.com/KnowRe-Dev/WebDevCurriculum)의 우상단의 Fork 버튼을 눌러 자신의 저장소에 복사해 둡니다.
* Windows의 경우 같이 설치된 git shell을, MacOSX의 경우 터미널을 실행시켜 커맨드라인에 들어간 뒤, 명령어를 이용하여 복사한 저장소를 clone합니다.
  * 앞으로의 git 작업은 되도록 커맨드라인을 통해 하는 것을 권장합니다.
* 이 문서가 있는 폴더 바로 밑에 있는 sandbox 폴더에 파일을 추가한 후 커밋해 보기도 하고, 파일을 삭제해 보기도 하고, 수정해 보기도 하면서 각각의 단계에서 커밋했을 때 어떤 것들이 저장되는지를 확인합니다.
* `clone`/`add`/`commit`/`push`/`pull`/`branch`/`stash` 명령을 충분히 익혔다고 생각되면, 자신의 저장소에 이력을 push합니다.

## Advanced
* Mercurial은 어떤 형상관리 시스템일까요? 어떤 장점이 있을까요?
* 실리콘밸리의 테크 대기업들은 어떤 형상관리 시스템을 쓰고 있을까요?
