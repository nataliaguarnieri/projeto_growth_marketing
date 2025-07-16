# 📈 Growth360: Performance Multicanal e Jornada de Clientes

Simulação de uma empresa digital com campanhas em diversos canais e funil de conversão integrado com vendas. O projeto abrange engenharia e análise de dados para monitoramento de performance, otimização de funis e suporte à estratégia de marketing e growth.

---

## 🎯 Objetivo

**Analisar a performance de canais digitais e a jornada de clientes para gerar insights de marketing e growth**, simulando um ambiente real de tomada de decisão com dados.

---

## 📊 Escopo Analítico

| Eixo do Projeto                                                                                   | Simulação e Análise no Projeto                                                   |
|---------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| Performance de canais (Google Ads, FB Ads, LinkedIn, SEO, Email)                                 | Campanhas multicanais com custo e resultados simulados                                       |
| KPIs: ROI, ROAS, CAC, LTV                                                                         | Cálculo realista via dbt com métricas por canal e campanha                                   |
| Funil de conversão e jornada do cliente                                                           | Eventos de interação + pipeline de vendas                                                    |
| Coortes e personas                                                                                | Agrupamentos por comportamento e atributos demográficos                                       |
| Comportamento em site e landing pages                                                             | Simulação de eventos web (visita, scroll, clique, etc.)                                      |
| Testes A/B e modelos de atribuição                                                                | Grupos de teste e controle + atribuição linear/último clique                                 |
| Relatórios estratégicos                                                                           | Dashboards + análise estratégica em notebook                                                 |
| Integração marketing + vendas                                                                     | Conexão entre campanhas e conversões no pipeline comercial                                   |

---

## 🧱 Arquitetura Técnica

### Geração de Dados Sintéticos (com Python)

| Tabela          | Descrição                                                                      |
|-----------------|----------------------------------------------------------------------------------|
| `users`         | Usuários com idade, sexo, localização, canal favorito, persona                  |
| `personas`      | Tags simulando perfis comportamentais (ex: estudante, empreendedor)             |
| `web_events`    | Interações em landing pages (visita, scroll, clique em CTA, bounce)             |
| `campaigns`     | Campanhas por canal, com data, objetivo, segmento-alvo                          |
| `ad_spend`      | Investimento por campanha, canal e dia                                          |
| `conversions`   | Conversões com valor gerado e canal atribuído                                   |
| `sales_pipeline`| Pipeline do lead (lead → MQL → SQL → venda)                                     |
| `ab_tests`      | Grupo de experimento (teste x controle) com resultado                           |

---

### Armazenamento em Nuvem

- Arquivos `.parquet` ou `.csv`
- Bucket na nuvem: **AWS S3** ou **Google Cloud Storage**
- Particionado por canal, data ou tipo de evento

---

## 🧠 Transformações com dbt

**Camadas dbt:**

- `stg_`: Limpeza e padronização dos dados brutos
- `int_`: Métricas intermediárias (ex: tempo na jornada, tags de comportamento)
- `fct_`: Métricas agregadas de performance (campanha, canal, usuário)
- `dim_`: Dimensões auxiliares (canais, personas, tempo, funil)

**Principais KPIs calculados:**

| Métrica         | Fórmula Simplificada                                |
|-----------------|------------------------------------------------------|
| ROI             | (Receita - Custo) / Custo                            |
| ROAS            | Receita / Custo de anúncios                          |
| CAC             | Custo / Nº de clientes adquiridos                    |
| LTV             | Receita média por usuário * tempo médio de retenção  |
| Taxa conversão  | Nº conversões / Nº visitantes                        |

---

## 📊 Dashboard

Ferramentas possíveis: **Metabase**, **Looker Studio** ou **Apache Superset**

### Principais Visualizações:

- Visão geral da performance por canal
- Análise de cohort de usuários (data de aquisição vs retenção/conversão)
- Funil de conversão visual
- Resultados de testes A/B
- Comportamento em landing pages
- Custo e retorno por campanha

---

## 📈 Análise Estratégica

Feita em **Jupyter Notebook** ou apresentação com storytelling. Inclui:

- Canais com maior ROI/ROAS
- Perfis de usuários com maior LTV
- Gargalos no funil de conversão
- Segmentos com maior engajamento por tipo de campanha
- Recomendações de otimização para os times de marketing e vendas

---

## 🛠️ Stack de Ferramentas

| Camada              | Ferramentas                                                                         |
|---------------------|--------------------------------------------------------------------------------------|
| Geração de dados    | Python, Pandas, Faker                                                               |
| Armazenamento       | AWS S3 ou GCP Storage                                                               |
| Transformação       | dbt (local ou dbt Cloud, com DuckDB ou BigQuery)                                   |
| Orquestração (extra)| Airflow (opcional)                                                                  |
| Dashboard           | Metabase, Superset ou Looker Studio                                                 |
| Análise final       | Jupyter, Google Slides ou PowerPoint                                                |
| Documentação        | GitHub + dbt docs + README completo                                                 |

---

## ✅ Etapas do Projeto

| Etapa                         | Status      |
|------------------------------|-------------|
| Estrutura inicial do projeto | ☐           |
| Geração de dados sintéticos  | ☐           |
| Armazenamento em nuvem       | ☐           |
| Criação do projeto dbt       | ☐           |
| Modelagem `stg_`             | ☐           |
| Modelagem `int_` e `fct_`    | ☐           |
| Cálculo dos KPIs             | ☐           |
| Conexão com dashboard        | ☐           |
| Análise estratégica final    | ☐           |
| Documentação e README        | ☐           |

---

## 🌟 Extensões Futuras

- Deploy do dashboard interativo (ex: Streamlit)
- Orquestração com Airflow
- Feature store de usuários segmentados
- Criação de alertas automáticos para métricas fora da média

