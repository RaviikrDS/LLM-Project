# Project Proposal: Multilingual Ticket Classification System Using RAG and LLMs
**Project Proposal: Multilingual Ticket Classification System Using RAG and LLMs**

**Submitted by:** [Your Name]  
**Date:** [Insert Date]  

---

### 1. **Project Title**
**Intelligent Ticket Classification System for ServiceNow (Incident, RITM, Change Tickets)**

---

### 2. **Overview**
This project aims to develop a scalable and intelligent ticket classification system capable of handling multilingual (English and Spanish) ServiceNow tickets. The system will classify support tickets into categories and subcategories using a hybrid approach combining Retrieval-Augmented Generation (RAG) and Large Language Models (LLMs).

---

### 3. **Problem Statement**
ServiceNow tickets (Incidents, RITMs, and Change Requests) are often manually triaged and categorized, leading to:
- High manual effort
- Inconsistent classifications
- Slower resolution times

A multilingual, automated classifier can significantly reduce these inefficiencies.

---

### 4. **Solution Architecture**

**Key Components:**
- **Frontend UI**: Upload ticket dump (.csv/.xlsx), view classified results
- **FastAPI Backend**: Handles API, processing, and prediction
- **Embedding Engine**: Multilingual embedding model (e.g., MiniLM)
- **Vector Store**: FAISS/Chroma for retrieval of relevant historical examples
- **Keyword Dictionary Layer**: English + Spanish keywords per category/subcategory
- **LLM Inference Layer**: Generates predictions using retrieved examples + definitions

**Architecture Flow:**
1. Upload ticket (any type/language)
2. Detect language (English/Spanish)
3. Keyword filtering to narrow categories
4. Retrieve relevant historical examples from vector DB
5. Build prompt with context
6. Query LLM
7. Return category, subcategory, and confidence score

**Architecture Diagram:**
[Diagram Rendered in Document Below]

---

### 5. **Features & Capabilities**
- Multilingual support (English + Spanish)
- Supports Incident, RITM, and Change Tickets
- Hybrid RAG + Rule-based classification
- Confidence-based fallback to keyword logic
- Plug-and-play ticket-type modules

---

### 6. **Technology Stack**
- **Frontend**: Streamlit or React
- **Backend**: FastAPI (Python)
- **LLM**: GPT-4 / Mistral / LLaMA (based on use case)
- **Vector Store**: FAISS / Chroma
- **Embeddings**: Sentence Transformers (multilingual MiniLM)
- **Database**: PostgreSQL / SQLite
- **CI/CD**: GitHub Actions
- **Containerization**: Docker + Docker Compose

---

### 7. **Codebase Folder Structure**
[Code Tree Rendered in Document Below]

---

### 8. **Current Dataset Assets**
- 200K labeled Incident Tickets
- Keyword dictionary for 100+ categories/subcategories

These will be used to bootstrap RAG retrieval and guide prompt generation.

---

### 9. **Future Scope**
- Extend to additional ticket types: Problem, Task, HR, etc.
- Add support for other languages (e.g., Portuguese, French)
- Build feedback loop for human-in-the-loop correction
- Integrate with ServiceNow via APIs for real-time classification
- Create analytics dashboard for category trends
- Fine-tune LLM with internal ticket data for even higher accuracy

---

### 10. **Hardware Requirements for Server Deployment**
- **CPU**: 8+ cores (Intel Xeon or AMD Ryzen recommended)
- **RAM**: 32–64 GB (for large batch processing)
- **GPU**: (Optional) NVIDIA A10 / T4 / RTX 3090 for LLM inference locally
- **Disk**: 200 GB SSD minimum
- **Network**: 1 Gbps
- **OS**: Ubuntu 20.04+ or Amazon Linux 2

---

### 11. **Recommended Open-Source Models**

#### **Embedding Models (Multilingual)**
| Model | Language Support | Notes |
|-------|------------------|-------|
| `paraphrase-multilingual-MiniLM-L12-v2` | English, Spanish, 50+ | ✅ Fast and accurate, recommended |
| `distiluse-base-multilingual-cased-v2` | 15+ languages | Good balance |
| `LaBSE` | 100+ | Large, high-quality |

#### **LLMs for Inference (Multilingual)**
| Model | Size | GPU | Notes |
|-------|------|-----|-------|
| `Mistral-7B Instruct` | 7B | ✅ | Best open-source for English/Spanish |
| `LLaMA 3 8B Instruct` | 8B | ✅ | Meta's latest, great quality |
| `Mixtral 8x7B` | 45B | High-end GPU | Very powerful |
| `Phi-2 / Phi-3-mini` | Tiny | CPU-friendly | Lightweight fallback |

> Best combo: MiniLM + Mistral or LLaMA 3 for classification with RAG

---

### 12. **Security and Data Protection Considerations**
This project will ensure full compliance with enterprise security and privacy standards:
- ✅ Role-based access control (RBAC) for UI/API endpoints
- ✅ HTTPS for all communication (frontend ↔ backend ↔ vector DB)
- ✅ All data encrypted at rest and in transit
- ✅ No PII stored without masking (only metadata and anonymized text)
- ✅ Secure Docker images with vulnerability scanning
- ✅ API key/token-based access control for model inference
- ✅ LLM interactions logged and auditable for compliance
- ✅ Option to self-host models to avoid cloud data leakage
- ✅ Periodic security audits and dependency scans

---

### 13. **Conclusion**
This project provides a forward-compatible, modular solution for automated, multilingual ticket classification. It will reduce manual overhead, improve SLA compliance, support security governance, and serve as a foundation for broader ITSM automation.

---

**Approval:**  
**Manager Name:** ____________________  
**Signature:** ________________________  
**Date:** _____________________________

