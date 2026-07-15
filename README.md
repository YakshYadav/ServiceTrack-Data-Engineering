<h1 align="center">⚙️ ServiceTrack Analytics Pipeline</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Apache_Spark-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white" />
  <img src="https://img.shields.io/badge/Databricks-FF3621?style=for-the-badge&logo=databricks&logoColor=white" />
  <img src="https://img.shields.io/badge/Delta_Lake-00AADC?style=for-the-badge&logo=databricks&logoColor=white" />
  <img src="https://img.shields.io/badge/Python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54" />
</p>

## 📊 Business Impact & Final Dashboard
This project transforms raw, messy service center exports into a structured analytics infrastructure. The dashboards below visualize the final Gold-layer data, tracking technician efficiency, SLA compliance, and device failure trends.

![Dashboard Part 1](dashboard1.png.png)

![Dashboard Part 2](dashboard2.png.png)
---

## 🏗️ Pipeline Architecture (Medallion Design)
The data flows through a strict Medallion Architecture, ensuring data quality and enabling time-travel auditing.

```mermaid
graph LR
    A[(Raw CSVs)] -->|Auto Loader| B[🥉 Bronze Layer]
    B -->|Clean & Enrich| C[🥈 Silver Layer]
    C -->|Aggregates & SCD2| D[🥇 Gold Layer]
    D -->|Databricks SQL| E{{Business Dashboard}}
    
    style A fill:#f9f,stroke:#333,stroke-width:2px
    style B fill:#cd7f32,stroke:#333,stroke-width:2px
    style C fill:#c0c0c0,stroke:#333,stroke-width:2px
    style D fill:#ffd700,stroke:#333,stroke-width:2px
    style E fill:#87cefa,stroke:#333,stroke-width:2px

    ---

### 📝 Project Details
| 🏢 Company | 👨‍💻 Data Engineer | 👨‍🏫 Mentor(s) | 👩‍💼 HR Coordinator |
| :--- | :--- | :--- | :--- |
| **Celebal Technologies** | Yaksh Yadav | [Yashashvi Dubey](https://www.linkedin.com/in/yashashvi-dubey-92a3862a8/) & [Raj Biswas](https://www.linkedin.com/in/raj-biswas-1a07aa277/) | [Priyanshi Jain](https://www.linkedin.com/in/priyanshi-jain20/) |

---
