---
title: TIL. 210110) git 명령어
excerpt: 블로그를 만들면서 몇가지 git 명령어에 익숙해졌다.

header:
  teaser: /assets/images/blessing.png
  overlay_image: /assets/images/blessing.png
  overlay_filter: 0.2
  # caption:

categories:
  - TIL
tags:
  - git
---

# 블로그를 만들며 익숙해진 git 명령어들

git 너무 어렵다. 블로그 만들고 싶어서 엉엉 울면서 배운 명령어들! &#128518; 아직 자세한 개념은 더 공부해야하지만, git bash로 git에 뭔가를 연결시켜서 올릴 수 있게 되어 뿌듯하다! 잊어버리지 않게 메모해둔다. 다음엔 좀더 자세하게 공부해봐야지,,,

#### 1. 로컬이랑 리모트 리포지토리[원격 저장소]랑 연결

```bash
# 로컬 내 블로그 폴더로 이동!
cd jeong-yeon-lee.github.io
# 로컬 저장소로 지정!
$ git init
# 이걸 하면 옆에 브랜치가 표시됨
# 폴더 내에 모든 파일 올리기->Staging Area
$ git add .
#Staging Area 에 있는 파일들을 커밋(저장?)
$ git commit -m "커밋메시지"
#브랜치가 master로 되어있어서 main으로 바꿔감
$ git branch -M main
# Github의 원격 저장소와 연결!!!
$ git remote add git@github.com:Jeong-yeon-Lee/Jeong-yeon-Lee.github.io.git(원격저장소 주소)
# 원격 저장소에 저장!
$ git push -u origin main
```

#### 2. 브랜치

```bash
# 브랜치 보기
$ git branch
# 브랜치 만들기
$ git branch {브랜치 이름}
# 브랜치 고치기
$ git branch -m {브랜치 원래이름} {바꿀이름}
# 브랜치 삭제하기
$ git branch -d {브랜치 이름}
# 특정 브랜치로 가기
$ git checkout {브랜치 이름}
```

#### 3. 잘못된 커밋 삭제하고 돌아가기

```bash
# 특정 커밋으로 돌아가기
$ git reset --{옵션} {돌아가고 싶은 커밋해시}
# 잘못된 커밋들 완전 삭제후 이전상태로 돌아가기
# (참고)협업시에는 위험함!
$ git reset --hard {돌아가고 싶은 커밋해시}
# 원하는 커밋으로 돌아온 후, 오류없이 강제 push
$ git push -f origin main

```

#### 4. 기타 사용한 것(Linux CLI 명령어들)

```bash
# 기본적으로
$ {명령어} {location/of/file}
# 파일의 내용 보기
$ cat {파일명}
# 현재 폴더안에 있는 것들 보기
$ ls
# 폴더 들어가기
$ cd {폴더명}
# 파일 삭제
$ rm {파일명}
# 폴더와 내부 파일까지 모두 삭제할 경우 -r 옵션을 준다
$ rm -r {폴더명}
# 물어보지 않고 강제 삭제를 원할 경우-f (--force) 옵션을 준다
# 즉, 강제로 폴더와 폴더 내 모든 파일들을 삭제하고자 할 경우,
$ rm -r-f {파일/폴더명}
```
