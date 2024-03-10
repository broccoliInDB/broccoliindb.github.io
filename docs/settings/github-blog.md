---
layout: default
title: jekyll
parent: 세팅
nav_order: 3
---
# [Jekyll](https://jekyllrb-ko.github.io/)
정적웹사이트 생성기

## 빠른 시작방법

사용하고픈 템플릿을 선정해서 `계정.github.io` 로 레포를 만들면됨.

[[예시: just-the-docs]](https://github.com/just-the-docs/just-the-docs)

이후 로컬에서 실행하려면

```
gem install bundler
bundle install
bundle exec jekyll serve
```

하면 되는데 아래 에러가 날수도 있음.
```
ERROR:  While executing gem ... (Gem::FilePermissionError)
    You don't have write permissions for the /Library/Ruby/Gems/2.6.0 directory.
```

이경우 사용자 홈 디렉토리에 gem을 설치하도록 환경변수를 설정한다.

```
export GEM_HOME=$HOME/.gem
export PATH=$GEM_HOME/bin:$PATH
```

이후 다시 로컬 실행과정을 반복하면 됨.

참고로 ruby 버전은 `rbenv`를 통해함.
chat gpt를 통해 디테일은 확인하기