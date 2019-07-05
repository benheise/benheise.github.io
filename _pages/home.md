---
layout: splash
permalink: /
header:
  overlay_color: "#5e616c"
  overlay_image: /images/gcl_blurred2.png
excerpt: >
  A hacker, podcaster, and information security professional.
feature_row:
  - image_path: /images/mm-customizable-feature.png
    alt: "projects"
    title: "Projects"
    excerpt: "Check out some of the recent projects I've been working on in my spare time."
    url: "/projects/"
    btn_class: "btn--primary"
    btn_label: "Learn more"
  - image_path: /images/mm-responsive-feature.png
    alt: "services"
    title: "Services Offered"
    excerpt: "There's a variety of offensive security services, and here are some of the ones I can help you with."
    url: "/services/"
    btn_class: "btn--primary"
    btn_label: "Learn more"
  - image_path: /images/mm-free-feature.png
    alt: "posts"
    title: "CTFs"
    excerpt: "Check out the Capture The Flags and Cyber Exercises I've participated in."
    url: "/capturetheflag/"
    btn_class: "btn--primary"
    btn_label: "Learn more"      
---

-----
<center>

Our Live Stream

{% include twitchPlayer.html %}
</center>

-----

{% include feature_row %}

## Blog Posts

<ul class="taxonomy__index">
  {% assign postsInYear = site.posts | group_by_exp: 'post', 'post.date | date: "%Y"' %}
  {% for year in postsInYear %}
    <li>
      <a href="#{{ year.name }}">
        <strong>{{ year.name }}</strong> <span class="taxonomy__count">{{ year.items | size }}</span>
      </a>
    </li>
  {% endfor %}
</ul>

{% assign postsByYear = site.posts | group_by_exp: 'post', 'post.date | date: "%Y"' %}
{% for year in postsByYear %}
  <section id="{{ year.name }}" class="taxonomy__section">
    <h2 class="archive__subtitle">{{ year.name }}</h2>
    <div class="entries-{{ page.entries_layout | default: 'list' }}">
      {% for post in year.items %}
        {% include archive-single.html type=page.entries_layout %}
      {% endfor %}
    </div>
    <a href="#page-title" class="back-to-top">{{ site.data.ui-text[site.locale].back_to_top | default: 'Back to Top' }} &uarr;</a>
  </section>
{% endfor %}