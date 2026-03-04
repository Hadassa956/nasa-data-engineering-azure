# NASA NEO Data Pipeline | Medallion Architecture on Azure

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Apache Spark](https://img.shields.io/badge/apache_spark-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white)
![Databricks](https://img.shields.io/badge/Databricks-FF3621?style=for-the-badge&logo=databricks&logoColor=white)
![Microsoft Azure](https://img.shields.io/badge/microsoft_azure-0089D6?style=for-the-badge&logo=microsoft-azure&logoColor=white)

## About the Project
An end-to-end Data Engineering pipeline built to extract, transform, and serve Near Earth Object (NEO) data consumed directly from the official NASA API. This project implements the Medallion Architecture pattern to ensure data quality, scalability, and governance.

## Architecture & Data Flow
The data pipeline is divided into three logical layers within Azure Data Lake Storage Gen2:
* **🥉 Bronze Layer:** Ingestion of raw data (nested JSON) directly from the NASA API, stored in Parquet format for read optimization.
* **🥈 Silver Layer:** Data cleansing, structure flattening, and addition of audit metadata (e.g., `silver_processing_date`).
* **🥇 Gold Layer:** Business logic application. The data was filtered and refined to deliver a final table containing only asteroids classified by NASA as a real threat (`is_potentially_hazardous_asteroid == True`).

## Technologies & Tools
* **Languages:** Python, PySpark
* **Big Data Processing:** Databricks
* **Cloud Storage:** Azure Data Lake Storage Gen2 (ADLS Gen2)
* **Security & Governance:** Azure Key Vault (complete isolation of credentials and API keys)
* **Version Control:** Git & GitHub

## Security Practices
No credentials, storage account keys, or API tokens were exposed in the source code. This project strictly utilizes Azure Key Vault integrated with Databricks Secret Scopes to fetch access keys at runtime, adhering to cloud security best practices.

---

Português-PT
# NASA NEO Data Pipeline | Arquitetura Medallion na Cloud

## Sobre o Projeto
Pipeline de Engenharia de Dados *end-to-end* construído para extrair, transformar e disponibilizar dados de Asteroides Próximos da Terra (NEO) consumidos diretamente da API oficial da NASA. Este projeto implementa o padrão de Arquitetura Medallion para garantir a qualidade, a escalabilidade e a governação dos dados.

## Arquitetura e Fluxo de Dados
O fluxo de dados foi dividido em três camadas lógicas dentro do Azure Data Lake Storage Gen2:
* **🥉 Camada Bronze:** Ingestão dos dados brutos (JSON aninhado) a partir da API da NASA, guardados no formato Parquet para otimização de leitura.
* **🥈 Camada Silver:** Limpeza dos dados, planificação (*flattening*) de estruturas complexas e adição de metadados de auditoria (ex: `data_processamento_silver`).
* **🥇 Camada Gold:** Aplicação de regras de negócio. Os dados foram filtrados e refinados para entregar uma tabela final contendo apenas os asteroides classificados pela NASA como uma ameaça real (`is_potentially_hazardous_asteroid == True`).

## Tecnologias e Ferramentas Utilizadas
* **Linguagens:** Python, PySpark
* **Processamento de Big Data:** Databricks
* **Armazenamento na Cloud:** Azure Data Lake Storage Gen2 (ADLS Gen2)
* **Segurança e Governação:** Azure Key Vault (isolamento completo de credenciais e chaves de API)
* **Controlo de Versões:** Git e GitHub

## Práticas de Segurança
Nenhuma credencial, chave de conta de armazenamento ou token de API foi exposto no código-fonte. Este projeto utiliza estritamente o Azure Key Vault integrado com o Databricks Secret Scopes para ir buscar as chaves de acesso em tempo de execução, cumprindo as melhores práticas de segurança na *cloud*.
