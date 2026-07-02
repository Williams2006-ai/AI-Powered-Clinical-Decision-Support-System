# AI-Powered Clinical Decision Support System (CDSS)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Compliance: HIPAA](https://img.shields.io/badge/Compliance-HIPAA%20Compliant-blue.svg)](#security--hipaa-compliance)
[![CI/CD: GitHub Actions](https://img.shields.io/badge/CI%2FCD-GitHub%20Actions-orange.svg)](#cicd--deployment)

An enterprise-grade, multimodal clinical decision support platform designed to assist healthcare providers in diagnosing diseases and curating treatment plans. The system securely ingests, normalizes, and analyzes fragmented patient data—including Electronic Health Records (EHRs), high-resolution medical imaging (DICOM), and unstructured clinical notes—using state-of-the-art deep learning architectures.

---

## 💡 Business Problem & Value

### The Challenge
Modern healthcare providers grapple with severe **diagnostic errors**, **time-consuming workflows**, and massive **data overload** spread across highly fragmented legacy systems.

### Our Solution
* **Reduces Misdiagnosis:** Enhances diagnostic accuracy via multi-modal AI verification, directly saving costs and improving patient outcomes.
* **Accelerates Decision-Making:** Unifies disjointed data channels into a single timeline, significantly optimizing hospital operational throughput.
* **Data-Driven Treatment Pathways:** Empowers clinicians with objective, evidence-based data insights backed by Explainable AI (XAI).

---

## 🧠 Core AI/ML Architecture

The core intelligence layer processes complex medical information through specialized pipelines:
* **Computer Vision:** Deep Convolutional Neural Networks (CNNs) process medical imaging data (X-rays, MRIs, CT scans) to isolate anomalies.
* **Natural Language Processing:** Transformer-based models evaluate unstructured clinical notes to extract symptoms, history, and codify terms.
* **Multimodal Learning Layer:** Late-fusion architectures synthesize imaging embeddings, text embeddings, and structured EHR metrics into unified risk profiles.
* **Explainable AI (XAI):** Built-in **SHAP** and **LIME** engines generate mathematical feature attribution graphs, ensuring clinicians can inspect and trust every model output.

---

## 🧰 Technology Stack

| Layer | Technologies Used |
| :--- | :--- |
| **Frontend** | React.js, TypeScript, Tailwind CSS / Material UI, Chart.js / D3.js |
| **Backend** | Python (FastAPI), Node.js (API Gateway abstraction), REST & GraphQL |
| **AI / ML** | PyTorch, TensorFlow, Hugging Face Transformers, OpenCV, Scikit-learn |
| **Data Engineering** | Apache Spark, Apache Airflow, Apache Kafka (Real-time streams) |
| **Databases** | PostgreSQL (Structured data), MongoDB (Unstructured data), Redis (Cache/Broker) |
| **DevOps & Cloud** | AWS (S3, EC2, SageMaker), Docker, Kubernetes (EKS), GitHub Actions |

---

## 📂 Repository File Structure

This platform utilizes a **Monorepo** design to keep services unified while maintaining strict operational boundaries between client applications, core servers, and data processing runtimes.

```text
ai-cdss-platform/
├── .github/workflows/          # Automated CI/CD pipelines & compliance scanners
├── apps/
│   ├── frontend/               # React client app written in strict TypeScript
│   │   ├── src/
│   │   │   ├── components/     # Reusable UI systems (Viewers, Modals, Forms)
│   │   │   ├── features/       # Feature-slice modular layout (auth, patient, dashboard)
│   │   │   └── services/       # GraphQL and API network layers
│   │   └── Dockerfile
│   │
│   ├── backend/                # Core Python FastAPI service layer
│   │   ├── app/
│   │   │   ├── api/            # Versioned API route architectures (v1/v2)
│   │   │   ├── core/           # Security, OAuth2 handles, cryptographic compliance engines
│   │   │   └── models/         # Database models (PostgreSQL & MongoDB collections)
│   │   └── Dockerfile
│   │
│   └── ai-engine/              # Machine learning runtimes & engineering processes
│       ├── data_pipelines/     # Airflow DAGs and Spark data cluster orchestration
│       ├── inference/          # FastAPI model serving endpoints & SageMaker bindings
│       └── notebooks/          # Explanatory research, EDA, and model validation scripts
│
├── infra/                      # Infrastructure-as-Code & local runtime environments
│   ├── terraform/              # Declarative cloud blueprints (AWS EKS, RDS, S3)
│   └── docker-compose.yml      # Local single-command stack orchestrator
└── README.md                   # Core project documentation
