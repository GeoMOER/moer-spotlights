---
layout: splash
title: Course Units
permalink: /units.html
sidebar:
        nav: "units"

feature_row:
  - image_path: /assets/images/jekyll-logo.png
    alt: "Unit 1"
    title: "01 Dr. Jekyll & Ms Ruby"
    excerpt: "Introduction & Set up."
    url: "/unit01/unit01-01.html"
    btn_label: "Show me more"
    btn_class: "btn--danger"

---

# Overview of Course Units

{% for post in site.posts limit: 5 %}
  {% include archive-single.html %}
{% endfor %}

{% include feature_row id="intro" type="center" %}

{% include feature_row %}

---

<!---
your comment goes here
and here
{% include units_page %}
-->
