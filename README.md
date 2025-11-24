# IF1014-Mining

Projeto de Mineração de Dados desenvolvido para a disciplina IF1014, ministrada pelo professor Leandro Maciel Almeida sobre o nome Tópicos Avançados em SI4 - Data Mining. Este projeto utiliza o dataset de geolocalização Nomao sob diversos algoritmos de Machine Learning.

## 📊 Sobre o Dataset

O dataset Nomao é um conjunto de dados de classificação binária que contém 120 features baseadas em geolocalização, seu intuito é o desafio da deduplicação. Nomao era conhecido como um motor de busca de lugares, agregando informações sobre estabelecimentos e pontos de interesse. Sua base de dados era formada a partir de múltiplas fontes (web, GPS, usuários etc.), resultando em um volume expressivo de registros.


## Nomao Challenge
 
Competição de Data Mining realizada em 2012, com foco na deduplicação de registros de locais. O desafio central era criar modelos capazes de identificar se duas entradas correspondiam ao mesmo lugar, ou seja, consistia nos desafios da deduplicação.


## Qual o porquê de deduplicação?

- Qualidade dos Dados: A existência de registros duplicados prejudica buscas, relatórios e análises, afetando a confiabilidade do sistema.

- Decisões Estratégicas: Empresas que dependem de dados geoespaciais (logística, mapas digitais, delivery etc.) precisam de dados limpos e precisos para tomar decisões acertadas.

## Metas

- Deduplicação Eficiente: Desenvolver um modelo capaz de identificar se dois registros se referem ao mesmo local, reduzindo drasticamente o número de duplicatas.

- Melhoria de Indicadores: Alcançar métricas robustas (por exemplo, F1-score  elevado) que atestem a eficácia do modelo, em especial comparando com a literatura que encontramos.




## 🗂️ Estrutura do Projeto

```
IF1014-Mining/
├── README.md
├── Data/
│   ├── Nomao.features      # Descrição das features
│   ├── Nomao.names         # Metadados do dataset
│   ├── test.csv            # Conjunto de teste
│   └── train.csv           # Conjunto de treino
└── Notebooks/
    ├── exploratory.ipynb   # Análise exploratória dos dados
    ├── dt.ipynb            # Decision Tree
    ├── knn.ipynb           # K-Nearest Neighbors
    ├── random_forest.ipynb # Random Forest
    ├── mlp.ipynb           # Multi-Layer Perceptron
    ├── mlp_ensemble.ipynb  # Ensemble de MLPs
    ├── stacking.ipynb      # Stacking Classifier
    └── z.ipynb             # Notebook auxiliar
```