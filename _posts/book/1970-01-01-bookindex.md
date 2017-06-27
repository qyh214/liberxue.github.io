---
istop: true
layout: post
category: book
title: liberxue读过书|在读的书
keywords: 书籍,book,linberxue,目录
tags: 书籍,book, linberxue,目录
excerpt: 何其有幸。仅需短短几小时，至多几十个小时就能读完一本作家的心血结晶。感受他们的或磅礴思想、或悲欢离合，从文字中汲取养分与力量,感受他们的或磅礴思想、或悲欢离合，从文字中汲取养分与力量。
redirect_from:
  - /1970/01/bookindex/
---

科普是现实和功利主义的，科幻是感性和理想主义的，科普是知识的灌输，而科幻则是心灵的启迪。
 
 
从本质上说，金戒指和钻石戒指没有什么不同，都是出于炫耀意义的产物，所以他们怎么能衬托出谁比谁更高贵呢？真正的高贵可能是什么也不戴，却比那些戴满饰品的人更光彩夺目。
 
 
人间的贵有三种，一种是一眼就能看出的贵，这通常是因为其吃穿用度写满了昂贵的标签，这是富贵；一种是第一眼看不出贵，但过后就能感受出来的身份地位、教养学识，这是权贵；还有一种是看多少眼都还是那样耀眼，只因为其迷人的气质和思想，这是高贵.

{% capture site_tags %}{% for tag in site.tags %}{{ tag | first }}{% unless forloop.last %},{% endunless %}{% endfor %}{% endcapture %}
{% assign tags_list = site_tags | split:',' | sort %}

<ul class="entry-meta inline-list">
  {% for item in (0..site.tags.size) %}{% unless forloop.last %}
    {% capture this_word %}{{ tags_list[item] | strip_newlines }}{% endcapture %}
  	<li><a href="#{{ this_word }}" class="tag"><span class="term">{{ this_word }}</span> <span class="count">{{ site.tags[this_word].size }}</span></a></li>
  {% endunless %}{% endfor %}
</ul>

{% for item in (0..site.tags.size) %}{% unless forloop.last %}
  {% capture this_word %}{{ tags_list[item] | strip_newlines }}{% endcapture %}
	<article>
	<h2 id="{{ this_word }}" class="tag-heading">{{ this_word }}</h2>
		<ul>
    {% for post in site.tags[this_word] %}{% if post.title != null %}
      <li class="entry-title"><a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></li>
    {% endif %}{% endfor %}
		</ul>
	</article><!-- /.hentry -->
{% endunless %}{% endfor %}