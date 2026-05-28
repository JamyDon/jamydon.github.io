---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if site.author.googlescholar %}
<p><a href="{{site.author.googlescholar}}" class="pub-link pub-link--scholar"><i class="fa fa-graduation-cap"></i>Google Scholar</a> <a href="https://www.semanticscholar.org/author/Chenming-Tang/2293892905" class="pub-link pub-link--scholar"><i class="fa fa-atom"></i>Semantic Scholar</a></p>
{% endif %}

{% include base_path %}

<div class="musings-list">
{% for pub in site.data.publications %}
  {% include publication-data-single.html pub=pub %}
{% endfor %}
</div>
