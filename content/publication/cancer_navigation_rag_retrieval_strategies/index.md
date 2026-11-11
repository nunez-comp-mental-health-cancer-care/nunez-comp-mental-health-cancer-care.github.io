---
title: "Limits of Single-Pass Retrieval-Augmented Generation for AI-Powered Cancer Care Navigation: A Comparison of Retrieval Strategies"

authors:
- Emrul Hasan
- Yuci Zhang
- Olivia Cook
- Andrew Loe
- Matthew Sha
- Leah T’ien
- Margaret Ng
- Chris Rauscher
- Srinivas Raman
- Jacqueline L. Bender
- Raymond T. Ng
- Alan Bates
- John-Jose Nunez

date: "2026-09-04T00:00:00Z"
doi: "10.64898/2026.08.31.26361774"

publishDate: "2026-09-04T00:00:00Z"

publication_types: ["3"]

publication: "medRxiv (preprint)"
publication_short: "medRxiv"

abstract: "### Background

 People affected by cancer often face difficulty finding relevant clinical, psychological, and practical support services. AI-powered navigation assistants may improve access to these resources, but their retrieval performance must be reliable.

### Objective

 To develop a single-pass retrieval-augmented generation assistant for cancer-care navigation and compare the retrieval strategies, including their robustness to reworded questions.

### Methods

 We created a database of 853 cancer-support resources reviewed by librarians, clinicians, researchers, and patient partners. We evaluated the system using 100 questions derived from questions submitted by patients. We compared keyword-based, semantic, and hybrid retrieval using Precision@K, Hit@K, and nDCG@K. The best-performing configuration was then tested using semantically equivalent rewordings of the original questions.

### Results

 Keyword-based retrieval performed poorly, achieving a P@1 of 25.0% and Hit@5 of 43.0%. Semantic retrieval improved these results to 58.0% and 86.0%, respectively. The best hybrid configuration achieved a P@1 of 64.0%, Hit@5 of 90.0%, and nDCG@5 of 51.0%. Performance remained relatively stable when the questions were reworded, with a P@1 of 61.0%, Hit@5 of 88.0%, and nDCG@5 of 46.1%.

### Conclusions

 Hybrid retrieval performed best and remained relatively stable when questions were reworded. However, its limited ability to rank a relevant resource first highlights the limitations of single-pass retrieval for patient-facing cancer navigation. Future work will explore metadata filtering and a multi-agent architecture to improve retrieval reliability."

featured: false

tags:
  - Cancer Care Navigation
  - Retrieval-Augmented Generation
  - Large Language Models
  - Chatbot

url_pdf: ''
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: 'https://doi.org/10.64898/2026.08.31.26361774'
url_video: ''

image:
  caption: ''
  focal_point: ""
  preview_only: false

---
