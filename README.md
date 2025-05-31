<h1 align="center"> Análise de Sentimentos em Avaliações de Produtos Amazon<br /> </h1>

## **1.0 Visão geral**

Este projeto tem como objetivo principal analisar e classificar avaliações de produtos da Amazon, identificando automaticamente se uma avaliação é positiva ou negativa. A partir de uma base real de avaliações, implementei 3 diferentes abordagens de processamento de linguagem natural (NLP) para transformar textos em dados estruturados e aplicar algoritmos de classificação para prever o sentimento das avaliações.

A base de dados utilizada neste projeto foi obtida por meio de web scraping realizado na Amazon e disponibilizada por um usuário da comunidade no Kaggle, através do seguinte link:

🔗 [Amazon Product Review Dataset on Kaggle](https://www.kaggle.com/datasets/sampaiovitor/avaliaes-em-portugus-amazon-e-mercado-livre)/)

> ⚠️ **Observação:** O autor do dataset não especifica o período de coleta das avaliações nem fornece detalhes adicionais sobre a metodologia de extração. Por se tratar de dados obtidos via scraping, é importante considerar possíveis limitações quanto à representatividade temporal e à completude das informações.

O projeto tem impacto direto em áreas como comércio eletrônico, suporte ao cliente e análise de reputação de produtos, permitindo automatizar a triagem de feedbacks dos consumidores, identificar produtos mal avaliados com maior rapidez e fornecer insights relevantes para decisões de marketing e melhorias de produto.

## **2.0 Objetivos técnicos**

Entregar planilhas em excel com as quantidade e representação percentual das avaliações positivas e negativas por tipo de produto e marca. Essa entrega será feita para as 3 abordagens de classificação, totalizando 6 planilhas de resulatdos. 

A solução contempla três abordagens distintas para a classificação:

- Classificador por quantidade de palavras — Utiliza uma regra simples com base no número de palavras positivas e negativas encontradas no texto.

- CountVectorizer — técnica de vetorização que transforma o texto em uma matriz de frequências de palavras, permitindo o uso de modelos de machine learning.

- TF-IDF (Term Frequency-Inverse Document Frequency) — abordagem que pondera a importância das palavras considerando a frequência no corpus, resultando em vetores mais informativos para classificação.

## **3.0 Ferramentas utilizadas**

- **Python (Anaconda):** Pré-processamento, modelagem e avaliação.
- **Pandas / seaborn / matplotlib/ Scikit-learn / nltk / re / wordcloud:** Bibliotecas para manipulação e NLP.
- **Jupyter Notebook:** Ambiente de desenvolvimento.
  
## **4.0 Desenvolvimento**

O desenvolvimento detalhado está disponível no notebook Avaliação de Produtos em anexo. 

As estapas exploradas são:
- Limpeza e pré-processamento dos dados textuais
- Criação de três abordagens de classificação:
  -   Classificador por contagem de palavras: Abordagem simples e interpretável, baseada na contagem de palavras positivas e negativas presentes nas avaliações. Para isso, utilizei dois dicionários previamente definidos: um com palavras de conotação positiva e outro com palavras negativas.
  -   Classificação com CountVectorizer: Transforma os textos em vetores com base na frequência de palavras. Modelo treinado com o algoritmo supervisionado Naive Bayes.
  - Classificação com TF-IDF: Utiliza a ponderação de termos para melhorar a relevância dos vetores. Aplicação do mesmo classificador com dados vetorizados. Modelo treinado com o algoritmo supervisionado Logistic Regressor.
- Avaliação de desempenho dos modelos.
- Resultado dos modelos (planilhas com as classificações das avaliações).
- Comparação entre as abordagens.

O projeto foi dividido em três abordagens de classificação:

### 5.1 Classificador por contagem de palavras
Abordagem simples e interpretável, baseada na contagem de palavras positivas e negativas presentes nas avaliações. Para isso, utilizei dois dicionários previamente definidos: um com palavras de conotação positiva e outro com palavras negativas.

### 5.2 Classificação com CountVectorizer
Transforma os textos em vetores com base na frequência de palavras. Modelo treinado com algoritmo supervisionado (ex: Naive Bayes).

### 5.3 Classificação com TF-IDF
Utiliza a ponderação de termos para melhorar a relevância dos vetores. Aplicação do mesmo classificador com dados vetorizados.


## **5.0 Resultados**

