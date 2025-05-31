<h1 align="center"> Análise de Sentimentos em Avaliações de Produtos Amazon<br /> </h1>

## **1.0 Visão geral**

Este projeto tem como objetivo principal analisar e classificar avaliações de produtos da Amazon, identificando automaticamente se uma avaliação é positiva ou negativa. A partir de uma base real de avaliações, implementei 3 diferentes abordagens de processamento de linguagem natural (NLP) para transformar textos em dados estruturados e aplicar algoritmos de classificação para prever o sentimento das avaliações.

A base de dados utilizada neste projeto foi obtida por meio de web scraping realizado na Amazon e disponibilizada por um usuário da comunidade no Kaggle, através do seguinte link:

🔗 [Amazon Product Review Dataset on Kaggle](https://www.kaggle.com/datasets/sampaiovitor/avaliaes-em-portugus-amazon-e-mercado-livre)/)

> ⚠️ **Observação:** O autor do dataset não especifica o período de coleta das avaliações nem fornece detalhes adicionais sobre a metodologia de extração. Por se tratar de dados obtidos via scraping, é importante considerar possíveis limitações quanto à representatividade temporal e à completude das informações.

O projeto tem impacto direto em áreas como comércio eletrônico, suporte ao cliente e análise de reputação de produtos, permitindo automatizar a triagem de feedbacks dos consumidores, identificar produtos mal avaliados com maior rapidez e fornecer insights relevantes para decisões de marketing e melhorias de produto.

## **2.0 Objetivos técnicos**

Além da construção dos classificadores, o objetivo técnico deste projeto é a entrega de planilhas em formato Excel contendo os resultados da análise de sentimentos. Para cada uma das três abordagens de classificação — contagem de palavras, vetorização com CountVectorizer e TF-IDF — serão geradas duas planilhas com:

Distribuição absoluta: quantidade de avaliações positivas e negativas, segmentadas por tipo de produto e marca.

Distribuição percentual: representação em percentual dessas classificações nas mesmas segmentações.

Ao todo, serão entregues 6 planilhas contendo uma visão consolidada dos resultados obtidos em cada abordagem, permitindo comparações detalhadas e facilitando a interpretação dos padrões de sentimento por produto e marca.

As três abordagens distintas para a classificação são:

- Classificador por quantidade de palavras — utiliza uma regra simples com base no número de palavras positivas e negativas encontradas no texto.

- CountVectorizer — técnica de vetorização que transforma o texto em uma matriz de frequências de palavras, permitindo o uso de modelos de machine learning.

- TF-IDF (Term Frequency-Inverse Document Frequency) — abordagem que pondera a importância das palavras considerando a frequência no corpus, resultando em vetores mais informativos para classificação.

## **3.0 Ferramentas utilizadas**

- **Python (Anaconda):** Pré-processamento, modelagem e avaliação.
- **Pandas / seaborn / matplotlib/ Scikit-learn / nltk / re / wordcloud:** Bibliotecas para manipulação e NLP.
- **Jupyter Notebook:** Ambiente de desenvolvimento.
- **ChatGpt:** IA generativa para criar o target das avaliações. Essa classificação foi importante para o treinamento dos modelos supervisionados .
  
## **4.0 Desenvolvimento**

O desenvolvimento detalhado está disponível no notebook Avaliação de Produtos em anexo. 

As estapas implementadas são:

- Criação de um prompt no chatgpt para gerar classificações das avaliações. Sendo, 0: negativo e 1:positivo. Resultando na base de dados: avaliacoes_classificadas.csv.
- Importação, limpeza e pré-processamento dos dados textuais.
- Criação de três abordagens de classificação:
  -   **Classificador por contagem de palavras:** Abordagem simples e interpretável, baseada na contagem de palavras positivas e negativas presentes nas avaliações. Para isso, utilizei dois dicionários previamente definidos: um com palavras de conotação positiva e outro com palavras negativas.
  -   **Classificação com CountVectorizer:** Transforma os textos em vetores com base na frequência de palavras. Modelo treinado com o algoritmo supervisionado Naive Bayes.
  -   **Classificação com TF-IDF:** Utiliza a ponderação de termos para melhorar a relevância dos vetores. Aplicação do mesmo classificador com dados vetorizados. Modelo treinado com o algoritmo supervisionado Logistic Regressor.
- Avaliação de desempenho dos modelos.
- Resultado dos modelos (planilhas com as classificações das avaliações).
- Comparação entre as abordagens.

## **5.0 Resultados**

O principal objetivo deste projeto foi implementar diferentes abordagens de classificação de sentimentos em avaliações de produtos da Amazon, explorando as características, vantagens e desafios de cada técnica.

🔹 Abordagem 1 – Classificador por Contagem de Palavras
Nesta abordagem simples e interpretável, as avaliações foram classificadas com base na contagem de palavras positivas e negativas contidas nos textos, utilizando dois dicionários customizados. Um dos principais desafios enfrentados foi a criação desses dicionários base, que exigem uma curadoria cuidadosa para serem eficazes.

A elaboração dos conjuntos de palavras positivas e negativas depende de uma avaliação prévia das avaliações reais, sendo ideal contar com o apoio da área de operação ou especialistas do negócio para sugerirem termos representativos. Apesar de sua simplicidade e transparência, essa abordagem demanda uma constante manutenção e adaptação dos dicionários, o que pode limitar sua escalabilidade.

✅ Pontos fortes: fácil de interpretar, sem necessidade de modelo supervisionado.

⚠️ Limitações: dependência da qualidade dos dicionários; baixa adaptabilidade a novos contextos.

🔹 Abordagem 2 – Naive Bayes com CountVectorizer
Nesta abordagem, as avaliações foram convertidas em vetores numéricos com base na frequência absoluta das palavras (CountVectorizer) e classificadas por meio de um modelo supervisionado Naive Bayes.

A vetorização simplificada captura a presença de palavras-chave, mas não considera a importância relativa dos termos no corpus. Ainda assim, o modelo demonstrou bom desempenho em bases balanceadas, sendo uma solução eficiente para conjuntos de dados moderadamente complexos.

✅ Pontos fortes: rápida implementação, bom desempenho em bases simples.
⚠️ Limitações: sensível a palavras comuns, pode superestimar termos irrelevantes e depende de um dataset previamente rotulado.

🔹 Abordagem 3 – Regressão Logística com TF-IDF
Nesta abordagem, os textos foram vetorizados com TF-IDF (Term Frequency – Inverse Document Frequency), que pondera a importância de cada palavra com base em sua frequência no documento e na base como um todo. O modelo de classificação utilizado foi uma Regressão Logística, amplamente aplicada em problemas de NLP pela sua capacidade de lidar com alta dimensionalidade e fornecer probabilidades associadas às previsões.

Comparada às demais abordagens, esta apresentou melhor equilíbrio entre desempenho e generalização, com menor tendência ao overfitting. Ainda assim, para uma aplicação em produção, seria necessário um cuidado maior na validação cruzada, ajuste de hiperparâmetros e testes com dados reais não vistos.

✅ Pontos fortes: vetorização mais robusta, melhor generalização, modelo bem compreendido.
⚠️ Limitações: maior complexidade no ajuste e interpretação, sensível a ruídos e também requer um conjunto de dados rotulado para treinamento.

Considerações Finais
A comparação entre os métodos evidenciou que abordagens mais sofisticadas, como TF-IDF combinada com modelos supervisionados, tendem a oferecer maior precisão e capacidade de generalização. No entanto, a contagem de palavras, ainda têm valor quando simplicidade, interpretabilidade e baixo custo computacional são prioritários.

Para aplicações reais, recomenda-se:

- Refinamento dos dicionários de sentimentos com apoio do time de negócio.
- Inclusão de validação cruzada e tuning de hiperparâmetros.
- Avaliação de modelos mais avançados, como Word2Vec, FastText ou BERT.






