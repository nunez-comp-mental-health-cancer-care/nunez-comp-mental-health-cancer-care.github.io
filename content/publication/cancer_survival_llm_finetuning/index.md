---
title: "Investigating fine-tuning versus zero-shot learning for general large language models when predicting cancer survival from initial oncology consultation documents"

authors:
- T. Phaterpekar
- Z. Zeng
- Y. Mali
- Bonnie Leung
- Cheryl Ho
- Raymond T. Ng
- Alan T. Bates
- John-Jose Nunez

date: "2026-01-01T00:00:00Z"
doi: "10.1016/j.esmorw.2026.100703"

publishDate: "2026-01-01T00:00:00Z"

publication_types: ["2"]

publication: "ESMO Real World Data and Digital Oncology"
publication_short: "ESMO Real World Data Digit Oncol"

abstract: "Unstructured oncology consultation notes contain rich clinical information that may support survival prediction. Open-weight large language models (LLMs) can utilize these notes with zero-shot inference or fine-tuning, but their relative value for this setting remains unclear. This study evaluates open-weight LLMs for predicting 60-month survival from initial oncology consultation notes, comparing zero-shot performance, performance after fine-tuning, and smaller NLP models trained on the same dataset. Using Meta's Llama models on a dataset of 59,800 patients, zero-shot performance was limited while fine-tuning meaningfully improved performance: Llama-2-13B achieved balanced accuracy 0.842, weighted F1 0.846, AUC 0.905. Performance was numerically similar to smaller models trained on the same task. For predicting 60-month survival, fine-tuning open-weight LLMs improves performance over zero-shot use, but does not consistently outperform smaller language models."

featured: true

tags:
  - Machine Learning
  - Large Language Models
  - Cancer
  - Survival Prediction
  - Oncology
  - Natural Language Processing
  - Fine-tuning

url_pdf: ''
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: 'https://www.sciencedirect.com/science/article/pii/S2949820126000226'
url_video: ''

image:
  caption: ''
  focal_point: ""
  preview_only: false

---

This study investigates whether fine-tuning open-weight large language models (LLMs) improves cancer survival prediction from oncology consultation notes compared to zero-shot approaches. Using Meta's Llama models on 59,800 patient records from BC Cancer, fine-tuning consistently improved performance over zero-shot inference, but did not outperform smaller task-specific NLP models. The findings suggest both approaches merit continued investigation, with the best choice depending on clinical context and practical constraints such as hardware, privacy, and deployment feasibility.
