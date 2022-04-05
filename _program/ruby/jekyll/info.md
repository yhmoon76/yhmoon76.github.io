---
title: Jekyll
author: WooYou
date: 2022-03-31
category: [rudy, Jekyll]
layout: default
---

###Jekyll 과 Bundler

```shell
  Jekyll 과 Bundler 를 설치 및 설치 확인
  $ gem install jekyll bundler
  
  jekyll 버전 확인
  $ jekyll -v

  ./myblog 에 새 Jekyll 사이트를 생성한다.
  $ jekyll new myblog
  
  사이트를 빌드하고 로컬 서버에 적용한다.
  $ bundle exec jekyll serve
  
  'require': cannot load such file -- webrick (LoadError) 에러시 
  $ bundle add webrick
```

RubyMine Run/Debug 설정

메뉴 : Run > Edit Configurations  
![Edit Configurations](/images/program/ruby/jekyll/Edit_Configurations.PNG)




* [Liquid 필터](https://jekyllrb-ko.github.io/docs/liquid/filters/)
* [jekyll 설치 url](https://jekyllrb-ko.github.io/docs/)
* [jekyll 참조1](http://djflexible.github.io/blog/github-jekyll.html)
* [jekyll 참조2](https://blog.naver.com/h_proms/221208814331)