# MVP de Engenharia de Dados

## Análise do Catálogo Disney+ em Arquitetura Lakehouse

---

## 1. Introdução

Este repositório apresenta o **MVP de Engenharia de Dados** desenvolvido como parte de um trabalho acadêmico de pós-graduação, cujo objetivo é demonstrar a aplicação prática de conceitos de ingestão, transformação, modelagem e análise de dados em um ambiente **Lakehouse**, utilizando a plataforma **Databricks**. O estudo tem como base o dataset público *Disney+ Movies and TV Shows*, disponibilizado pela plataforma Kaggle, contendo informações sobre títulos do catálogo da Disney+.

O trabalho foi estruturado de modo a evidenciar boas práticas de engenharia de dados, incluindo organização em camadas, governança, rastreabilidade e modelagem dimensional, culminando na produção de análises analíticas que respondem a questões relevantes sobre a evolução do catálogo da plataforma.

---

## 2. Objetivos do Trabalho

O MVP tem como objetivos principais:

* Implementar um pipeline de dados completo utilizando a arquitetura Medallion;
* Demonstrar o processo de ingestão e transformação de dados em ambiente Databricks;
* Construir um modelo dimensional em esquema estrela para suporte analítico;
* Garantir rastreabilidade e qualidade dos dados ao longo do fluxo de ETL;
* Responder às seguintes questões analíticas:

  1. Qual é o tempo médio entre o lançamento de um filme e sua entrada no catálogo Disney+?
  2. Como evoluiu a diversidade de gêneros únicos ao longo do tempo, considerando o ano de adição ao catálogo?
  3. Quais gêneros são mais frequentes no catálogo Disney+, incluindo análises comparativas entre filmes e séries?

---

## 3. Metodologia e Arquitetura

O pipeline de dados foi implementado no Databricks seguindo a **arquitetura Medallion**, organizada em três camadas distintas:

* **Camada Bronze**: ingestão do arquivo CSV original sem modificações, preservando os dados brutos conforme a fonte, garantindo rastreabilidade, auditoria e possibilidade de reprocessamento.
* **Camada Silver**: aplicação de limpezas e transformações simples, incluindo tratamento de valores nulos, padronização de tipos de dados e normalização de campos multivalorados, preparando os dados para uso analítico.
* **Camada Gold**: modelagem analítica em esquema estrela, com definição de tabela fato e dimensões, criação de métricas derivadas (como *lag_days*) e disponibilização de dados otimizados para consultas e visualizações.

A tabela fato foi definida considerando um cenário **factless**, no qual o evento central é a adição de um título ao catálogo, permitindo análises temporais e agregações a partir das dimensões associadas.

---

## 4. Organização do Repositório

A estrutura do repositório está organizada da seguinte forma:

```
.
├── README.md
├── data/
│   └── disney_plus_titles.csv
└── notebooks/
    └── MVP Engenharia de Dados - Viviane Mendes Matos.ipynb
    └── Catalogo_Dados.pdf
    └── MER StarSchema Disney+.png
    └── Linhagem de Dados MVP.png

```

### Descrição dos principais artefatos

* **README.md**
  Documento principal do projeto, descrevendo objetivos, metodologia, arquitetura e organização do trabalho.

* **Catalogo_Dados.pdf**
  Catálogo de dados da camada Gold, contendo a descrição das tabelas, atributos, domínios esperados e regras de qualidade.

* **MER StarSchema Disney+.png**
  Diagrama Entidade-Relacionamento do modelo dimensional em esquema estrela.

* **Linhagem de Dados MVP.png**
  Diagrama conceitual de linhagem, representando o fluxo dos dados desde a origem até a camada analítica.

* **data/**
  Pasta que contém o dataset original utilizado no estudo.

* **notebooks/**
  Pasta que reúne os artefatos de implementação, incluindo o notebook principal:

  * **MVP Engenharia de Dados - Viviane Mendes Matos.ipynb**, que consolida todo o desenvolvimento do pipeline, desde a ingestão até as análises e visualizações finais.

---

## 5. Notebook de Implementação

O notebook **MVP Engenharia de Dados - Viviane Mendes Matos.ipynb** concentra todas as etapas do trabalho, incluindo:

* Ingestão dos dados na camada Bronze;
* Processos de limpeza e transformação na camada Silver;
* Normalização de atributos multivalorados;
* Construção das tabelas da camada Gold;
* Consultas SQL analíticas;
* Geração de gráficos e tabelas-resumo;
* Validações de qualidade e consistência dos dados.

A utilização de um **notebook único** visa facilitar a leitura sequencial do processo, a reprodutibilidade do experimento e a avaliação acadêmica do fluxo completo de dados.

---

## 6. Considerações Finais

Este trabalho evidencia a aplicação integrada de conceitos fundamentais de Engenharia de Dados em um cenário realista, combinando arquitetura Lakehouse, modelagem dimensional e análise exploratória. A abordagem adotada permite compreender de forma clara a evolução dos dados desde sua origem até o consumo analítico, além de oferecer uma base sólida para extensões futuras, como a incorporação de novas fontes de dados, automação de verificações de qualidade e aprofundamento das análises estatísticas.

* ou alinhar o conteúdo ao **template padrão da sua pós-graduação**.

