<div align="center">

<img src="https://capsule-render.vercel.app/api?type=cylinder&color=0:0b132b,50:1c2541,100:3a506b&height=230&section=header&text=LAB%20NOTEBOOK&fontSize=64&fontColor=e0fbfc&animation=twinkling&fontAlignY=40&desc=Shashank%20R%20%C2%B7%20experiments%20in%20learning%20from%20signals%2C%20structure%20and%20language&descAlignY=64&descSize=16" width="100%" alt="Lab Notebook banner" />

<a href="https://git.io/typing-svg"><img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=500&size=19&pause=1100&color=6FFFE9&center=true&vCenter=true&width=760&lines=Hypothesis%3A+a+lung+is+a+graph.;Hypothesis%3A+a+failing+print+looks+different+in+patches.;Hypothesis%3A+a+resume+is+a+signal+worth+scoring.;Method%3A+build+it%2C+measure+it%2C+report+it+honestly." alt="Typing animation" /></a>

<br/>

[![Portfolio](https://img.shields.io/badge/portfolio-open-3a506b?style=flat-square)](https://shashank-portfolio-c46v.vercel.app)
[![LinkedIn](https://img.shields.io/badge/linkedin-shashank--r-3a506b?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/shashank-r)
[![Mail](https://img.shields.io/badge/mail-get%20in%20touch-3a506b?style=flat-square&logo=gmail&logoColor=white)](mailto:r8013938@gmail.com)
[![Elsevier](https://img.shields.io/badge/peer--reviewed-Elsevier%202026-3a506b?style=flat-square)](#peer-reviewed-output)

</div>

---

## Abstract

```
INVESTIGATOR   Shashank R
AFFILIATION    Saveetha Engineering College, Chennai   (B.Tech AI & Data Science, 2023-2027)
FIELD NOTES    graph neural networks / vision transformers / retrieval / agentic systems
STANDARD       every number reported here is one I measured and can reproduce
STATUS         active. published once, two manuscripts in review, more experiments running.
```

This notebook is a record of what I have built, why, and how well it worked. Entries follow one format: a hypothesis, a method, and a result, with the result reported as measured.

---

## Index of experiments

| ID | Title | Instrument | Result |
|---|---|---|---|
| [EXP-001](#exp-001--is-a-lung-a-graph) | Is a lung a graph? | GCN, PyTorch Geometric | 95.47% test accuracy |
| [EXP-002](#exp-002--can-a-transformer-see-a-failing-print) | Can a transformer see a failing print? | Vision Transformer | approx. 99% test accuracy |
| [EXP-003](#exp-003--can-a-resume-be-scored-like-a-signal) | Can a resume be scored like a signal? | Random Forest, Flask, Firebase | working end-to-end platform |

---

## EXP-001 &mdash; Is a lung a graph?

> **Hypothesis.** Respiratory sounds carry structure that isolated-clip classifiers throw away. Connecting similar samples into a graph should let a network use it.

```
 .wav --> 76-d features --> K-NN graph --> GCN x4 (residual) --> 5 classes
          MFCC                 temporal
          spectral             connectivity
          chroma
          mel spectrogram
```

**Method.** A 76-dimensional feature vector per sample, K-NN graph construction for temporal connectivity, and a 4-layer GCN with residual connections.

**Result.**

```
test accuracy         95.47 %
macro F1               0.943
5-fold CV accuracy    91.00 % +/- 1.32 %
samples               1,211
```

The cross-validation figure is lower than the headline test accuracy, and I report both on purpose. Deployed as a React + Express + Flask app: drop in a WAV file, get a prediction in real time.

`PyTorch Geometric` `Librosa` `Flask` `Express` `React` &nbsp;|&nbsp; Manuscript under review &nbsp;|&nbsp; Code: `github.com/Shashank2006offl/<repo-name>`

---

## EXP-002 &mdash; Can a transformer see a failing print?

> **Hypothesis.** Print defects are local texture failures. A Vision Transformer, which reasons over image patches, should separate them reliably.

```
 frame --> patches --> transformer encoder --> 5 defect categories
                                                   |
                                  webcam capture --+--> live verdict
```

**Method.** A ViT pipeline trained on a custom dataset of 1,000+ images across 5 defect categories.

**Result.** Approximately 99% test accuracy, shipped with a Flask interface and optional webcam-based live capture.

`TensorFlow` `Keras` `OpenCV` `Flask` &nbsp;|&nbsp; Manuscript under review &nbsp;|&nbsp; Code: `github.com/Shashank2006offl/<repo-name>`

---

## EXP-003 &mdash; Can a resume be scored like a signal?

> **Hypothesis.** One PDF holds enough signal to estimate ATS fit, likely salary, and what to fix.

```
 PDF --> parse --> features --+--> ATS match score
                              +--> salary prediction (Random Forest)
                              +--> AI resume coaching
          Firebase auth + Bearer Token verification guards the API
```

**Method.** An end-to-end career analytics platform. The salary model is a RandomForestRegressor trained on Data Science job-market data.

**Result.** A working platform from a single upload to actionable feedback.

`React` `Flask` `scikit-learn` `Firebase` &nbsp;|&nbsp; Code: `github.com/Shashank2006offl/<repo-name>`

---

## Peer-reviewed output

| Status | Paper | Venue |
|---|---|---|
| Published | *Adaptive AI Scheduling of Building HVAC to Charge Phase Change Thermal Batteries with Elevator Regenerative Braking Heat* (Rajagopal M., **Shashank R.**) | *Measurement: Energy*, Elsevier, 2026 |
| In review | *GNN-Powered Respiratory Disease Detection* | manuscript |
| In review | *3D Printer Defect Detection using Vision Transformers* | manuscript |

---

## Instruments

```python
bench = {
    "models":     ["GNN", "CNN", "ViT", "RandomForest"],
    "frameworks": ["PyTorch", "PyTorch Geometric", "TensorFlow", "Keras", "scikit-learn"],
    "genai":      ["RAG", "LangGraph", "LangChain", "multi-agent systems", "LLM APIs"],
    "retrieval":  ["pgvector", "HNSW", "Sentence Transformers", "Supabase"],
    "services":   ["FastAPI", "Flask", "Express"],
    "interfaces": ["React", "TypeScript", "HTML", "CSS", "JavaScript"],
    "data":       ["NumPy", "Pandas", "Librosa", "OpenCV"],
}
```

<div align="center">

![Python](https://img.shields.io/badge/-Python-1c2541?style=flat-square&logo=python&logoColor=6FFFE9)
![PyTorch](https://img.shields.io/badge/-PyTorch-1c2541?style=flat-square&logo=pytorch&logoColor=6FFFE9)
![TensorFlow](https://img.shields.io/badge/-TensorFlow-1c2541?style=flat-square&logo=tensorflow&logoColor=6FFFE9)
![scikit-learn](https://img.shields.io/badge/-scikit--learn-1c2541?style=flat-square&logo=scikitlearn&logoColor=6FFFE9)
![LangChain](https://img.shields.io/badge/-LangChain-1c2541?style=flat-square&logo=langchain&logoColor=6FFFE9)
![FastAPI](https://img.shields.io/badge/-FastAPI-1c2541?style=flat-square&logo=fastapi&logoColor=6FFFE9)
![React](https://img.shields.io/badge/-React-1c2541?style=flat-square&logo=react&logoColor=6FFFE9)
![TypeScript](https://img.shields.io/badge/-TypeScript-1c2541?style=flat-square&logo=typescript&logoColor=6FFFE9)
![PostgreSQL](https://img.shields.io/badge/-pgvector-1c2541?style=flat-square&logo=postgresql&logoColor=6FFFE9)

</div>

---

## Lab log

```
2021-2023     Higher Secondary (CBSE, Science)
2023          Joined Saveetha Engineering College, AI & Data Science
2024 Jun-Jul  Web Development Intern, Connect Infosystems, Chennai
2026          First peer-reviewed paper published (Elsevier)
2026          AI Engineer Intern, Nexa Mobility
2027          Expected graduation
```

Coursework: Machine Learning, Deep Learning, Graph Neural Networks, Computer Vision, Data Analytics, Statistics, Neural Networks.
Certifications: Foundations and Core Concepts of PyTorch (Coursera), Machine Learning 101 and Data Analytics Using Pandas (GUVI).

---

## Activity, as a snake would see it

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Shashank2006offl/Shashank2006offl/output/github-contribution-grid-snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Shashank2006offl/Shashank2006offl/output/github-contribution-grid-snake.svg" />
  <img alt="Contribution snake" src="https://raw.githubusercontent.com/Shashank2006offl/Shashank2006offl/output/github-contribution-grid-snake.svg" />
</picture>

<br/>

<img src="https://github-readme-stats.vercel.app/api?username=Shashank2006offl&show_icons=true&theme=midnight-purple&hide_border=true&bg_color=0b132b&title_color=6FFFE9&icon_color=6FFFE9&text_color=e0fbfc" height="165" alt="GitHub stats" />
<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Shashank2006offl&layout=compact&hide_border=true&bg_color=0b132b&title_color=6FFFE9&text_color=e0fbfc" height="165" alt="Top languages" />

</div>

---

<div align="center">

### Open to research collaborations, ML engineering roles, and problems worth a hypothesis.

[Portfolio](https://shashank-portfolio-c46v.vercel.app) &nbsp;|&nbsp; [LinkedIn](https://linkedin.com/in/shashank-r) &nbsp;|&nbsp; [Email](mailto:r8013938@gmail.com)

<img src="https://capsule-render.vercel.app/api?type=cylinder&color=0:3a506b,100:0b132b&height=80&section=footer" width="100%" alt="footer" />

</div>
