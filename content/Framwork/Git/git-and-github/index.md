---
emoji: 🥽
title: (Git) Git Bash를 시작해보자
date: '2022-01-16 00:00:00'
author: 양경섭
tags: Git
categories: 프레임워크
---

# 로컬저장소 만들기

| 명령어        | 설명                                     |
| ------------- | ---------------------------------------- |
| git status    | git 워킹트리의 상태를 보여준다           |
| git status -s | git status 명령을 짧게 요약해서 보여준다 |
| git init      | 현재 폴더에 Git 저장소를 생성한다        |

### Git 저장소 초기화

```bash
$ git init # Git 저장소 생성

$ ls -a # 파일 목록 확인

$ git status # 워킹 트리 상태 확인
```

- **Initialized empty Git repository** 라는 문구가 나오면 성공
- 위의 명령어를 실행하면 해당 디렉토리에 [.git]이라는 폴더가 자동으로 생성됩니다.

### 옵션 설정하기

```bash
$ git config --global <옵션명> # 지정한 전역 옵션의 내용을 확인

$ git config --global <옵션명> <새로운 값> # 지정한 전역 옵션의 값을 새로 설정

$ git config --global --unset <옵션명> # 지정한 전역 옵션을 삭제

$ git config --local <옵션명> # 지정한 지역 옵션의 내용을 확인

$ git config --local <옵션명> <새로운 값>

$ git conifg --local --unset <옵션명>
```

```bash
$ git config --global user.email "<이메일>"
$ git config --global user.name "<이름>"
```

- 누가 커밋을 했는지 확인 하기 위한 세팅입니다

# 기본 CLI 명령어

### 기본적인 git 명령들

```bash
$ git add 파일1 파일2 ... # 파일들을 스테이지에 추가

$ git commit # 스테이지에 있는 파일들을 커밋

$ git commit -a # add명령을 생략하고 바로 커밋 , 단 untracked 파일은 커밋 X

$ git push [-u] [원격저장소별명] [브랜치이름] # 현재 브랜치에서 새로 생성한 커밋들을
# 원격저장소에 업로드, -u 옵션으로 브랜치의 업스트림을 등록할 수 있다.

$ git pull # 원격저장소의 변경사항을 워킹트리에 반영한다
```

### CLI로 log 살펴보기

```bash
$ git log # 현재 브랜치의 커밋 이력을 보는 명령

$ git log -n<숫자> # 전체 커밋 중 최신 n개의 커밋만 살펴봅니다

$ git log --oneline --graph --decorate -all # 자주 사용하는 옵션으로, 간결하게 보여준다
# --oneline : 커밋 메시지를 한 줄로 요약해서 보여줍니다
# --graph : 커밋 옆에 브랜치의 흐름을 그래프로 보여줍니다
# --decorate : 원래는 --decorate=short 옵션을 의미,브랜치와 태그 등의 참조를 간결하게 표시
# --all : all 옵션이 없을 경우 HEAD와 관계없는 옵션은 보여주지 않는다
```

💡 좋은 커밋 메시지의 7가지 규칙

1. 제목과 본문을 빈 줄로 분리한다
2. 제목은 50자 이내로 쓴다
3. 제목을 영어로 쓸 경우 첫 글자는 대문자로 쓴다
4. 제목에는 마침표를 넣지 않는다
5. 제목을 영어로 쓸 경우 동사원형으로 시작한다
6. 본문을 72자 단위로 줄바꿈한다.
7. 어떻게 보다 무엇과 왜를 설명한다.

### reset 명령어로 언스테이징하기

```bash
$ git reset [파일명] # 스테이지 영역에 있는 파일을 내립니다
```

# 원격저장소 관련 CLI 명령어

| 명령어                                             | 설명                                                                                |
| -------------------------------------------------- | ----------------------------------------------------------------------------------- |
| git remote add <원격저장소 이름> <원격저장소 주소> | 원격저장소 등록, 여러개 등록할 수 있지만 통상 첫 번째 원격 저장소를 origin으로 지정 |
| git remote -v                                      | 원격저장소 목록을 살펴본다                                                          |

### 원격저장소 등록 및 push

```bash
$ git remote add origin <원격저장소 주소>

$ git remote -ve

$ git push
```

- 업스트림 에러가 발생 할 수 있다
- 로컬저장소의 master 브랜치와 연결된 원격저장소의 브랜치가 없어서 발생하는 오류

### git push 재시도

```bash
$ git push -u origin master
```

- 브랜치가 연결되었기때문에 이후에는 *git push*로 수행할 수 있다

### git clone 사용해 보기

```bash
$ git clone <저장소 주소> [새로운 폴더명] # 로컬저장소 주소도 클론이 가능하다
```

```toc

```
