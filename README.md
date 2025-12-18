# MVP – Engenharia de Dados  
## Análise de Risco de Crédito no Setor Bancário

Este repositório contém o desenvolvimento completo do **MVP de Engenharia de Dados**,
cujo objetivo é a construção de um pipeline de dados em nuvem para **análise de risco
de crédito no setor bancário**, utilizando a plataforma **Databricks**.

O projeto contempla todas as etapas exigidas no MVP: **objetivo, coleta, modelagem,
carga, análise e autoavaliação**, seguindo boas práticas de Engenharia de Dados.

---

## 🎯 Objetivo do Projeto

O objetivo deste MVP é **analisar fatores que influenciam a inadimplência em operações
de crédito**, utilizando dados históricos de clientes e empréstimos.

A partir do pipeline construído, busca-se responder perguntas de negócio como:

- Quais fatores demográficos influenciam o risco de crédito?
- Como renda e idade impactam a inadimplência?
- Quais tipos de empréstimos apresentam maior risco?
- Existe relação entre taxa de juros e inadimplência?
- O tempo de emprego influencia o risco de crédito?

---

## 📊 Conjunto de Dados

- **Fonte:** Kaggle  
- **Dataset:** Credit Risk Dataset  
- **Link:** https://www.kaggle.com/datasets/laotse/credit-risk-dataset  

O dataset é público, estruturado e amplamente utilizado em estudos de risco de crédito,
contendo informações demográficas, financeiras e características dos empréstimos.

A escolha dessa fonte se deu pela confiabilidade, clareza de licença e adequação ao
contexto acadêmico do MVP.

---

## 🏗️ Arquitetura do Projeto

O pipeline de dados foi estruturado seguindo o padrão **Lakehouse**, com camadas bem
definidas:

```text
Bronze → Silver → Gold (Data Warehouse)
```

- **Bronze:** dados brutos extraídos da fonte
- **Silver:** dados tratados, limpos e padronizados
- **Gold:** Data Warehouse modelado em esquema estrela

Os dados são armazenados utilizando **Delta Lake**, garantindo persistência e
consistência.

---

## 🗂️ Estrutura do Repositório

```text
.
├── evidencias/
│   ├── 01_pipeline_execucao_sucesso.png
│   ├── 02_bronze_credit_risk.png
│   ├── 03_silver_credit_risk.png
│   ├── 04_gold_fato_credit_risk.png
│   └── README.md
├── 00_setup_environment.ipynb
├── 01_extract_credit_risk.ipynb
├── 02_transform_credit_risk.ipynb
├── 03_load_dw_credit_risk.ipynb
├── 04_analysis_credit_risk.ipynb
├── AUTOAVALIACAO.md
└── README.md
```

### Descrição dos Notebooks

- **00_setup_environment.ipynb**  
  Configuração inicial do ambiente no Databricks (catálogo, schemas e volumes).

- **01_extract_credit_risk.ipynb**  
  Extração dos dados brutos e carga na camada Bronze.

- **02_transform_credit_risk.ipynb**  
  Limpeza, padronização e tratamento dos dados (camada Silver).

- **03_load_dw_credit_risk.ipynb**  
  Construção do Data Warehouse em **esquema estrela** (camada Gold).

- **04_analysis_credit_risk.ipynb**  
  Análise da qualidade dos dados e resposta às perguntas de negócio.

---

## 🧩 Modelagem dos Dados

O Data Warehouse foi modelado em **esquema estrela**, composto por:

### Tabela Fato
- `fato_credit_risk`

### Tabelas Dimensão
- `dim_customer`
- `dim_home`
- `dim_employment`
- `dim_intent`

Essa modelagem facilita consultas analíticas, agregações e análises exploratórias.

---

## 🔄 Pipeline de ETL

O pipeline de ETL foi implementado utilizando **Databricks Jobs**, permitindo a execução
sequencial dos notebooks de extração, transformação e carga com **um único acionamento
manual**.

A abordagem adotada foi de **carga completa (full load)**, adequada ao contexto do MVP
e à natureza estática do dataset. Possíveis evoluções para ingestão incremental são
discutidas na autoavaliação.

---

## 📈 Análise dos Dados

Na etapa de análise, foram realizadas:

- Avaliação da qualidade dos dados
- Análise exploratória das variáveis
- Respostas às perguntas de negócio relacionadas ao risco de crédito

Os resultados indicam que fatores como renda, idade, finalidade do empréstimo, taxa de
juros e tempo de emprego apresentam forte relação com a inadimplência.

---

## 🧠 Autoavaliação

A autoavaliação do projeto, incluindo dificuldades encontradas, aprendizados e
trabalhos futuros, está disponível no arquivo:

```text
AUTOAVALIACAO.md
```

---

## 🛠️ Tecnologias Utilizadas

- Databricks (Free Edition)
- Apache Spark
- Delta Lake
- SQL
- Python
- Kaggle

---

## 📌 Considerações Finais

Este MVP demonstra a aplicação prática de conceitos de Engenharia de Dados, desde a
ingestão até a análise analítica, utilizando uma arquitetura organizada, documentada
e alinhada às boas práticas do mercado.

O projeto serve como base para evoluções futuras, como ingestão incremental,
modelos preditivos e visualizações interativas.

