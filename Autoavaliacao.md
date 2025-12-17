# Autoavaliação – MVP Engenharia de Dados

## Atingimento dos Objetivos

O objetivo principal deste MVP foi construir um pipeline de dados completo utilizando
tecnologias em nuvem, contemplando as etapas de extração, transformação, modelagem,
carga e análise de dados, com foco no **setor bancário**, especificamente na **análise
de risco de crédito**.

De forma geral, considera-se que os objetivos definidos inicialmente foram **atingidos
com sucesso**. Foi possível estruturar um pipeline funcional no Databricks, partindo
da ingestão dos dados brutos até a construção de um Data Warehouse em esquema estrela,
permitindo análises consistentes e alinhadas às perguntas de negócio.

As perguntas propostas no início do trabalho foram respondidas por meio de consultas
SQL e análises exploratórias, evidenciando fatores relevantes para a inadimplência,
como renda, idade, finalidade do empréstimo, taxa de juros e tempo de emprego.

---

## Considerações sobre a Etapa de Coleta

A etapa de coleta foi intencionalmente mantida simples, utilizando um conjunto de dados
público e confiável disponibilizado pela plataforma Kaggle. Essa decisão foi tomada
de forma consciente, considerando o contexto acadêmico do MVP e a natureza estática
do dataset, que representa um histórico consolidado de operações de crédito.

Optar por uma fonte estruturada e amplamente utilizada permitiu concentrar os esforços
nas etapas centrais de Engenharia de Dados, como organização em camadas, modelagem
dimensional, qualidade dos dados e análise analítica, evitando riscos éticos e legais
associados a técnicas de web scraping quando não necessárias.

Essa abordagem está alinhada com práticas comuns em projetos reais, nos quais dados
já consolidados e confiáveis são frequentemente utilizados como ponto de partida para
pipelines analíticos.

---

## Dificuldades Encontradas

Durante o desenvolvimento do MVP, algumas dificuldades foram enfrentadas:

- Limitações da **versão gratuita do Databricks**, que não permite o uso do DBFS público,
exigindo o uso de **Unity Catalog e Volumes** para persistência dos dados.
- Instabilidade e indisponibilidade de alguns datasets originalmente planejados,
o que exigiu adaptação na escolha da fonte de dados.
- Ajustes de contexto entre catálogo e schema no Databricks, especialmente durante
consultas SQL, exigindo maior atenção à qualificação dos nomes das tabelas.
- Necessidade de compreender o comportamento do SQL Warehouse, que executa apenas
uma consulta por bloco, o que impactou inicialmente a enfatização dos resultados.

Essas dificuldades contribuíram para um maior aprendizado prático sobre governança,
organização de dados e particularidades da plataforma Databricks.

---

## Aprendizados e Evolução Técnica

O desenvolvimento do MVP proporcionou aprendizado significativo em:

- Construção de pipelines de ETL utilizando Apache Spark e Delta Lake.
- Organização de dados em camadas **Bronze, Silver e Gold**.
- Modelagem dimensional em **esquema estrela**, com uso de surrogate keys.
- Uso do Databricks Jobs para execução sequencial de notebooks.
- Importância da documentação e explicação dos processos técnicos para fins de
avaliação e reprodutibilidade.

Além disso, foi possível reforçar a importância da análise de qualidade dos dados
antes da tomada de decisões analíticas.

---

## Evolução para Ingestão Incremental

Atualmente, o pipeline foi implementado utilizando uma abordagem de carga completa
(full load), adequada ao contexto do MVP e à característica estática da fonte de dados.
Essa decisão simplifica o controle do fluxo e garante reprodutibilidade durante o
desenvolvimento e avaliação do projeto.

Como evolução futura, o pipeline pode ser facilmente adaptado para ingestão incremental,
por meio do uso de operações de append na camada Bronze, deduplicação na camada Silver
e operações de merge (upsert) na camada Gold, utilizando recursos nativos do Delta Lake.

Essa adaptação permitiria o processamento eficiente de novas cargas de dados, mantendo
histórico e garantindo escalabilidade do pipeline em um cenário de produção.

---

## Trabalhos Futuros

Como continuidade e evolução deste MVP, alguns trabalhos futuros podem ser considerados:

- Implementação de um modelo preditivo de risco de crédito utilizando técnicas de
Machine Learning.
- Automatização completa da ingestão de dados utilizando APIs ou conectores externos.
- Criação de dashboards interativos para visualização dos indicadores de risco.
- Inclusão de novas fontes de dados para enriquecer a análise, como dados macroeconômicos.
- Monitoramento contínuo da qualidade dos dados ao longo do tempo.

Essas extensões tornariam o projeto ainda mais robusto e próximo de um ambiente
real de produção.

---

## Considerações Finais

O MVP cumpriu seu papel como um projeto prático de Engenharia de Dados, integrando
conceitos teóricos e técnicos de forma aplicada. O trabalho desenvolvido representa
uma base sólida para projetos futuros e contribui de forma relevante para o
portfólio acadêmico e profissional.
