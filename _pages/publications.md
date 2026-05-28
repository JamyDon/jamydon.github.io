---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if site.author.googlescholar %}
  <div class="wordwrap">You can also find my articles on <a href="{{site.author.googlescholar}}">my Google Scholar profile</a>.</div>
{% endif %}

{% include base_path %}

<div class="musings-list">
{% for post in site.publications reversed %}
  {% include publication-single.html %}
{% endfor %}
</div>

<script>
(function() {
  var iconMap = {
    "publication": "fa-file-text",
    "preprint": "fa-file-lines",
    "code": "fa-code"
  };
  var excerpts = document.querySelectorAll(".musing-item__excerpt");
  excerpts.forEach(function(el) {
    var links = el.querySelectorAll("a");
    links.forEach(function(link) {
      var text = link.textContent.trim().toLowerCase();
      if (iconMap[text]) {
        link.className = "pub-link pub-link--" + text;
        link.innerHTML = '<i class="fa ' + iconMap[text] + '"></i>' + link.textContent.trim();
      }
    });
    /* Remove | separators */
    var walker = document.createTreeWalker(el, NodeFilter.SHOW_TEXT, null, false);
    var textNodes = [];
    while (walker.nextNode()) { textNodes.push(walker.currentNode); }
    textNodes.forEach(function(node) {
      node.nodeValue = node.nodeValue.replace(/\s*\|\s*/g, " ");
    });
  });
})();
</script>
