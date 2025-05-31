<h1 align="center"> Análise de Sentimentos em Avaliações de Produtos Amazon<br /> </h1>

## **1.0 Visão geral**

Este projeto tem como objetivo principal analisar e classificar avaliações de produtos da Amazon, identificando automaticamente se uma avaliação é positiva ou negativa. A partir de uma base real de avaliações, implementei 3 diferentes abordagens de processamento de linguagem natural (NLP) para transformar textos em dados estruturados e aplicar algoritmos de classificação para prever o sentimento das avaliações.

A base de dados utilizada neste projeto foi obtida por meio de web scraping realizado na Amazon e disponibilizada por um usuário da comunidade no Kaggle, através do seguinte link:

🔗 [Amazon Product Review Dataset on Kaggle](https://www.kaggle.com/datasets/sampaiovitor/avaliaes-em-portugus-amazon-e-mercado-livre)/)

> ⚠️ **Observação:** O autor do dataset não especifica o período de coleta das avaliações nem fornece detalhes adicionais sobre a metodologia de extração. Por se tratar de dados obtidos via scraping, é importante considerar possíveis limitações quanto à representatividade temporal e à completude das informações.

O projeto tem impacto direto em áreas como comércio eletrônico, suporte ao cliente e análise de reputação de produtos, permitindo automatizar a triagem de feedbacks dos consumidores, identificar produtos mal avaliados com maior rapidez e fornecer insights relevantes para decisões de marketing e melhorias de produto.

## **2.0 Objetivos técnicos**

A solução contempla três abordagens distintas para a classificação:

- Classificador por quantidade de palavras — abordagem simples e interpretável baseada em regras heurísticas.

- CountVectorizer — técnica de vetorização que transforma o texto em uma matriz de frequências de palavras, permitindo o uso de modelos de machine learning.

- TF-IDF (Term Frequency-Inverse Document Frequency) — abordagem que pondera a importância das palavras considerando a frequência no corpus, resultando em vetores mais informativos para classificação.


## **3.0 Ferramentas utilizadas**

- **Python (Anaconda):** Pré-processamento, modelagem e avaliação.
- **Pandas / seaborn / matplotlib/ Scikit-learn / nltk/ re / wordcloud/:** Bibliotecas para manipulação e NLP.
- **Jupyter Notebook:** Ambiente de desenvolvimento.
  
## **4.0 Desenvolvimento**

## **5.0 Resultados**

