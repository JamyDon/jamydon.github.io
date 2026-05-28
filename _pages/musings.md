---
layout: archive
title: "Musings"
permalink: /musings/
author_profile: true
---

{% include base_path %}

<div class="musings-list">
{% for post in site.musings reversed %}
  {% include musing-single.html %}
{% endfor %}
</div>
