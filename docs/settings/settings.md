---
layout: default
title: 세팅
nav_order: 1
has_children: true
permalink: /docs/settings
---

# Settings

<!-- When Setting packages for beginning on mac, I usually do these belows through brew. 

I do not put in details, since there are chances the way to install is changed, Details can be founded on chat gpt. -->
보통 초기 세팅시에 아래 것들을 기본적으로 설치한다. brew를 통해 기본적으로 설치를 함. 시간이 지나면 변경되는 일이 잦으니까
 자세한 설치법은 chat gpt나 검색을 통해서 확인하는게 좋다.

## 1. brew 
> 환경변수에 등록하는 것 잊지말기

  - vim
  - oh my zsh
  - item2
  - vscode
  - nvm 
  - git

## 2. ssh keygen
> 두개 이상의 깃허브 계정을 활용할때는 계정에 따라 키를생성한다.

### 1) ssh 키 생성
- 각 계정에 대해 ssh키 생성
```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

- 키 생성 중에 두 번 물어보면서 "Enter a file in which to save the key"라는 메시지가 나타남. 여기서 기본값인 /Users/you/.ssh/id_rsa를 변경하여 각 계정에 맞게 지정. 
```bash 
/Users/you/.ssh/id_rsa_second
``` 

### 2) ssh 에이전트에 키 추가
```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
ssh-add ~/.ssh/id_rsa_second
ssh-add -l //로 확인
``` 

### 3) ssh 키를 github에 추가
계정 > settings > ssh 공개키 등록

### 4) config 작성

```bash
Host github-personal
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa_personal

Host github-work
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa_work
```
> 여기까지 잘 진행되면 아래와 같은 명령어로 확인가능함

```
ssh -T git@github-personal
ssh -T git@github-work

하면 키에 따라 계정연결됨 확인가능
```

```
➜  .ssh ssh -T git@github-work
Hi ccoli-buzzni! You've successfully authenticated, but GitHub does not provide shell access.
➜  .ssh ssh -T git@github-personal
Hi broccoliInDB! You've successfully authenticated, but GitHub does not provide shell access.
```

### 5) 각 프로젝트의 config는 구별해서 등록해준다.
```
git config user.name "Your Name"
git config user.email "your-email@example.com"
```