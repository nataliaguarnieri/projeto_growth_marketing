# 💐 Floratta Digital – Análise de Growth e Jornada de Clientes

Este projeto simula a **Floratta Digital**, uma empresa fictícia de cosméticos veganos e fragrâncias artesanais, inspirada em marcas como **Natura** e **O Boticário**. A Floratta opera 100% online e utiliza canais de marketing digital para atrair, converter e fidelizar clientes. O objetivo do projeto é analisar o desempenho das campanhas multicanal, o comportamento de usuários e a jornada de compra, com foco em estratégias de **growth marketing**.

---

## 🎯 Objetivo

Construir um projeto completo de engenharia e análise de dados que simula uma operação real de marketing digital e vendas diretas ao consumidor. O projeto é dividido em três fases:

1. **Engenharia de dados:** geração, armazenamento, modelagem e cálculo de KPIs
2. **Visualização estratégica:** construção de dashboards para os times de Marketing, Growth e Vendas
3. **Análise avançada:** execução e análise de um teste A/B, com recomendações de otimização

---

## 🧪 Sobre a Floratta Digital

> A **Floratta Digital** é uma marca 100% online de cosméticos veganos e fragrâncias artesanais. Voltada para mulheres urbanas entre 25 e 45 anos, a empresa aposta em campanhas multicanal, personalização de ofertas e fidelização por meio de experiências sensoriais. Suas principais estratégias envolvem:

- Campanhas em **Instagram Ads**, **Google Ads**, **YouTube Ads**, **Email Marketing** e **SEO**
- Ofertas como “Kit de Amostra Grátis”, “Fragrância da Estação” e “Clube de Assinatura”
- Conversão via landing pages segmentadas

---

## 🧬 Jornada Simulada

```text
🟡 Visitante (Instagram/Google/SEO)
→ 🟠 Interação com anúncio ou página
→ 🔵 Cadastro como lead
→ 🟣 Primeira compra
→ 🟢 Retenção ou churn
```

---

## 📊 Escopo do Projeto

| Tema do Projeto                                                                                      | Implementação no Projeto                                                                     |
|----------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| Análise de canais (Google, Insta, Email, SEO)                                                     | Simulação de campanhas com dados sintéticos por canal e por segmento                         |
| KPIs de marketing: ROI, ROAS, CAC, LTV                                                            | Cálculo via dbt usando eventos de conversão, custo e retenção                                |
| Funil de conversão e jornada do cliente                                                           | Mapeamento da jornada desde o clique até a retenção, com timestamps                          |
| Segmentação e coortes                                                                             | Agrupamento por idade, comportamento, persona e data de aquisição                            |
| Comportamento em landing pages                                                                    | Simulação de interações com páginas (scroll, clique, bounce, tempo na página)                |
| Teste A/B com CTA                                                                                 | Implementação de grupos teste e controle em landing pages, com análise posterior             |
| Relatórios estratégicos                                                                           | Dashboards para Growth e apresentação de recomendações com base nos dados                    |
| Integração marketing e vendas                                                                     | Conexão entre campanhas e conversões no funil de vendas (lead → venda)                       |

---

## 🛠️ Stack de Ferramentas

| Etapa                    | Ferramentas utilizadas                                                  |
|--------------------------|------------------------------------------------------------------------|
| Geração de dados         | Python, Pandas, Faker                                                  |
| Armazenamento            | AWS S3 ou Google Cloud Storage (parquet/csv)                          |
| Transformação e modelagem| dbt (com DuckDB ou BigQuery)                                           |
| Dashboard                | Looker Studio ou Power BI                                              |
| Orquestração             | Apache Airflow (local)                                                 |
| Análise final            | Jupyter Notebook ou Google Slides                                      |
| Documentação             | GitHub + dbt docs + README completo                                    |

---

## 📂 Estrutura de Dados Sintéticos

| Tabela                  | Descrição                                                                 |
|-------------------------|---------------------------------------------------------------------------|
| `users`                | Usuárias simuladas com idade, cidade, canal favorito, persona             |
| `campaigns`            | Campanhas com canal, produto, criativo, datas                             |
| `web_events`           | Eventos em landing pages (scroll, clique, bounce, tempo na página)        |
| `ad_spend`             | Investimentos diários por campanha e canal                                |
| `leads`                | Leads gerados a partir das campanhas, com origem e tags                   |
| `sales_pipeline`       | Pipeline de vendas (lead → MQL → SQL → venda)                             |
| `conversions`          | Compras feitas, com valor e canal atribuído                               |
| `ab_tests`             | Grupos teste e controle em campanhas de landing page                      |

---

## 🧠 Transformações com dbt

### Camadas:

- `stg_`: Padronização e limpeza dos dados brutos
- `int_`: Cálculos intermediários (ex: tempo até conversão, custo por lead)
- `fct_`: Fatos agregados com métricas de desempenho
- `dim_`: Tabelas de dimensão como canal, tempo, persona

### KPIs implementados:

| Métrica         | Fórmula simplificada                                 |
|-----------------|------------------------------------------------------|
| ROI             | (Receita - Custo) / Custo                            |
| ROAS            | Receita / Custo de anúncio                           |
| CAC             | Custo / Nº de clientes adquiridos                    |
| LTV             | Receita média por usuário * tempo médio de retenção  |
| Taxa conversão  | Nº conversões / Nº visitantes                        |

---

## 📊 Dashboards

Criados com Looker Studio ou Power BI, com visualizações como:

- Performance por canal e campanha
- Comparativo de CAC, ROAS, LTV
- Cohorts por data de aquisição
- Funil de conversão
- Resultado do teste A/B
- Comportamento de visitantes em páginas

---

## 📈 Análise Avançada

### 🔬 Teste A/B: CTA na Landing Page

- **Hipótese:** O CTA “Descubra sua fragrância ideal” gera mais conversão do que “Peça já sua amostra grátis”
- **Execução:** Grupos de teste e controle aplicados aos visitantes da landing page
- **Métrica avaliada:** Taxa de conversão visita → lead
- **Resultado:** _[será analisado e apresentado após simulação]_

---

### 📌 Recomendações Estratégicas (exemplo)

- Redirecionar investimento do canal YouTube para Google Ads, que tem ROAS 3x superior
- Focar campanhas de email marketing no público "executiva urbana", com maior LTV
- Adotar CTA mais emocional nas landing pages baseado no resultado do teste A/B

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
| Execução do teste A/B        | ☐           |
| Análise estratégica final    | ☐           |
| Documentação e README        | ✅           |

---

## 👩‍💻 Sobre o Projeto

Este projeto foi desenvolvido por [Natália Guarnieri]([https://www.linkedin.com/in/nataliaguarnieri/]) como parte do seu portfólio em dados, com foco em engenharia, análise de marketing e estratégias de crescimento baseadas em dados.

