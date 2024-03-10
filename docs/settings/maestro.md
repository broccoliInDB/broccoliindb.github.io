---
layout: default
title: maestro
parent: 세팅
nav_order: 1
---
# [Maestro](https://maestro.mobile.dev/)
마에스트로는 mobile UI testing framework 이다.

## 설치방법
[[공식 설치방법 링크]](https://maestro.mobile.dev/getting-started/installing-maestro)

설치후에 환경변수를 추가한다.

```
export PATH="$PATH":"$HOME/.maestro/bin"
```

이후에 자바를 설치해야한다.
[[자바는 공식 사이트]](https://www.oracle.com/kr/java/technologies/downloads/) 에서 해당하는 cpu에 설치파일을 받는다 나는 m2니까 arm으로 받았고 dmg를 받아 설치함. 

> 자바홈으로 환경등록을 해야하는데 일단은 자바경로를 찾아주고 있길래 생략함.

설치 후 
maestro 스크립트를 yaml파일로 만들고 실행할때 아래의 같은 에러가 보인다면

```
error: unable to find utility 'simctl', not a developer tool or in PATH
```

```
xcode-select --install
sudo xcode-select -switch /Applications/Xcode.app/Contents/Developer
```

를 실행하면 됨