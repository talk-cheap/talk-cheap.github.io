---
layout: page
title: "标签"
description: "点击任意标签可以快速找到相关内容"  
header-img: "img/green.png"  
---

<div>
	<!-- 标签云 -->
	<div id='tag_cloud' class="tags">
		{% for tag in site.tags %}
		<a href="#{{ tag[0] }}" title="{{ tag[0] }}" rel="{{ tag[1].size }}">{{ tag[0] }}</a>
		{% endfor %}
	</div>
	
	<!-- 标签列表 -->
	{% for tag in site.tags %}
	<div class="one-tag-list">
		<span class="fa fa-tag listing-seperator" id="{{ tag[0] }}">{{ tag[0] }}</span>
		{% for post in tag[1] %}
		 <div class="post-preview">
			<a href="{{ post.url | prepend: site.baseurl }}">
				<h2 class="post-title">            {{ post.title }}
				</h2>
				{% if post.subtitle %}
				<h3 class="post-subtitle">
					{{ post.subtitle }}
				</h3>
				{% endif %}
			</a>
			<p class="post-meta">{{ post.date | date:"%Y-%m-%d" }}</p>
		</div>
		<hr>
		{% endfor %}
	</div>
	{% endfor %}
</div>