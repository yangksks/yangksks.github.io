---
emoji: 🥽
title: (Git) Git과 GitHub
date: '2022-01-07 00:00:00'
author: 양경섭
tags: Git
categories: 프레임워크
---

## 로컬저장소 만들기
```bash
$ git init
```
* **Initialized empty Git repository** 라는 문구가 나오면 성공
* 위의 명령어를 실행하면 해당 디렉토리에 [.git]이라는 폴더가 자동으로 생성됩니다.

```bash
$ git config --global user.email "[이메일]"
$ git config --global user.name "[이름]"
```
* 누가 커밋을 했는지 확인 하기 위한 세팅입니다 


## 커밋은 add->commit->push
 ```bash
 $ git add [파일명]
 $ git commit -m "[커밋 설명]"
 ```
 * **push** 명령어는 원격저장소에 로컬저장소의 커밋을 push 하는 명령어이기 때문에 원격저장소 실습에서 다시 정리하겠습니다.


 ## 이전 커밋으로 돌아가기
 ```bash
 $ git log
 $ git checkout [커밋 ID]
 ```
* **log** 명령어를 통해서 저장된 커밋을 확인할 수 있고 **커밋 ID**를 복사하여 **checkout** 명령어를 통해서 버전을 되돌립니다.
* 커밋 ID 에서 -는 최신 커밋을 의미합니다


## 원격저장소에 커밋 올리기
```bash
$ git remote add origin [원격저장소 주소]
$ git push origin master
```
* 우선 로컬저장소에 원격저장소 주소를 등록해야합니다.
* 그리고 로컬저장소에 있는 커밋들을 push 명령어로 원격저장소에 올립니다.


## 원격저장소의 커밋을 로컬저장소에 내려받기
* 원격저장소의 코드와 버전 전체를 내 컴퓨터로 내려받는 것을 **클론** 이라고 합니다.

```bash
// 원하는 로컬저장소의 경로에서 아래 명령어를 입력합니다.
$ git clone [원격저장소 주소]
```


## 원격저장소의 새로운 커밋을 로컬저장소에 갱신하기
```bash
$ git pull origin master
```
* **pull**은 원격저장소에 새로운 커밋이 있다면 그걸 내 로컬저장소에 받아오는 명령어입니다.  


```toc

```