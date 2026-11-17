<div align="center">

<img src="assets/header.svg" alt="Shashank R, AI / ML Engineer" width="100%" />

<br/>

[![Portfolio](https://img.shields.io/badge/PORTFOLIO-0b132b?style=for-the-badge&logo=vercel&logoColor=6FFFE9&labelColor=0b132b&color=1c2541)](https://shashank-portfolio-c46v.vercel.app)
[![LinkedIn](https://img.shields.io/badge/LINKEDIN-0b132b?style=for-the-badge&logo=linkedin&logoColor=6FFFE9&labelColor=0b132b&color=1c2541)](https://linkedin.com/in/shashank-r)
[![Email](https://img.shields.io/badge/EMAIL-0b132b?style=for-the-badge&logo=gmail&logoColor=6FFFE9&labelColor=0b132b&color=1c2541)](mailto:r8013938@gmail.com)
[![Elsevier](https://img.shields.io/badge/PUBLISHED-ELSEVIER%202026-0b132b?style=for-the-badge&logoColor=6FFFE9&labelColor=0b132b&color=1c2541)](#-research)

<br/>

<img src="assets/metrics.svg" alt="95.47% GCN accuracy, 0.943 macro F1, ~99% ViT accuracy, 1 published and 2 papers in review" width="100%" />

</div>

<br/>

<div align="center"><img src="assets/divider.svg" width="100%" alt="" /></div>

## `> whoami`

I'm a final-year B.Tech student in **AI & Data Science** at Saveetha Engineering College, Chennai, and an **AI Engineer Intern at Nexa Mobility**. I build models that exploit structure (graphs, image patches, embeddings) and wrap them in products people can actually use.

| | |
|:--|:--|
| **Right now** | Multi-agent LLM workflows that turn release changes into explainable, validated test selections |
| **Published** | Elsevier, *Measurement: Energy* (2026) |
| **Under review** | GNN respiratory classification, ViT 3D-print defect detection |
| **Open to** | Internships, research collaborations and ML engineering roles |

> **Reporting standard.** Every number here is one I measured. When the headline result and the cross-validated result disagree, I show both.

<div align="center"><img src="assets/divider.svg" width="100%" alt="" /></div>

## `> experience`

```mermaid
%%{init: {'theme':'base','themeVariables':{'cScale0':'#14214a','cScale1':'#1b2f5e','cScaleLabel0':'#e3ebf8','cScaleLabel1':'#e3ebf8','lineColor':'#6FFFE9','fontFamily':'ui-monospace, Menlo, Consolas, monospace'}}}%%
timeline
    2024 : Web Development Intern · Connect Infosystems, Chennai
         : Jun – Jul 2024
         : Responsive interfaces with HTML, CSS and JavaScript
    2026 : AI Engineer Intern · Nexa Mobility, Bangalore
         : LangGraph multi-agent test selection
         : Semantic retrieval with pgvector and HNSW
         : Evidence-linked traceability and validation
```

#### 2026 · AI Engineer Intern, Nexa Mobility

- Built an AI workflow that converts release requirements and software-change evidence into explainable, validated test selections.
- Designed a **LangGraph multi-agent system** with specialised agents for release analysis, dependency reasoning, ranking, gap suggestions, reporting and spreadsheet analysis.
- Implemented semantic retrieval over a structured test corpus with Sentence Transformers, pgvector/HNSW and cosine similarity, backed by deterministic ID and coverage validation.
- Added claim-to-test traceability, bounded retries, concurrency controls, and separate validation and approval states.

<details>
<summary><b>View the workflow</b></summary>

```mermaid
flowchart TB
    R([Requirements + change evidence]) --> G{{LangGraph orchestrator}}
    G --> A1[Release analysis]
    G --> A2[Dependency reasoning]
    G --> A3[Ranking]
    G --> A4[Gap suggestions]
    G --> A5[Reporting + spreadsheet analysis]
    S[(Test corpus<br/>pgvector · HNSW)] --> A3
    A1 --> V
    A2 --> V
    A3 --> V
    A4 --> V
    A5 --> V
    V[Deterministic ID + coverage validation] --> O([Approved selection<br/>claim-to-test traceability])
    style R fill:#0f1a3a,stroke:#6FFFE9,color:#e3ebf8
    style O fill:#0f1a3a,stroke:#b9a7ff,color:#e3ebf8
    style G fill:#14214a,stroke:#6FFFE9,color:#e3ebf8
    style S fill:#14214a,stroke:#3a506b,color:#e3ebf8
    style V fill:#14214a,stroke:#b9a7ff,color:#e3ebf8
```

</details>

#### Jun – Jul 2024 · Web Development Intern, Connect Infosystems

- Built responsive web interfaces with HTML, CSS and JavaScript and worked through frontend workflows and production deployment.

<div align="center"><img src="assets/divider.svg" width="100%" alt="" /></div>

## `> projects`

### 01 · Respiratory sounds as a graph

*A lung recording is not an isolated clip. What if neighbouring samples could inform each other?*

```mermaid
flowchart LR
    A([WAV audio]) --> B[76-d features<br/>MFCC · spectral · chroma · mel]
    B --> C[K-NN graph<br/>temporal connectivity]
    C --> D[4-layer GCN<br/>residual connections]
    D --> E([5 classes])
    style A fill:#0f1a3a,stroke:#6FFFE9,color:#e3ebf8
    style E fill:#0f1a3a,stroke:#b9a7ff,color:#e3ebf8
    style B fill:#14214a,stroke:#3a506b,color:#e3ebf8
    style C fill:#14214a,stroke:#3a506b,color:#e3ebf8
    style D fill:#14214a,stroke:#3a506b,color:#e3ebf8
```

**95.47%** test accuracy · **0.943** macro F1 · **91.00% ± 1.32%** 5-fold CV · 1,211 samples
Deployed as a React + Express + Flask app: upload a WAV, get a prediction in real time.

`PyTorch Geometric` · `Librosa` · `Flask` · `Express` · `React` | Manuscript under review | [Code →](https://github.com/Shashank2006offl/REPO-NAME)

<br/>

### 02 · Catching failed prints with a Vision Transformer

*Print defects are local texture failures, which is exactly what patch-based attention is good at.*

```mermaid
flowchart LR
    A([Frame]) --> B[Patch embedding]
    B --> C[Transformer encoder]
    C --> D([5 defect categories])
    A -. optional .-> E[Live webcam verdict]
    style A fill:#0f1a3a,stroke:#6FFFE9,color:#e3ebf8
    style D fill:#0f1a3a,stroke:#b9a7ff,color:#e3ebf8
    style B fill:#14214a,stroke:#3a506b,color:#e3ebf8
    style C fill:#14214a,stroke:#3a506b,color:#e3ebf8
    style E fill:#14214a,stroke:#3a506b,color:#e3ebf8
```

**~99%** test accuracy on a custom 1,000+ image dataset, shipped with a Flask interface and optional webcam capture.

`TensorFlow` · `Keras` · `OpenCV` · `Flask` | Manuscript under review | [Code →](https://github.com/Shashank2006offl/REPO-NAME)

<br/>

### 03 · LuminaRole.ai, a resume analyser

*One PDF in; ATS fit, salary estimate and coaching out.*

```mermaid
flowchart LR
    A([Resume PDF]) --> B[Parse + features]
    B --> C[ATS match score]
    B --> D[Salary prediction<br/>RandomForest]
    B --> E[AI coaching]
    F{{Firebase Auth<br/>Bearer token}} -.guards API.-> B
    style A fill:#0f1a3a,stroke:#6FFFE9,color:#e3ebf8
    style B fill:#14214a,stroke:#3a506b,color:#e3ebf8
    style C fill:#14214a,stroke:#b9a7ff,color:#e3ebf8
    style D fill:#14214a,stroke:#b9a7ff,color:#e3ebf8
    style E fill:#14214a,stroke:#b9a7ff,color:#e3ebf8
    style F fill:#0f1a3a,stroke:#3a506b,color:#8fa3c0
```

Salary model trained on Data Science job-market data; the API is protected with Firebase authentication.

`React` · `Flask` · `scikit-learn` · `Firebase` | [Code →](https://github.com/Shashank2006offl/REPO-NAME)

<div align="center"><img src="assets/divider.svg" width="100%" alt="" /></div>

## `> research`

| Status | Paper | Venue |
|:--|:--|:--|
| **Published** | *Adaptive AI Scheduling of Building HVAC to Charge Phase Change Thermal Batteries with Elevator Regenerative Braking Heat*, Rajagopal M., **Shashank R.** | *Measurement: Energy*, Elsevier, 2026 |
| In review | *GNN-Powered Respiratory Disease Detection* | Manuscript |
| In review | *3D Printer Defect Detection using Vision Transformers* | Manuscript |

<div align="center"><img src="assets/divider.svg" width="100%" alt="" /></div>

## `> stack`

| Area | Tools |
|:--|:--|
| **Languages** | ![Python](https://img.shields.io/badge/Python-0b132b?style=flat-square&logo=python&logoColor=6FFFE9) ![TypeScript](https://img.shields.io/badge/TypeScript-0b132b?style=flat-square&logo=typescript&logoColor=6FFFE9) ![JavaScript](https://img.shields.io/badge/JavaScript-0b132b?style=flat-square&logo=javascript&logoColor=6FFFE9) ![HTML/CSS](https://img.shields.io/badge/HTML%20%2F%20CSS-0b132b?style=flat-square&logo=html5&logoColor=6FFFE9) |
| **Deep learning** | ![PyTorch](https://img.shields.io/badge/PyTorch-0b132b?style=flat-square&logo=pytorch&logoColor=6FFFE9) ![PyTorch Geometric](https://img.shields.io/badge/PyTorch%20Geometric%20(GNNs)-0b132b?style=flat-square&logo=pytorch&logoColor=6FFFE9) ![TensorFlow](https://img.shields.io/badge/TensorFlow-0b132b?style=flat-square&logo=tensorflow&logoColor=6FFFE9) ![Keras](https://img.shields.io/badge/Keras-0b132b?style=flat-square&logo=keras&logoColor=6FFFE9) |
| **ML + data** | ![scikit-learn](https://img.shields.io/badge/scikit--learn-0b132b?style=flat-square&logo=scikitlearn&logoColor=6FFFE9) ![NumPy](https://img.shields.io/badge/NumPy-0b132b?style=flat-square&logo=numpy&logoColor=6FFFE9) ![Pandas](https://img.shields.io/badge/Pandas-0b132b?style=flat-square&logo=pandas&logoColor=6FFFE9) ![OpenCV](https://img.shields.io/badge/OpenCV-0b132b?style=flat-square&logo=opencv&logoColor=6FFFE9) ![Librosa](https://img.shields.io/badge/Librosa%20(audio)-0b132b?style=flat-square&logoColor=6FFFE9) |
| **GenAI + agents** | ![LangGraph](https://img.shields.io/badge/LangGraph-0b132b?style=flat-square&logoColor=6FFFE9) ![LangChain](https://img.shields.io/badge/LangChain-0b132b?style=flat-square&logo=langchain&logoColor=6FFFE9) ![RAG](https://img.shields.io/badge/RAG-0b132b?style=flat-square&logoColor=6FFFE9) ![Sentence Transformers](https://img.shields.io/badge/Sentence%20Transformers-0b132b?style=flat-square&logo=huggingface&logoColor=6FFFE9) |
| **Retrieval + data stores** | ![pgvector](https://img.shields.io/badge/pgvector%20%2B%20HNSW-0b132b?style=flat-square&logo=postgresql&logoColor=6FFFE9) ![Supabase](https://img.shields.io/badge/Supabase-0b132b?style=flat-square&logo=supabase&logoColor=6FFFE9) ![Firebase](https://img.shields.io/badge/Firebase-0b132b?style=flat-square&logo=firebase&logoColor=6FFFE9) |
| **Backend + frontend** | ![FastAPI](https://img.shields.io/badge/FastAPI-0b132b?style=flat-square&logo=fastapi&logoColor=6FFFE9) ![Flask](https://img.shields.io/badge/Flask-0b132b?style=flat-square&logo=flask&logoColor=6FFFE9) ![Express](https://img.shields.io/badge/Express-0b132b?style=flat-square&logo=express&logoColor=6FFFE9) ![React](https://img.shields.io/badge/React-0b132b?style=flat-square&logo=react&logoColor=6FFFE9) |
| **Tooling** | ![Git](https://img.shields.io/badge/Git-0b132b?style=flat-square&logo=git&logoColor=6FFFE9) ![GitHub](https://img.shields.io/badge/GitHub-0b132b?style=flat-square&logo=github&logoColor=6FFFE9) ![Vercel](https://img.shields.io/badge/Vercel-0b132b?style=flat-square&logo=vercel&logoColor=6FFFE9) |

<div align="center"><img src="assets/divider.svg" width="100%" alt="" /></div>

## `> education`

| | |
|:--|:--|
| **B.Tech, Artificial Intelligence & Data Science** | Saveetha Engineering College, Chennai · 2023 – 2027 |
| **Higher Secondary (CBSE, Science)** | 2021 – 2023 |
| **Coursework** | Machine Learning, Deep Learning, Graph Neural Networks, Computer Vision, Data Analytics, Statistics, Neural Networks |
| **Certifications** | Foundations and Core Concepts of PyTorch (Coursera) · Machine Learning 101 (GUVI) · Data Analytics Using Pandas (GUVI) |

<div align="center"><img src="assets/divider.svg" width="100%" alt="" /></div>

<div align="center">

### Have a hard modelling problem or a research idea?

[**Portfolio**](https://shashank-portfolio-c46v.vercel.app) &nbsp;·&nbsp; [**LinkedIn**](https://linkedin.com/in/shashank-r) &nbsp;·&nbsp; [**r8013938@gmail.com**](mailto:r8013938@gmail.com)

</div>
