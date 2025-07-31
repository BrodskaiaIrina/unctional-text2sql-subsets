# RedSQL: Russian Domain-Specific Text-to-SQL Benchmark

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/release/python-380/)

## 📖 Overview

**RedSQL** is the first domain-specific text-to-SQL benchmark in Russian, designed to evaluate large language models' performance on specialized database queries across nine high-impact domains. This benchmark addresses the gap between academic text-to-SQL datasets and real-world applications by incorporating domain-specific terminology, complex schema structures, and realistic operational scenarios.

### Key Features

- 🌍 **9 Domain-Specific Datasets**: Banking, Aviation, Medicine, Logistics, Jurisprudence, Architecture, Energy, Science & Research, and Engineering
- 🇷🇺 **Russian Language Focus**: First comprehensive Russian text-to-SQL benchmark for domain-specific applications
- 📊 **409 Curated Query Pairs**: Carefully crafted natural language questions with corresponding SQL queries
- 🏗️ **Complex Schema Structures**: Average of 15.4 tables per database and 4.6 tables per query
- 🔬 **Comprehensive Evaluation**: Analysis of 5 state-of-the-art LLMs with both English and Russian prompts

## 🎯 Motivation

Existing text-to-SQL benchmarks like Spider and WikiSQL focus on general-domain scenarios and primarily English language. However, real-world applications often involve:

- **Domain-specific terminology** (e.g., ICD codes in healthcare, technical abbreviations in aviation)
- **Complex legacy schemas** with opaque column names and sparse documentation
- **Specialized query patterns** typical of operational environments
- **Non-English language requirements** for global deployment

RedSQL bridges this gap by providing a realistic testbed for evaluating model robustness under domain shift, particularly in Russian-language contexts.

## 📁 Repository Structure

```
functional-text2sql-subsets/
├── databases/                    # SQL database schemas and data for all domains
│   ├── database_banking_*.sql   # Banking domain database files
│   ├── database_aviation_*.sql  # Aviation domain database files
│   ├── database_medicine_*.sql  # Medicine domain database files
│   ├── database_logistics_*.sql # Logistics domain database files
│   ├── database_jurisprudence_*.sql # Jurisprudence domain database files
│   ├── database_architecture_*.sql # Architecture domain database files
│   ├── database_energy_*.sql    # Energy domain database files
│   ├── database_science_*.sql   # Science & Research domain database files
│   └── database_engineering_*.sql # Engineering domain database files
└── responses/                   # Model evaluation results and query datasets
    ├── text2SQL_banking.json   # Banking queries and responses
    ├── text2SQL_aviation.json  # Aviation queries and responses
    ├── text2SQL_medicine.json  # Medicine queries and responses
    ├── text2SQL_logistics.json # Logistics queries and responses
    ├── text2SQL_jurisprudence.json # Jurisprudence queries and responses
    ├── text2SQL_architecture.json # Architecture queries and responses
    ├── text2SQL_energy.json    # Energy queries and responses
    ├── text2SQL_science_and_research.json # Science queries and responses
    └── text2SQL_engineering.json # Engineering queries and responses
```

## 🏢 Domain Descriptions

### 🏦 Banking
**Complexity: High** | **Queries: 47** | **Avg Tables/Query: 4.2**

The banking domain encompasses comprehensive financial operations including customer management, account handling, transaction processing, and loan administration. This domain features complex relationships between customers, multiple account types, transaction histories, and credit facilities.

**Key Entities:**
- Customers (personal and corporate)
- Accounts (checking, savings, credit)
- Transactions (deposits, withdrawals, transfers)
- Loans and credit facilities
- Payment systems and cards

**Sample Query:** "Покажите всех клиентов с просроченными кредитами на сумму более 100,000 рублей"

### ✈️ Aviation
**Complexity: Medium** | **Queries: 46** | **Avg Tables/Query: 3.8**

The aviation domain covers airline operations, flight management, aircraft maintenance, and passenger services. This domain includes complex scheduling, route planning, and regulatory compliance requirements typical of the aviation industry.

**Key Entities:**
- Airports and terminals
- Aircraft and fleet management
- Flights and schedules
- Pilots and crew
- Passengers and bookings
- Maintenance records

**Sample Query:** "Найдите все рейсы из Москвы в Санкт-Петербург с задержкой более 30 минут за последнюю неделю"

### 🏥 Medicine
**Complexity: High** | **Queries: 45** | **Avg Tables/Query: 5.1**

The medical domain represents healthcare operations including patient management, medical records, treatment protocols, and pharmaceutical tracking. This domain features highly specialized terminology and complex regulatory requirements.

**Key Entities:**
- Patients and medical histories
- Doctors and medical staff
- Diagnoses and ICD codes
- Treatments and procedures
- Prescriptions and medications
- Hospital departments and resources

**Sample Query:** "Покажите всех пациентов с диагнозом диабет, которые не посещали врача более 6 месяцев"

### 🚛 Logistics
**Complexity: High** | **Queries: 46** | **Avg Tables/Query: 4.9**

The logistics domain encompasses supply chain management, warehouse operations, transportation, and inventory control. This domain involves complex routing, scheduling, and resource optimization challenges.

**Key Entities:**
- Warehouses and storage facilities
- Shipments and deliveries
- Vehicles and transportation
- Routes and scheduling
- Inventory and stock management
- Suppliers and customers

**Sample Query:** "Найдите все поставки, которые опаздывают более чем на 2 дня и имеют высокий приоритет"

### ⚖️ Jurisprudence
**Complexity: Medium** | **Queries: 37** | **Avg Tables/Query: 3.6**

The jurisprudence domain covers legal case management, court proceedings, legal documentation, and regulatory compliance. This domain includes specialized legal terminology and complex procedural requirements.

**Key Entities:**
- Legal cases and proceedings
- Clients and legal representation
- Courts and judges
- Legal documents and contracts
- Laws and regulations
- Legal fees and billing

**Sample Query:** "Покажите все дела по гражданским спорам, рассматриваемые в арбитражном суде за текущий месяц"

### 🏗️ Architecture
**Complexity: Medium** | **Queries: 46** | **Avg Tables/Query: 4.3**

The architecture domain encompasses construction project management, building design, resource allocation, and regulatory compliance. This domain involves complex project timelines and resource dependencies.

**Key Entities:**
- Construction projects
- Buildings and structures
- Architects and contractors
- Materials and resources
- Project timelines and milestones
- Permits and regulations

**Sample Query:** "Найдите все строительные проекты, которые превышают бюджет более чем на 15%"

### ⚡ Energy
**Complexity: High** | **Queries: 45** | **Avg Tables/Query: 5.2**

The energy domain covers power generation, distribution, consumption monitoring, and infrastructure management. This domain includes complex technical specifications and regulatory compliance requirements.

**Key Entities:**
- Power plants and generation facilities
- Distribution networks and grids
- Energy consumption and metering
- Maintenance and operations
- Regulatory compliance
- Environmental monitoring

**Sample Query:** "Покажите все электростанции с коэффициентом использования мощности ниже 70% за последний квартал"

### 🔬 Science & Research
**Complexity: High** | **Queries: 52** | **Avg Tables/Query: 4.8**

The science and research domain encompasses academic research management, laboratory operations, publication tracking, and grant administration. This domain features complex research workflows and collaboration patterns.

**Key Entities:**
- Research projects and grants
- Scientists and researchers
- Publications and citations
- Laboratory equipment and resources
- Experiments and data collection
- Collaborations and partnerships

**Sample Query:** "Найдите все исследовательские проекты в области искусственного интеллекта с бюджетом более 5 миллионов рублей"

### 🔧 Engineering
**Complexity: High** | **Queries: 45** | **Avg Tables/Query: 4.7**

The engineering domain covers industrial operations, manufacturing processes, quality control, and technical project management. This domain involves complex technical specifications and production workflows.

**Key Entities:**
- Engineering projects
- Manufacturing processes
- Quality control and testing
- Technical specifications
- Equipment and machinery
- Production schedules and resources

**Sample Query:** "Покажите все производственные линии с показателем брака выше 2% за последний месяц"

## 🚀 Quick Start

### Dataset Usage

Each domain dataset is provided in JSON format in the `responses/` directory. The structure includes:

```json
{
  "domain": "banking",
  "database_schema": "database_banking_create.sql",
  "queries": [
    {
      "id": 1,
      "question_ru": "Покажите все транзакции клиента с ID 12345 за последний месяц",
      "question_en": "Show all transactions for customer with ID 12345 for the last month",
      "sql_query": "SELECT * FROM transactions WHERE customer_id = 12345 AND transaction_date >= DATE('now', '-1 month')",
      "difficulty": "medium",
      "tables_used": ["transactions", "customers"]
    }
  ]
}
```

### Database Files

For each domain, three types of database files are provided in the `databases/` directory:

- **`*_create.sql`**: Schema definitions with table structures
- **`*_filled.sql`**: Populated databases with synthetic data
- **`*_full.sql`**: Complete database files ready for use

## 📊 Benchmark Statistics

| Domain | Queries | Avg Tables/Query | Complexity | Key Challenges |
|--------|---------|------------------|------------|----------------|
| Banking | 47 | 4.2 | High | Financial regulations, complex transactions |
| Aviation | 46 | 3.8 | Medium | Scheduling, safety regulations |
| Medicine | 45 | 5.1 | High | Medical terminology, patient privacy |
| Logistics | 46 | 4.9 | High | Supply chain complexity, routing |
| Jurisprudence | 37 | 3.6 | Medium | Legal terminology, procedural rules |
| Architecture | 46 | 4.3 | Medium | Project management, resource allocation |
| Energy | 45 | 5.2 | High | Technical specifications, regulations |
| Science & Research | 52 | 4.8 | High | Research workflows, collaboration |
| Engineering | 45 | 4.7 | High | Manufacturing processes, quality control |

**Total**: 409 queries across 9 domains

## 🔬 Evaluation Results

We evaluated 5 state-of-the-art language models on RedSQL:

- **Gemini Flash 2.0**
- **DeepSeek V3**
- **Meta LLaMA 3.3 70B**
- **OpenAI GPT-4o**
- **GigaChat Max**

### Key Findings

1. **Domain Complexity Impact**: Medicine, Science & Research, and Banking emerged as the most challenging domains
2. **Language Sensitivity**: Performance varies significantly between English and Russian prompts
3. **Model Robustness**: GPT-4o shows the most stable performance across domains
4. **Terminology Challenges**: Domain-specific terms significantly impact model performance


## 🔗 Related Work

- **Spider**: Cross-domain text-to-SQL benchmark
- **WikiSQL**: Large-scale text-to-SQL dataset
- **BIRD**: Big bench for large-scale database grounded text-to-SQL evaluation
- **PAUQ**: Previous Russian text-to-SQL benchmark (general domain)
---

**Note**: This benchmark is designed for research purposes to advance the field of domain-specific text-to-SQL generation. All data is synthetically generated and does not contain real personal or sensitive information. 

## Citation

```bibtex
@inproceedings{brodskaya-etal-2025-bridging,
    title = "Bridging the Gap with {R}ed{SQL}: A {R}ussian Text-to-{SQL} Benchmark for Domain-Specific Applications",
    author = "Brodskaya, Irina  and
      Tutubalina, Elena  and
      Somov, Oleg",
    editor = "Piskorski, Jakub  and
      P{\v{r}}ib{\'a}{\v{n}}, Pavel  and
      Nakov, Preslav  and
      Yangarber, Roman  and
      Marcinczuk, Michal",
    booktitle = "Proceedings of the 10th Workshop on Slavic Natural Language Processing (Slavic NLP 2025)",
    month = jul,
    year = "2025",
    address = "Vienna, Austria",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2025.bsnlp-1.9/",
    pages = "76--83",
    ISBN = "978-1-959429-57-9",
    abstract = "We present the first domain-specific text-to-SQL benchmark in Russian, targeting fields with high operational load where rapid decision-making is critical. The benchmark spans across 9 domains, including healthcare, aviation, and others, and comprises 409 curated query pairs. It is designed to test model generalization under domain shift, introducing challenges such as specialized terminology and complex schema structures. Evaluation of state-of-the-art large language models (LLM) reveals significant performance drop in comparison to open-domain academic benchmarks, highlighting the need for domain-aware approaches in text-to-SQL. The benchmark is available at: https://github.com/BrodskaiaIrina/functional-text2sql-subsets"
}```
