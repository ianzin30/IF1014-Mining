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

## 🤖 Modelos Implementados

### 1. Decision Tree (dt.ipynb)
- Classificador baseado em árvore de decisão
- Hiperparâmetros otimizados: criterion, max_depth, min_samples_split, min_samples_leaf
- **Melhor F1-Score**: ~0.9415

### 2. K-Nearest Neighbors (knn.ipynb)
- Algoritmo baseado em distância entre vizinhos
- Hiperparâmetros otimizados: n_neighbors, weights, p (distância)
- **Melhor F1-Score**: ~0.9461

### 3. Random Forest (random_forest.ipynb)
- Ensemble de árvores de decisão
- Hiperparâmetros otimizados: n_estimators, max_depth, min_samples_split, min_samples_leaf, bootstrap
- **Melhor F1-Score**: ~0.9610

### 4. Multi-Layer Perceptron (mlp.ipynb)
- Rede neural feedforward
- Hiperparâmetros otimizados: hidden_layer_sizes, activation, solver, alpha, learning_rate_init
- **Melhor F1-Score**: ~0.9517

### 5. MLP Ensemble (mlp_ensemble.ipynb)
- Comitê de redes neurais MLP
- Combina múltiplas MLPs usando voting

### 6. Stacking Classifier (stacking.ipynb)
- **Melhor modelo do projeto**
- Combina KNN, Random Forest e LightGBM
- Meta-modelo: Logistic Regression
- **Melhor F1-Score**: ~0.9644
- **Acurácia**: 0.9708
- **AUC**: 0.9951

## 🛠️ Metodologia

### Pré-processamento
- Balanceamento de classes com **SMOTE** (Synthetic Minority Over-sampling Technique)
- Pipeline de processamento usando `imblearn`

### Otimização de Hiperparâmetros
- **RandomizedSearchCV** com validação cruzada estratificada (5 folds)
- Múltiplas rodadas de otimização (20 iterações) para cada modelo
- Métrica principal: **F1-Score Macro**

### Validação
- Validação cruzada estratificada (StratifiedKFold)
- Conjunto de teste separado para avaliação final
- Métricas avaliadas: Acurácia, Precisão, Recall, F1-Score, AUC-ROC

## 📈 Resultados

| Modelo | F1-Score | Acurácia | AUC |
|--------|----------|----------|-----|
| Decision Tree | 0.9415 | - | - |
| KNN | 0.9461 | 0.9600 | - |
| Random Forest | 0.9610 | - | - |
| MLP | 0.9517 | - | - |
| **Stacking** | **0.9644** | **0.9708** | **0.9951** |

## 🚀 Como Executar

### Requisitos
```bash
pip install numpy pandas matplotlib scikit-learn imbalanced-learn lightgbm jupyter
```

### Executar Notebooks
```bash
jupyter notebook
```

Navegue até a pasta `Notebooks/` e abra o notebook desejado.

## 📝 Notebooks

- **exploratory.ipynb**: Análise exploratória inicial dos dados
- **dt.ipynb**: Implementação e otimização do Decision Tree
- **knn.ipynb**: Implementação e otimização do KNN
- **random_forest.ipynb**: Implementação e otimização do Random Forest
- **mlp.ipynb**: Implementação e otimização do MLP
- **mlp_ensemble.ipynb**: Ensemble de MLPs
- **stacking.ipynb**: Modelo de Stacking (melhor resultado)

## 🔍 Destaques Técnicos

- Uso de **Pipelines** para garantir reprodutibilidade
- **SMOTE** para lidar com desbalanceamento de classes
- **RandomizedSearchCV** para otimização eficiente de hiperparâmetros
- **Validação cruzada estratificada** para avaliação robusta
- **Stacking** com meta-modelo para combinar múltiplos algoritmos

## 📊 Visualizações

Todos os notebooks incluem:
- Matriz de confusão
- Curva ROC
- Gráficos de evolução do F1-Score ao longo das iterações
- Relatório de classificação detalhado

## 👥 Autor

Desenvolvido para a disciplina IF1014 - Mineração de Dados

## 📄 Licença

Este projeto é de código aberto para fins educacionais.

---

**Nota**: O modelo de Stacking apresentou o melhor desempenho geral, combinando as forças de diferentes algoritmos (KNN, Random Forest e LightGBM) com um meta-modelo de Regressão Logística.
