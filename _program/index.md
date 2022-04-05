---
title: Git
author: WooYou
date: 2022-03-30
category: git
layout: default
---
디렉토리
------
{% for depth1 in site.data.navigation %}
{% if depth1.code == 'program'%}
{% for depth2 in depth1.subMenu %}
* [{{depth2.name}}]({{depth2.link}})
{% endfor %}
{% endif %} 
{% endfor %}  


블러그
---------
* [조대협][id]

[id]: https://bcho.tistory.com/ "조대협"
