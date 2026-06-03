---
permalink: /
title: "About Me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

Hi, I'm Chenming Tang – a Master's student in [Computer Science](https://cs.pku.edu.cn/English/Home.htm) at [Peking University](https://english.pku.edu.cn/), advised by Prof. [Yunfang Wu](https://cs.pku.edu.cn/info/1083/1705.htm). Before that, I got my Bachelor's degree at [School of EECS](http://eecs.pku.edu.cn/en/), [Peking University](https://english.pku.edu.cn/). My research spans various facets of NLP and generally aims to make LMs better assistants for human in various aspects.

<p class="research-chips" aria-label="Research interests"><span class="research-chip">Agentic reinforcement learning</span><span class="research-chip">LM memory</span><span class="research-chip">LM personalization</span><span class="research-chip">Financial LMs</span></p>

<div class="profile-note">
  <p><strong>I’m actively seeking a PhD opportunity for Fall 2027 (US, SG and HK preferred), and I’d love to connect with like-minded academic researchers.</strong></p>
  <p>For an in-depth overview of my background and accomplishments, please feel free to check out <span class="profile-note__actions"><a href="http://jamydon.github.io/cv/" class="pub-link pub-link--cv"><i class="fa fa-file-lines"></i>CV</a> <a href="http://jamydon.github.io/contact/" class="pub-link pub-link--contact"><i class="fa fa-envelope"></i>Contact</a></span></p>
</div>

## Education

<div class="cv-list cv-list--compact">
  {% include cv-entry.html date="2024 - Present" title="M.S. (Academic) in Computer Science" meta="Peking University" inline_meta=true inline_meta_prominent=true %}
  {% include cv-entry.html date="2020 - 2024" title="B.S. in Computer Science" meta="Peking University" inline_meta=true inline_meta_prominent=true %}
</div>

## Selected Publications

<p class="section-actions"><a href="https://scholar.google.com/citations?user=qQ6PBaMAAAAJ" class="pub-link pub-link--scholar"><i class="fa fa-graduation-cap"></i>Google Scholar</a> <a href="https://jamydon.github.io/publications/" class="pub-link pub-link--scholar"><i class="fa fa-list"></i>Full List</a></p>

{% assign selected_pubs = site.data.publications | where: "home_selected", true | sort: "home_order" %}
<div class="musings-list home-publications">
{% for pub in selected_pubs %}
  {% include publication-data-single.html pub=pub %}
{% endfor %}
</div>

## Internship

<div class="cv-list cv-list--compact">
  {% include cv-entry.html date="Jul 2025 - Present" title="Research Intern" meta="Tencent HY" inline_meta=true inline_meta_prominent=true %}
</div>

## Honors and Awards

<div class="cv-list cv-list--compact">
  {% include cv-entry.html date="2024" title="Outstanding Graduate" meta="Peking University" inline_meta=true inline_meta_plain=true %}
  {% include cv-entry.html date="2023" title="Exceptional Award for Academic Innovation" meta="Peking University" inline_meta=true inline_meta_plain=true %}
  {% include cv-entry.html date="2023" title="Merit Student" meta="Peking University" inline_meta=true inline_meta_plain=true %}
  {% include cv-entry.html date="2023" title="First prize" meta="NLPCC 2023 Shared Task 1 (Chinese Grammatical Error Correction)" inline_meta=true inline_meta_plain=true %}
  {% include cv-entry.html date="2022" title="Second place" meta="CCL 2022 Shared Task 4 (Multi-reference Multi-source Chinese Learner Text Correction)" inline_meta=true inline_meta_plain=true %}
</div>

## /etc

<div class="profile-note profile-note--quiet">
  <p>I aim to pursue a career in <strong>academia</strong> rather than industry. I prioritize intellectual freedom over short-term commercial outcomes. I also place a high value on <strong>work-life balance</strong>, as I believe sustainable pace and well-being are essential for durable, creative, and thoughtful research.</p>
  <p>When I am not doing research, I enjoy investment, practice the art of <a href="https://en.wikipedia.org/wiki/Chinese_calligraphy">Chinese calligraphy</a>, and listen to music by <a href="https://en.wikipedia.org/wiki/Antonio_Vivaldi">Vivaldi</a>, <a href="https://en.wikipedia.org/wiki/Johann_Sebastian_Bach">Bach</a>, <a href="https://en.wikipedia.org/wiki/Johannes_Brahms">Brahms</a>, <a href="https://en.wikipedia.org/wiki/Sergei_Rachmaninoff">Rachmaninoff</a>, <em>et al.</em> One of my favorite music works these months is <a href="https://en.wikipedia.org/wiki/Symphony_No._4_(Brahms)">Symphony No. 4 by Brahms</a>.</p>
</div>
