## Pipeline de Dados - Olist

**Meu primeiro projeto de dados. Construí um pipeline completo no Snowflake com arquitetura Medallion e visualizei no Power BI. 
Hoje eu olho pra isso e penso: "e se eu tivesse feito isso na AWS?"**

Esse projeto é a prova de onde eu comecei. E a base para onde eu vou.

[![Snowflake](https://img.shields.io/badge/Snowflake-29B5E8?style=flat-square&logo=snowflake&logoColor=white)](https://www.snowflake.com/)
[![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=mysql&logoColor=white)](https://dev.mysql.com/doc/)
[![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat-square&logo=power-bi&logoColor=black)](https://powerbi.microsoft.com/)
[![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazon-aws&logoColor=white)](https://aws.amazon.com/)
[![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)


## O que é isso

Pipeline completo de dados usando a **arquitetura Medallion** (Bronze, Silver, Gold) no **Snowflake**, com dados de e-commerce da Olist. 
O objetivo era transformar dados brutos em indicadores de negócio (KPIs) visualizados no **Power BI**.

Esse foi meu **primeiro projeto de dados**. Eu tinha nível intermediário em conhecimento em Cloud ainda. Mas construir esse pipeline me ensinou algo que hoje eu uso na AWS: **como pensar em camadas, como transformar dados, como entregar valor pro negócio.**


## A arquitetura (como eu construí)

<p align="center">
  <img src="architecture-olist-medallion-pipeline.png" alt="Arquitetura de Dados Olist - Pipeline Medallion e Power BI" width="700%">
</p>

### O que cada camada faz

| Camada | O que acontece | Exemplo real |
|---|---|---|
| **Bronze** | Ingestão dos dados brutos da Olist | CSVs de pedidos, clientes, produtos jogados no Snowflake como estão |
| **Silver** | Limpeza, padronização, deduplicação | Datas no formato certo, CPFs validados, categorias unificadas |
| **Gold** | Modelagem dimensional e views analíticas | Tabela fato de vendas, dimensão de clientes, dimensão de tempo |

---

## Tech Stack

- **Snowflake** — data warehouse em nuvem, storage e compute separados
- **SQL** — criação de tabelas, views, stored procedures e transformações
- **Power BI** — dashboards interativos com KPIs de negócio
- **Arquitetura Medallion** — organização em Bronze, Silver, Gold

---

## Arquivos do projeto

| Arquivo | O que faz |
|---|---|
| `01_Criação_Camadas_Bronze_Silver.sql` | Scripts de preparação dos dados brutos e limpeza |
| `02_Criação_Camada_Gold.sql` | Criação das tabelas consolidadas e views analíticas |
| `03_Consultas_e_Analises.sql` | Consultas de exploração e verificação dos KPIs |
| `portfolio-tecnico-olist.pdf` | Documentação completa da arquitetura, modelagem e KPIs |

---

## KPIs que entreguei

- **Volume de Pedidos por Mês** — sazonalidade e tendência de vendas
- **Distribuição Geográfica de Clientes por Estado** — mapa de penetração de mercado
- **Ticket Médio** — valor médio por pedido
- **Tempo Médio de Entrega** — performance logística
- **Top Categorias de Produtos** — o que mais vende


<p align="center">
  <img src="dashboard-olist-analytics.png" alt="Dashboard Olist e KPIs de Vendas" width="700">
</p>
---

## O que esse projeto me ensinou (e que uso hoje na Cloud)

Esse foi meu **primeiro contato** com pipeline de dados. Na época eu não sabia o que era IAM, VPC, ou S3. Mas aprendi coisas que hoje são fundamentais na AWS:

1. **Camadas de dados são camadas de responsabilidade.** Bronze = "não confio nisso ainda". Gold = "pode usar pra decisão". Na AWS, isso se traduz em S3 buckets com políticas de lifecycle diferentes.

2. **SQL é SQL.** O que eu escrevi no Snowflake, eu escrevo no Athena, no Redshift, no RDS. A sintaxe muda pouco. O conceito não muda.

3. **Dashboard sem dados limpos é mentira.** Eu passei 70% do tempo limpando dados em Silver. O Power BI foi o último 10%. Na Cloud, isso se traduz em: **ETL antes de visualização, sempre.**

4. **Snowflake me ensinou sobre separação de storage e compute.** Quando eu vi EC2 + EBS na AWS, eu já entendia o conceito. Snowflake foi meu treino.

---

## Versão Cloud — Onde eu quero levar isso

Esse pipeline hoje está no Snowflake. Mas eu já sei como fazer isso na AWS. E vou fazer.


### Arquitetura futura na AWS:



## Objetivo
Este projeto foi desenvolvido para demonstrar habilidades em engenharia e análise de dados, utilizando a arquitetura **Medallion** (Bronze, Silver, Gold) para processar dados de e-commerce e gerar indicadores de negócio (KPIs).

## 🛠️ Tecnologias Utilizadas
- **Snowflake:** Armazenamento e processamento de dados em nuvem.
- **SQL:** Limpeza, transformação e modelagem dos dados.
- **Power BI:** Visualização de dados e criação de dashboards.

## 🏗️ Arquitetura do Projeto
- **Camada Bronze:** Ingestão dos dados brutos.
- **Camada Silver:** Limpeza e padronização.
- **Camada Gold:** Modelagem dimensional e criação de views analíticas.

## 📊 KPIs de Negócio
O projeto foca em indicadores operacionais:
- Volume de Pedidos por Mês.
- Distribuição Geográfica de Clientes por Estado.
- ![Dashboard Olist](dashboard_olist.png)

## 📂 Organização dos Arquivos
- `01_Criação_Camadas_Bronze_Silver.sql`: Scripts de preparação dos dados.
- `02_Criação_Camada_Gold.sql`: Criação das tabelas consolidadas e da View analítica.
- `03_Consultas_e_Analises.sql`: Consultas de exploração e verificação.
- Markdown
---

### 📄 Documentação Técnica
Para uma visão detalhada da arquitetura, modelagem dimensional e KPIs aplicados, acesse o documento abaixo:
[📥 Visualizar Portfólio Técnico - Olist](Portfolio_Projeto_Olist_v2.pdf)

---
*Projeto desenvolvido por Eliana Diniz Araújo e Silva como parte da construção de um portfólio de dados.*
