---
title: Rudy
author: WooYou
date: 2022-03-30
category: info
layout: default
---

[ruby 한글 홈페이지][1]  
[jetbrains RubyMine][2]

## [Ruby](https://rubyinstaller.org/)

* [download](https://rubyinstaller.org/downloads/)
* 설치후 버전확인
  ```shell
  $ ruby -v
  ruby 2.7.5p203 (2021-11-24 revision f69aeb8314) [x64-mingw32]
  ```
* boom.rb 파일 생성후 실행

    ```shell
    boom.rb 
    
    print("Boom!")
    
    $ ruby boom.rbr
    ```


* To install sqlite3 gem

    ```shell
    ridk exec pacman -S mingw-w64-x86_64-sqlite3
    gem install sqlite3 --platform ruby
    ```

* To install nokogiri gem

    ```shell
    ridk exec pacman -S mingw-w64-x86_64-libxslt
    gem install nokogiri --platform ruby -- --use-system-libraries
    ```

[RubyMine][3]

[1]:https://www.ruby-lang.org/ko/
[2]:https://www.jetbrains.com/help/ruby/installation-guide.html
[3]:/program/ruby/rubymine.html