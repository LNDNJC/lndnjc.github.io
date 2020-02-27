---
title:  "Git - Command"
excerpt: "DevCommon"

categories:
  - DevCommon
tags:
  - Git
  - VS
  - Dev
last_modified_at: 2020-02-27T10:06:00-05:00
---
# Git

## Command

- git init : git create (생성하기)
- git clone git_path : import Code (코드 가져오기)
- git checkout branch_name : Select Branch (브랜치 선택하기)
- git checkout -t remote_path/branch_name : Select Romote Branch (원격 브랜치 선택하기)
- git branch branch_name : Create Branch (브랜치 생성하기)
- git branch -r : View Remote Branch List (원격 브랜치 목록보기)
- git branch -a : View Local Branch List (로컬 브랜치 목록보기)
- git branch -m branch_name change_branch_name : Change Branch Name (브랜치 이름 바꾸기)
- git branch -d branch_name : Delete Branch (브랜치 삭제하기)
- git push remote_name — delete branch_name : Delete Remote Branch (원격 브랜치 삭제하기) ( git push origin — delete gh-pages )
- git add file_path : Select Changed Code (수정한 코드 선택하기) ( git add * )
- git commit -m “commit_description” : Comment on Selectecd Code (선택한 코드 설명 적기) ( git commit -m “내용”)
- git push romote_name branch_name : Send Added and Commited Code into Server (add하고 commit한 코드 git server에 보내기) (git push origin master)
- git pull : Merge Code (git서버에서 최신 코드 받아와 merge 하기)
- git fetch : Get Code from git server (git서버에서 최신 코드 받아오기)
- git reset — hard HEAD^ : Cancel the previous code (commit한 이전 코드 취소하기)
- git reset — soft HEAD^ : Cance only commit but not delete code (코드는 살리고 commit만 취소하기)
- git reset — merge : Cancel Merge (merge 취소하기)
- git reset — hard HEAD && git pull : Get git Code forcely (git 코드 강제로 모두 받아오기)
- git config — global user.name “user_name ” : Change Git ID Name (git 계정Name 변경하기)
- git config — global user.email “user_email” : Change Git ID Mail (git 계정Mail 변경하기)
- git stash / git stash save “description” : Save Temply Changed code and Change Branch (작업코드 임시저장하고 브랜치 바꾸기)
- git stash pop : Get the last Code which is saved temply (마지막으로 임시저장한 작업코드 가져오기)
- git branch — set-upstream-to=remote_path/branch_name : Solve Error of git pull no tracking info (git pull no tracking info 에러해결)

[GitHub Upload](https://www.notion.so/GitHub-Upload-2d489f7fca404f039ab84bc457768a44)