---
title: moon yongho test
author: WooYou
date: 2022-03-31
category: [rudy, Jekyll]
layout: default
---

{{page.previous.title}}

<br/>
<br/>
<br/>
{% for collection in site.collections %}
collection.label : {{collection.label}}  
{% endfor %}  
<br/>
<br/>
{% for collection in site.collections %}
{% if collection.label == 'program' %}
{{collection.label}}<br/>
<pre>
{% for post in site[collection.label] %}
post.title : {{post.title}}
{% endfor %}
</pre>
{% endif %}
{% endfor %}
  
<br/>
<br/>
  
{% for collection in site.collections %}

{% if collection.label == 'program' %}
{{collection.label}}<br/>
{% for post in site[collection.label] %}
<br/>

<pre>
post.title : {{post.title}}
post.path : {{post.path}}
post.categories : {{post.categories}}
post.exclude_from_search : {{post.exclude_from_search}}
post.tags : {{post.tags}}
</pre>

{% endfor %}
{% endif %}
{% endfor %}
<br/>
<br/>


