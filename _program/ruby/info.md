---
title: Rudy
author: WooYou
date: 2022-03-30
category: rudy
layout: post
isMenu: true
---
## [Ruby](https://rubyinstaller.org/)

* [download](https://rubyinstaller.org/downloads/)
* 설치후 버전확인
  <pre>
  $ ruby -v
  ruby 2.7.5p203 (2021-11-24 revision f69aeb8314) [x64-mingw32]
  </pre>
* boom.rb 파일 생성후 실행

    <pre>
    boom.rb 
    
    print("Boom!")
    
    
    $ ruby boom.rbr
    </pre>


* To install sqlite3 gem

    <pre>
    ridk exec pacman -S mingw-w64-x86_64-sqlite3
    gem install sqlite3 --platform ruby
    </pre>

* To install nokogiri gem

    <pre>
    ridk exec pacman -S mingw-w64-x86_64-libxslt
    gem install nokogiri --platform ruby -- --use-system-libraries
    </pre>

* Jekyll 과 Bundler

```shell
  Jekyll 과 Bundler 를 설치 및 설치 확인
  $ gem install jekyll bundler
  
  jekyll 버전 확인
  $ jekyll -v

  ./myblog 에 새 Jekyll 사이트를 생성한다.
  $ jekyll new myblog
  
  사이트를 빌드하고 로컬 서버에 적용한다.
  $ bundle exec jekyll serve
```

* [jekyll 설치 url](https://jekyllrb-ko.github.io/docs/)
* [jekyll 참조1](http://djflexible.github.io/blog/github-jekyll.html)
* [jekyll 참조2](https://blog.naver.com/h_proms/221208814331)