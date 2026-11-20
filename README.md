<p align="center">
  <img width="100%" src="https://capsule-render.vercel.app/api?type=soft&height=190&color=0:E9DFF5,50:F6E3EA,100:E1ECF7&text=L%C3%AA%20H%E1%BA%A3i%20Ti%E1%BA%BFn&fontColor=4A3F5C&fontSize=46&fontAlignY=42&desc=Software%20Engineer%20%C2%B7%20Distributed%20Systems%20in%20Education&descSize=17&descAlignY=66&descAlign=50" alt="Lê Hải Tiến" />
</p>

<p align="center">
  <em>“Simplicity is prerequisite for reliability.”</em><br/>
  <sub>— Edsger W. Dijkstra</sub>
</p>

<p align="center">⚜ &nbsp;━━━━━━━━━━━━━━━━━━━━━━━━ &nbsp;⚜</p>

## ❦ &nbsp;Prologue

I am a software engineer whose principal practice lies in the **design and stewardship of backend systems**.
My professional work is devoted to a service-oriented platform that supports the daily administration of an
**international school**, serving faculty, families and students alike. My interests reside at the
intersection of *software architecture*, *system integration* and *operational reliability*: the discipline
of making many independent components behave as one coherent and trustworthy whole.

<p align="center">⚜ &nbsp;━━━━━━━━━━━━━━━━━━━━━━━━ &nbsp;⚜</p>

## ❦ &nbsp;Principal Engagement

**Software Engineer · School Management Platform for an International School**

The platform is composed of a family of services, each entrusted with a distinct responsibility across the
academic lifecycle: admissions and enrolment, student records, tuition and finance, communication with
families, and integration with external academic and human-resources systems.

```mermaid
%%{init: {"theme":"base","themeVariables":{"fontFamily":"Georgia, serif","fontSize":"14px","lineColor":"#9C8FB5","primaryTextColor":"#4A3F5C"}}}%%
flowchart TB
    subgraph CL["Clients"]
        direction LR
        WEB["Staff Portal<br/>Vue 3 · Quasar"]
        MOB["Family & Student App<br/>mobile"]
    end

    subgraph ED["Edge Layer"]
        direction LR
        MBE["Mobile Backend"]
        BFF["Backend-for-Frontend<br/>FastAPI"]
    end

    subgraph CORE["Core Domain"]
        direction LR
        API["Core Domain Services<br/>Django · DRF · Celery"]
        IAM["Identity & Access<br/>JWT · RBAC"]
    end

    subgraph INT["Integration Layer · anti-corruption"]
        direction LR
        I1["Student Information<br/>Adapter"]
        I2["Human Resources<br/>Adapter"]
        I3["Notification<br/>Adapter"]
    end

    subgraph EXT["External Systems"]
        direction LR
        E1["Academic Systems"]
        E2["HR & Attendance"]
        E3["Payments · Cloud · Messaging"]
    end

    subgraph INF["Shared Infrastructure"]
        direction LR
        DB[("PostgreSQL<br/>database per service")]
        MQ[["RabbitMQ<br/>task queue"]]
        RC[("Redis<br/>cache")]
    end

    WEB --> API
    WEB --> IAM
    MOB --> MBE --> BFF
    BFF --> API
    BFF --> IAM
    API <--> IAM
    API --> I1 & I2 & I3
    I1 --> E1
    I2 --> E2
    I3 --> E3
    CORE -.-> INF

    classDef client fill:#E1ECF7,stroke:#8FB3D9,stroke-width:1.5px,color:#2F4A66
    classDef edge   fill:#F6E3EA,stroke:#D9A3B6,stroke-width:1.5px,color:#5C3346
    classDef core   fill:#E9DFF5,stroke:#A48BC9,stroke-width:2px,color:#3E2F5C
    classDef integ  fill:#E3F1E6,stroke:#9CC7A6,stroke-width:1.5px,color:#2E4F37
    classDef ext    fill:#FBF1DF,stroke:#D9BC85,stroke-width:1.5px,color:#5C4A26
    classDef infra  fill:#F2EEE9,stroke:#B9AFA3,stroke-width:1.5px,color:#4A443D

    class WEB,MOB client
    class MBE,BFF edge
    class API,IAM core
    class I1,I2,I3 integ
    class E1,E2,E3 ext
    class DB,MQ,RC infra

    style CL   fill:#F5F9FD,stroke:#8FB3D9,stroke-dasharray:4 3,color:#2F4A66
    style ED   fill:#FDF6F8,stroke:#D9A3B6,stroke-dasharray:4 3,color:#5C3346
    style CORE fill:#F8F4FC,stroke:#A48BC9,stroke-width:2px,color:#3E2F5C
    style INT  fill:#F5FAF6,stroke:#9CC7A6,stroke-dasharray:4 3,color:#2E4F37
    style EXT  fill:#FEFAF2,stroke:#D9BC85,stroke-dasharray:4 3,color:#5C4A26
    style INF  fill:#FAF8F5,stroke:#B9AFA3,stroke-dasharray:4 3,color:#4A443D
```

### Areas of Responsibility

| | Domain | Description |
|:-:|---|---|
| Ⅰ | **Service & Interface Design** | Formulating domain models and RESTful contracts for services that each govern their own data. |
| Ⅱ | **Identity & Authorisation** | Stateless, token-based authentication across service boundaries; role- and scope-based access control. |
| Ⅲ | **Systems Integration** | Encapsulating third-party systems behind adapters so that external models never permeate the core domain. |
| Ⅳ | **Asynchronous Processing** | Task queues, retry semantics, outbox-style delivery, idempotent synchronisation and reconciliation. |
| Ⅴ | **Schema Evolution** | Preserving a consistent and auditable migration lineage across every environment. |
| Ⅵ | **Delivery & Automation** | Continuous integration and containerised deployment; converting manual procedure into versioned configuration. |
| Ⅶ | **Architectural Review** | Evaluating the system against established microservice principles and charting improvements in resilience, observability and event-driven communication. |

<p align="center">⚜ &nbsp;━━━━━━━━━━━━━━━━━━━━━━━━ &nbsp;⚜</p>

## ❦ &nbsp;Technical Repertoire

<p align="center">
  <img src="https://img.shields.io/badge/Python-E9DFF5?style=for-the-badge&logo=python&logoColor=4A3F5C" />
  <img src="https://img.shields.io/badge/Django-E9DFF5?style=for-the-badge&logo=django&logoColor=4A3F5C" />
  <img src="https://img.shields.io/badge/Django_REST-E9DFF5?style=for-the-badge&logo=django&logoColor=4A3F5C" />
  <img src="https://img.shields.io/badge/FastAPI-E9DFF5?style=for-the-badge&logo=fastapi&logoColor=4A3F5C" />
  <img src="https://img.shields.io/badge/Celery-E9DFF5?style=for-the-badge&logo=celery&logoColor=4A3F5C" />
  <br/>
  <img src="https://img.shields.io/badge/PostgreSQL-F6E3EA?style=for-the-badge&logo=postgresql&logoColor=4A3F5C" />
  <img src="https://img.shields.io/badge/Redis-F6E3EA?style=for-the-badge&logo=redis&logoColor=4A3F5C" />
  <img src="https://img.shields.io/badge/RabbitMQ-F6E3EA?style=for-the-badge&logo=rabbitmq&logoColor=4A3F5C" />
  <br/>
  <img src="https://img.shields.io/badge/Vue_3-E1ECF7?style=for-the-badge&logo=vuedotjs&logoColor=4A3F5C" />
  <img src="https://img.shields.io/badge/Quasar-E1ECF7?style=for-the-badge&logo=quasar&logoColor=4A3F5C" />
  <img src="https://img.shields.io/badge/Docker-E1ECF7?style=for-the-badge&logo=docker&logoColor=4A3F5C" />
  <img src="https://img.shields.io/badge/Jenkins-E1ECF7?style=for-the-badge&logo=jenkins&logoColor=4A3F5C" />
</p>

| Discipline | Instruments |
|---|---|
| **Service Engineering** | Python · Django · Django REST Framework · Celery |
| **Lightweight Services** | FastAPI · asynchronous HTTP clients · SQLAlchemy · Pydantic |
| **Security & Identity** | JSON Web Tokens with asymmetric signatures · role-based access control |
| **Data Persistence** | PostgreSQL · Redis · multi-database routing |
| **Asynchronous Messaging** | RabbitMQ · background workers · scheduled tasks |
| **Presentation Layer** | Vue 3 · Quasar · Pinia |
| **Delivery** | Docker · Docker Compose · Jenkins · disciplined Git workflow |

<p align="center">⚜ &nbsp;━━━━━━━━━━━━━━━━━━━━━━━━ &nbsp;⚜</p>

## ❦ &nbsp;Methodological Principles

> *Database per Service* &nbsp;·&nbsp; *Stateless Authentication* &nbsp;·&nbsp; *Backend for Frontend*
> &nbsp;·&nbsp; *Anti-Corruption Layer* &nbsp;·&nbsp; *Transactional Outbox* &nbsp;·&nbsp; *Idempotency & Reconciliation*
> &nbsp;·&nbsp; *Cache-Aside* &nbsp;·&nbsp; *Adapter, Proxy, Strategy & Repository* &nbsp;·&nbsp; *Dependency Injection*
> &nbsp;·&nbsp; *The Twelve-Factor Application*

<p align="center">⚜ &nbsp;━━━━━━━━━━━━━━━━━━━━━━━━ &nbsp;⚜</p>

<p align="center">
  <img width="100%" src="https://capsule-render.vercel.app/api?type=soft&height=70&section=footer&color=0:E1ECF7,50:F6E3EA,100:E9DFF5" />
</p>
