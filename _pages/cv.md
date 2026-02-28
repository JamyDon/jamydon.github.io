---
layout: archive
title: "Curriculum Vitae"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

Education
======
* M.S. in Computer Science, Peking University, 2024 - 2027 (expected)
  * Advisor: Assoc. Prof. Yunfang Wu
* B.S. in Computer Science, Peking University, 2020 - 2024
  * GPA: 3.72/4.00

Publications
======
<!-- <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul> -->

**Rendered Publications**

* [Large Language Models Might Not Care What You Are Saying: Prompt Format Beats Descriptions](https://aclanthology.org/2025.findings-emnlp.3/)
  * **Chenming Tang\***, Zhixiang Wang\*, Hao Sun, Yunfang Wu
  * **Findings of EMNLP 2025** (_Findings of the Association for Computational Linguistics: EMNLP 2025_)

* [SCOI: Syntax-augmented Coverage-based In-context Example Selection for Machine Translation](https://aclanthology.org/2024.emnlp-main.555/)
  * **Chenming Tang**, Zhixiang Wang, Yunfang Wu
  * **EMNLP 2024** (_Proceedings of the 2024 Conference on Empirical Methods in Natural Language Processing, 2024_)
  
* [Ungrammatical-syntax-based In-context Example Selection for Grammatical Error Correction](https://aclanthology.org/2024.naacl-long.99/)
  * **Chenming Tang**, Fanyi Qu, Yunfang Wu
  * **NAACL 2024** (_Proceedings of the 2024 Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies (Volume 1: Long Papers), 2024_)
  
* [Are Pre-trained Language Models Useful for Model Ensemble in Chinese Grammatical Error Correction?](https://aclanthology.org/2023.acl-short.77/)
  * **Chenming Tang**, Xiuyu Wu, Yunfang Wu
  * **ACL 2023** (_Proceedings of the 61st Annual Meeting of the Association for Computational Linguistics (Volume 2: Short Papers), 2023_)

**Preprints**

* [Do Not Step Into the Same River Twice: Learning to Reason from Trial and Error](https://arxiv.org/abs/2510.26109)
  * **Chenming Tang**, Hsiu-Yuan Huang, Weijie Liu, Clive Bai, Saiyong Yang, Yunfang Wu
  * _arXiv preprint arXiv:2510.26109_
 
* [Aligning Language Models with Real-time Knowledge Editing](https://arxiv.org/abs/2508.01302)
  * **Chenming Tang**, Yutong Yang, Kexue Wang, Yunfang Wu. 2025
  * _arXiv preprint arXiv:2508.01302_

* [Think Outside the Policy: In-Context Steered Policy Optimization](https://arxiv.org/abs/2510.26519)
  * Hsiu-Yuan Huang\*, **Chenming Tang\***, Weijie Liu, Clive Bai, Saiyong Yang, Yunfang Wu
  * _arXiv preprint arXiv:2510.26519_
 
* [ORBIT: On-policy Exploration-Exploitation for Controllable Multi-Budget Reasoning](https://arxiv.org/abs/2601.08310)
  * Kun Liang, Clive Bai, Xin Xu, **Chenming Tang**, Sanwoo Lee, Weijie Liu, Saiyong Yang, Yunfang Wu
  * _arXiv preprint arXiv:2601.08310_

* [Lost in the Passage: Passage-level In-context Learning Does Not Necessarily Need a "Passage"](https://arxiv.org/abs/2502.10634)
  * Hao Sun, **Chenming Tang**, Gengyang Li, Yunfang Wu
  * _arXiv preprint arXiv:2502.10634_
  
* [Evaluating the Capability of Large-scale Language Models on Chinese Grammatical Error Correction Task](https://arxiv.org/abs/2307.03972)
  * Fanyi Qu, **Chenming Tang**, Yunfang Wu
  * _arXiv preprint arXiv:2307.03972_

\* Equal Contribution.

Research Experience
======
* **Reinforcement Fine-tuning of Language Models (LMs)**, Tencent & Peking University, 2025 - Present.
  * Advised by Dr. Weijie Liu & Assoc. Prof. Yunfang Wu.
  * Formulated exploration stagnation as a key challenge for on-policy reinforcement fine-tuning of LMs.
  * Designed LTE, a mistake-hinting mechanism that mitigates exploration stagnation and enhances both exploitation and exploration, significantly boosting the performance of post-trained LMs (under review).

* **Real-time Knowledge Editing for LMs**, Peking University, 2024 - 2025.
  * Advised by Assoc. Prof. Yunfang Wu.
  * Pinpointed key gaps of evaluation and approaches in real-time and real-world knowledge editing.
  * Led the development of CRAFT, a dynamic dataset for real-time and real-world knowledge editing.
  * Proposed KEDAS, a novel self-adaptive paradigm of aligning LMs with real-time and real-world knowledge editing, exhibiting superior performance on both KEDAS and mainstream benchmarks compared to existing methods (under review).
  * Mentored two students on dataset construction, baseline reproduction, and manuscript development.

* **Prompting and In-context Learning (ICL) for LMs**, Peking University, 2023 - 2024.
  * Advised by Assoc. Prof. Yunfang Wu.
  * Proposed the use of syntactic similarity for in-context demonstration selection in grammatical error correction (GEC), establishing its superiority over traditional semantic-based methods (NAACL 2024).
  * Introduced a novel ICL demonstration selection mechanism for machine learning that combines syntactic coverage and semantic overlap, yielding leading performance across six translation directions (EMNLP 2024).
  * Demonstrated a proper prompt format without well-designed descriptions is effective enough to achieve promising performance across 10 NLP tasks. Collaborated with and advised a student in data pre-processing and experiments on a broad range of tasks (EMNLP 2025 Findings).

* **Grammatical Error Correction (GEC)**, Peking University, 2022 - 2023.
  * Advised by Assoc. Prof. Yunfang Wu.
  * Developed three ensemble algorithms leveraging pre-trained LMs and demonstrated perplexity does not necessarily correlate with GEC performance.
  * Highlighted that human-annotated ground truth references in GEC datasets are far from sufficient and there existed a gap between a grammatically correct sentence and an idiomatic one (ACL 2023 Short Paper).
  * Won second place of CCL 2022 Shared Task 4 (Multi-reference Multi-source Chinese Learner Text Correction) and first prize of NLPCC 2023 Shared Task 1 (Chinese Grammatical Error Correction).
  
<!-- Talks
======
  <ul>{% for post in site.talks reversed %}
    {% include archive-single-talk-cv.html  %}
  {% endfor %}</ul> -->
  
<!-- Teaching
======
  <ul>{% for post in site.teaching reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul> -->
  
<!-- Service and leadership
======
* Currently signed in to 43 different slack teams -->

Honors and Awards
======
* **Outstanding Graduate**, Peking University, 2024.
* **Exceptional Award for Academic Innovation**, Peking University, 2023.
* **First prize**, the 12th CCF International Conference on Natural Language Processing and Chinese Computing (NLPCC 2023) Shared Task 1: "Chinese Grammatical Error Correction", 2023.
* **Second place**, the 21st China National Conference on Computational Linguistics (CCL 2022) Shared Task Track 4: "Multi-reference Multi-source Chinese Learner Text Correction", 2022.

Teaching
======
* Teaching Assistant, Introduction to Computing (C), Peking University, Spring 2025.
  * Instructor: Prof. Zhifang Sui & Assoc. Prof. Yunfang Wu
 
Standardized Tests
======
* **TOEFL iBT:** 111 (R:30, L:28, S:23, W:30)
* **GRE General Test:** 336 (V:166, Q:170, AWA:3.5)
