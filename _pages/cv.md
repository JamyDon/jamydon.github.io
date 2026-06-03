---
layout: archive
title: "Curriculum Vitae"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

<p class="cv-actions"><a href="https://jamydon.github.io/files/CV.pdf" class="pub-link pub-link--cv"><i class="fa fa-download"></i>Download PDF</a> <span class="musing-item__date-badge"><i class="fa fa-calendar" aria-hidden="true"></i>&nbsp;Updated Apr 2026</span></p>

## Education

<div class="cv-list">
  {% include cv-entry.html date="2024 - 2027" title="M.S. (Academic) in Computer Science" meta="Peking University" detail="Advisor: Assoc. Prof. Yunfang Wu" %}
  {% include cv-entry.html date="2020 - 2024" title="B.S. in Computer Science" meta="Peking University" detail="GPA: 3.72/4.00" %}
</div>

## Publications

<h3 class="cv-subsection-title">Refereed Publications</h3>
{% assign refereed_pubs = site.data.publications | where: "cv_group", "refereed" | sort: "cv_order" %}
<div class="musings-list cv-publications-list">
{% for pub in refereed_pubs %}
  {% include cv-publication-single.html pub=pub %}
{% endfor %}
</div>

<h3 class="cv-subsection-title">Preprints</h3>
{% assign preprint_pubs = site.data.publications | where: "cv_group", "preprint" | sort: "cv_order" %}
<div class="musings-list cv-publications-list">
{% for pub in preprint_pubs %}
  {% include cv-publication-single.html pub=pub %}
{% endfor %}
</div>

<p class="cv-footnote">* Equal Contribution.</p>

## Research Experience

<div class="cv-list">
  {% include cv-entry.html date="2025 - Present" title="Reinforcement Fine-tuning of Language Models (LMs)" meta="Tencent & Peking University" detail="Advised by Dr. Weijie Liu & Assoc. Prof. Yunfang Wu." %}
  {% include cv-entry.html date="2024 - 2025" title="Real-time Knowledge Editing for LMs" meta="Peking University" detail="Advised by Assoc. Prof. Yunfang Wu." %}
  {% include cv-entry.html date="2023 - 2024" title="Prompting and In-context Learning (ICL) for LMs" meta="Peking University" detail="Advised by Assoc. Prof. Yunfang Wu." %}
  {% include cv-entry.html date="2022 - 2023" title="Grammatical Error Correction (GEC)" meta="Peking University" detail="Advised by Assoc. Prof. Yunfang Wu." %}
</div>

## Honors and Awards

<div class="cv-list cv-list--compact">
  {% include cv-entry.html date="2024" title="Outstanding Graduate" meta="Peking University" %}
  {% include cv-entry.html date="2023" title="Exceptional Award for Academic Innovation" meta="Peking University" %}
  {% include cv-entry.html date="2023" title="First prize" meta="The 12th CCF International Conference on Natural Language Processing and Chinese Computing (NLPCC 2023) Shared Task 1: Chinese Grammatical Error Correction" %}
  {% include cv-entry.html date="2022" title="Second place" meta="The 21st China National Conference on Computational Linguistics (CCL 2022) Shared Task Track 4: Multi-reference Multi-source Chinese Learner Text Correction" %}
</div>

## Teaching

<div class="cv-list cv-list--compact">
  {% include cv-entry.html date="Spring 2025" title="Teaching Assistant, Introduction to Computing (C)" meta="Peking University" detail="Instructor: Prof. Zhifang Sui & Assoc. Prof. Yunfang Wu" %}
</div>

## Standardized Tests

<div class="cv-score-grid">
  <div class="cv-score">
    <p class="cv-score__label">TOEFL iBT</p>
    <p class="cv-score__value">111</p>
    <p class="cv-score__detail">R: 30 | L: 28 | S: 23 | W: 30</p>
  </div>
  <div class="cv-score">
    <p class="cv-score__label">GRE General Test</p>
    <p class="cv-score__value">336</p>
    <p class="cv-score__detail">V: 166 | Q: 170 | AWA: 3.5</p>
  </div>
</div>
