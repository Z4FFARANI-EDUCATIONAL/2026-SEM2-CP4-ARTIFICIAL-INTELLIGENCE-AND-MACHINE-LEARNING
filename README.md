# Detecção de Fraudes · Inteligência Artificial & Machine Learning

| Integrante | RM |
|---|---|
| [Guilherme Santos Nunes](https://github.com/sannunez) | RM558989 |
| [Kaique Zaffarani](https://github.com/Z4ffarani) | RM556677 |
| [Pedro Josué Pereira Almeida](https://github.com/Pedro-Josue) | RM554913 |

Checkpoint 4 · 2026.2 · Engenharia de Software · FIAP

---

## Esta entrega: Inteligência Artificial & Machine Learning

**Detecção de fraudes em cartão de crédito**, comparando uma abordagem supervisionada e uma não supervisionada em um problema de classe extremamente rara.

- **Análise exploratória:** medição do desbalanceamento (0,17% de fraudes), verificação de tipos, escala e duplicados, e discussão de por que a acurácia não basta para avaliar o modelo.
- **Regressão Logística (supervisionado):** busca sobre penalização L1, L2 e ElasticNet, quatro valores de `C` e `class_weight` padrão ou balanceado, com e sem PCA, usando divisão treino/validação/teste (60/20/20).
- **Isolation Forest (não supervisionado):** variação de `n_estimators`, `contamination` (incluindo a taxa real de fraude) e `max_samples`, com e sem PCA.
- **Comparação crítica:** a Regressão Logística sem PCA obteve o melhor F1 no teste (0,747) e o Isolation Forest detectou 27 das 99 fraudes sem usar rótulos. Discussão de por que o PCA piorou os dois modelos e de como combinar as abordagens.

**Dados:** [Credit Card Fraud Detection — ULB / Kaggle](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud), com 284.807 transações de cartões europeus (set/2013), 30 atributos (`Time`, `Amount` e `V1` a `V28`, já transformados por PCA) e alvo binário. O arquivo tem 150 MB e não é versionado: o notebook baixa automaticamente uma cópia pública idêntica na primeira execução.

| Entregável | Onde |
|---|---|
| Notebook | [`CP4-AI.ipynb`](CP4-AI.ipynb) |

## Como executar

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
jupyter notebook CP4-AI.ipynb
```

---

## Tecnologias

[![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org)
[![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)](https://jupyter.org)
[![pandas](https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white)](https://pandas.pydata.org)
[![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)](https://numpy.org)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)](https://scikit-learn.org)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat-square)](https://matplotlib.org)
[![seaborn](https://img.shields.io/badge/seaborn-4C72B0?style=flat-square)](https://seaborn.pydata.org)

---

## Referências

| # | Referência | Aplicação no projeto |
|---|---|---|
| 1 | [ULB / Kaggle — Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud) | Base de dados de transações |
| 2 | [scikit-learn — `IsolationForest`](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.IsolationForest.html) | Abordagem não supervisionada |
| 3 | [scikit-learn — `LogisticRegression`](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html) | Abordagem supervisionada |
