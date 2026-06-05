# Hospital Length of Stay Prediction (EN)

> **End-to-end machine learning project | Post-graduation final project **

This project predicts the hospital Length of Stay (LOS) category for patients using structured clinical data. It covers the full data science workflow: from exploratory analysis to machine learning modeling.

---

## Project Overview

| Item | Detail |
|---|---|
| **Dataset** | [Healthcare Dataset – Kaggle](https://www.kaggle.com/datasets/prasad22/healthcare-dataset) |
| **Records** | 55,500 patients |
| **Target** | LOS Category (Short / Medium / Long Stay) |
| **Models** | Decision Tree · Random Forest |
| **Language** | Python 3 |

---

## Project Structure

```
├── data/
│   ├── raw/                  # Original dataset
│   ├── staging/              # Staged dataset
│   ├── processed/            # Cleaned and encoded datasets
│   └── results/              # Model outputs and confusion matrices
├── notebooks/
│   ├── 01_EDA.ipynb
│   ├── 02_Pre-processing.ipynb
│   ├── 03_Decision_tree_model.ipynb
│   └── 04_Random_Forest_model.ipynb
├── requirements.txt
└── README.md
```

---

## Workflow

### 1 · Exploratory Data Analysis
- Investigated distributions, class balance, and feature relationships
- Key finding: **Medical condition showed a strong relationship with Length of Stay.**
  - Alzheimer's: ~54 days average · Flu: ~2.5 days average
- LOS is positively skewed (mean ≈ 18 days, median ≈ 8 days)

### 2 · Data Preprocessing
- Removed non-predictive columns (Name, Doctor, Hospital, Room Number, Billing Amount)
- Date columns removed to prevent data leakage
- Gender binary-encoded (0/1)
- Categorical features one-hot encoded (Blood Type, Medical Condition, Admission Type, Medication, Test Results)
- LOS transformed into 3 categories based on clinical benchmarks:

| Category | Days | Records |
|---|---|---|
| Short Stay | ≤ 5 days | 21,080 |
| Medium Stay | 6 – 14 days | 14,883 |
| Long Stay | ≥ 15 days | 19,537 |

### 3 · Modeling
- Two versions tested: **with** and **without** Insurance Provider
- Train / Test split: 80% / 20% (stratified)
- Models: `DecisionTreeClassifier` · `RandomForestClassifier`

---

## Results

### Decision Tree

| Version | Accuracy | Precision | Recall | F1-Score |
|---|---|---|---|---|
| With Insurance | 75.2% | 76% | 75% | 75% |
| Without Insurance | 76.5% | 77% | 76% | 77% |

### Random Forest

| Version | Accuracy | Precision | Recall | F1-Score |
|---|---|---|---|---|
| With Insurance | 78.7% | 78% | 79% | 78% |
| Without Insurance | 77.4% | 77% | 77% | 77% |

> **Key insight:** Removing Insurance Provider slightly improved the Decision Tree but had the opposite effect on Random Forest, confirming that the variable contributes marginally to prediction.

## Key Findings

- Long Stay was the easiest category for the models to identify.
- Medium Stay showed the highest classification difficulty.
- Insurance Provider had limited predictive value.

---

## Tech Stack

`Python` · `Pandas` · `NumPy` · `Matplotlib` · `Seaborn` · `Scikit-Learn`

---

## How to Run

```bash
# Clone the repository
git clone https://github.com/souigoralvim/length-of-stay-descomplica.git
cd length-of-stay-descomplica

# Install dependencies
pip install -r requirements.txt

# Run notebooks in order
# 01_EDA → 02_Pre-processing → 03_Decision_tree_model → 04_Random_Forest_model
```
---

## About

This project was developed as the final assignment of a post-graduation program in Data Science. It is also part of my data portfolio, demonstrating skills in data cleaning, EDA, feature engineering, and machine learning fundamentals applied to a real-world healthcare scenario.

---

# Predição de Tempo de Internação Hospitalar (PT)

> **Projeto de machine learning ponta a ponta | Trabalho final de pós-graduação**

Este projeto prevê a categoria de Tempo de Internação (LOS) de pacientes hospitalares utilizando dados clínicos estruturados. Cobre o fluxo completo de ciência de dados: da análise exploratória à modelagem com machine learning.

---

## Visão Geral

| Item | Detalhe |
|---|---|
| **Dataset** | [Healthcare Dataset – Kaggle](https://www.kaggle.com/datasets/prasad22/healthcare-dataset) |
| **Registros** | 55.500 pacientes |
| **Target** | Categoria de LOS (Curta / Média / Longa Internação) |
| **Modelos** | Decision Tree · Random Forest |
| **Linguagem** | Python 3 |

---

## Estrutura do Projeto

```
├── data/
│   ├── raw/                  # Dataset original
│   ├── staged/               # Dataset semi-processados
│   ├── processed/            # Datasets limpos e codificados
│   └── results/              # Resultados dos modelos e matrizes de confusão
├── notebooks/
│   ├── 01_EDA.ipynb
│   ├── 02_Pre-processing.ipynb
│   ├── 03_Decision_tree_model.ipynb
│   └── 04_Random_Forest_model.ipynb
├── requirements.txt
└── README.md
```

---

## Fluxo de Trabalho

### 1 · Análise Exploratória de Dados (EDA)
- Investigação de distribuições, balanceamento de classes e relações entre variáveis
- Principal descoberta: **Condição Médica apresenta uma forte relação com o Tempo de Internação.**
  - Alzheimer: ~54 dias de média · Gripe: ~2,5 dias de média
- LOS apresenta assimetria positiva (média ≈ 18 dias, mediana ≈ 8 dias)

### 2 · Pré-processamento
- Remoção de colunas não preditivas (Nome, Médico, Hospital, Quarto, Valor da Conta)
- Colunas de data removidas para evitar vazamento de dados (*data leakage*)
- Gênero codificado como binário (0/1)
- Variáveis categóricas com *one-hot encoding* (Tipo Sanguíneo, Condição Médica, Tipo de Admissão, Medicamento, Resultado do Exame)
- LOS transformado em 3 categorias baseadas em referências clínicas:

| Categoria | Dias | Registros |
|---|---|---|
| Curta Internação | ≤ 5 dias | 21.080 |
| Média Internação | 6 – 14 dias | 14.883 |
| Longa Internação | ≥ 15 dias | 19.537 |

### 3 · Modelagem
- Duas versões testadas: **com** e **sem** a variável Plano de Saúde
- Divisão treino / teste: 80% / 20% (estratificado)
- Modelos: `DecisionTreeClassifier` · `RandomForestClassifier`

---

## Resultados

### Decision Tree

| Versão | Acurácia | Precisão | Recall | F1-Score |
|---|---|---|---|---|
| Com Plano de Saúde | 75,2% | 76% | 75% | 75% |
| Sem Plano de Saúde | 76,5% | 77% | 76% | 77% |

### Random Forest

| Versão | Acurácia | Precisão | Recall | F1-Score |
|---|---|---|---|---|
| Com Plano de Saúde | 78,7% | 78% | 79% | 78% |
| Sem Plano de Saúde | 77,4% | 77% | 77% | 77% |

> **Insight principal:** Remover a variável Plano de Saúde melhorou levemente a Árvore de Decisão, mas teve efeito oposto no Random Forest — confirmando que a variável contribui marginalmente para a predição.

## Principais Descobertas

- Longa Internação foi a categoria mais fácil para os modelos identificarem.
- Média Internação apresentou a maior dificuldade de classificação.
- Plano de Saúde teve valor preditivo limitado.

---

## 🛠️ Tecnologias Utilizadas

`Python` · `Pandas` · `NumPy` · `Matplotlib` · `Seaborn` · `Scikit-Learn`

---

## ▶️ Como Executar

```bash
# Clonar o repositório
git clone https://github.com/souigoralvim/length-of-stay-descomplica.git
cd length-of-stay-descomplica

# Instalar dependências
pip install -r requirements.txt

# Executar os notebooks na ordem
# 01_EDA → 02_Pre-processing → 03_Decision_tree_model → 04_Random_Forest_model
```

---

## 📌 Sobre

Este projeto foi desenvolvido como trabalho final de uma pós-graduação em Ciência de Dados. Faz parte também do meu portfólio de dados, demonstrando habilidades em limpeza de dados, análise exploratória, engenharia de features e fundamentos de machine learning aplicados a um cenário real de saúde.
