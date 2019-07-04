---
title: "My Blog"
excerpt: "The place I post all the stuff I write about"
sitemap: true
permalink: /blog.html
---

{{ content }}

<h3 class="archive__subtitle">{{ site.data.ui-text[site.locale].recent_posts | default: "Recent Posts" }}</h3>

{% for post in paginator.posts %}
  {% include archive-single.html %}
{% endfor %}

{% include paginator.html %}
